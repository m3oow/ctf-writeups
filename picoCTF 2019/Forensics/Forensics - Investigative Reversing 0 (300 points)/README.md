
# Cryptography - Investgate Reversing 0 (300 points)

## Challenge

*We have recovered a [binary](./mystery) and an [image](./mystery.png). See what you can make of it. There should be a flag somewhere. Its also found in /problems/investigative-reversing-0_5_5cc04ac6883dd5a1d0bb9024323b6734 on the shell server.*

Hints:

* *Try using some forensics skills on the image.*
* *This problem requires both forensics and reversing skills.*
* *A hex editor may be helpful.*

## Flag

picoCTF{f0und_1t_9de03050}

## Walkthrough

First and before anything complicated, let's try a `strings` on both files:

```bash
root@kali:~/Downloads# strings mystery | grep -i pico
root@kali:~/Downloads# strings mystery.png | grep -i pico
picoCTK
```

The result is strange, but clearly a good start. There is what seems to be a flag at the end of `mystery.png`:

```raw
[...]
d2!‚ ‚ ‚ Bö!#‚ ‚ ‚ ‚ d2!‚ ‚ ‚ Bö!#‚ ‚ ‚ ‚ dÿïÿý^íZ8ÐV    IEND®B`‚picoCTK€k5zsid6q_9de03050}
```

The string `picoCTK€k5zsid6q_9de03050` probably has to be transformed / decoded to get the real flag using something. Let's investigate the binary with the help of [GHIDRA](https://ghidra-sre.org/), which quickly gives us a C decompilation:

```C

void main(void)

{
  long lVar1;
  FILE *__stream;
  FILE *__stream_00;
  size_t sVar2;
  long in_FS_OFFSET;
  int local_54;
  int local_50;
  char local_38 [4];
  char local_34 [4];
  char local_29;
  
  lVar1 = *(long *)(in_FS_OFFSET + 0x28);
  __stream = fopen("flag.txt","r");
  __stream_00 = fopen("mystery.png","a");
  if (__stream == (FILE *)0x0) {
    puts("No flag found, please make sure this is run on the server");
  }
  if (__stream_00 == (FILE *)0x0) {
    puts("mystery.png is missing, please run this on the server");
  }
  sVar2 = fread(local_38,0x1a,1,__stream);
  if ((int)sVar2 < 1) {
                    /* WARNING: Subroutine does not return */
    exit(0);
  }
  puts("at insert");
  fputc((int)local_38[0],__stream_00);
  fputc((int)local_38[1],__stream_00);
  fputc((int)local_38[2],__stream_00);
  fputc((int)local_38[3],__stream_00);
  fputc((int)local_34[0],__stream_00);
  fputc((int)local_34[1],__stream_00);
  local_54 = 6;
  while (local_54 < 0xf) {
    fputc((int)(char)(local_38[local_54] + '\x05'),__stream_00);
    local_54 = local_54 + 1;
  }
  fputc((int)(char)(local_29 + -3),__stream_00);
  local_50 = 0x10;
  while (local_50 < 0x1a) {
    fputc((int)local_38[local_50],__stream_00);
    local_50 = local_50 + 1;
  }
  fclose(__stream_00);
  fclose(__stream);
  if (lVar1 != *(long *)(in_FS_OFFSET + 0x28)) {
                    /* WARNING: Subroutine does not return */
    __stack_chk_fail();
  }
  return;
}
```

There are some weird analysis here (some var are badly named, and are just an index shift of *local_38*), but we can infer how it works :

* The first 6 bytes of our flag are written at the end of `mystery.png` as it:

```C
fputc((int)local_38[0],__stream_00);
fputc((int)local_38[1],__stream_00);
fputc((int)local_38[2],__stream_00);
fputc((int)local_38[3],__stream_00);
fputc((int)local_34[0],__stream_00);
fputc((int)local_34[1],__stream_00);
```

* \x05 is added to the next 9 bytes:

```C
local_54 = 6;
while (local_54 < 0xf) {
  fputc((int)(char)(local_38[local_54] + '\x05'),__stream_00);
  local_54 = local_54 + 1;
}
```

* \x03 is substracted to the next byte:

```C
fputc((int)(char)(local_29 + -3),__stream_00);
```

* Finally, the last bytes are written as it:

```C
local_50 = 0x10;
while (local_50 < 0x1a) {
  fputc((int)local_38[local_50],__stream_00);
  local_50 = local_50 + 1;
}
```

With all this:

```raw
p i c o C T K € k 5 z s i d 6 q _ 9 d e 0 3 0 5 0 }
| | | | | | | | | | | | | | | | | | | | | | | | | |
p i c o C T F { f 0 u n d _ 1 t _ 9 d e 0 3 0 5 0 }
```
