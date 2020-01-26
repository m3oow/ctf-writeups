
# Cryptography - caesar (100 points)

## Challenge

*Decrypt this [message](./ciphertext). You can find the ciphertext in /problems/caesar_5_d706b250ed3c6d2d2c72155de301a2f1 on the shell server.*

`ciphertext` content:

```raw
picoCTF{dspttjohuifsvcjdpobqjtwtvk}
```

## Flag

picoCTF{crossingtherubiconapisvsuj}

## Walkthrough

The string `dspttjohuifsvcjdpobqjtwtvk` is encrypted using Caesar cipher (substitution cipher). It can be easyly decrypted [here](https://www.dcode.fr/chiffre-cesar). The shift value is 1:

```raw
d => c
s => r
p => o
[...]
```
