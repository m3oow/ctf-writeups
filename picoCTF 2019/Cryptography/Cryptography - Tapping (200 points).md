
# Cryptography - Tapping (200 points)

## Challenge

*Theres tapping coming in from the wires. What's it saying nc 2019shell1.picoctf.com 37911.*

## Flag

PICOCTF{M0RS3C0D31SFUN2265937663}

## Walkthrough

After a connection to `2019shell1.picoctf.com:37911`, we receive what seems to be morse code:

```bash
root@kali:~/Downloads# nc 2019shell1.picoctf.com 37911
.--. .. -.-. --- -.-. - ..-. { -- ----- .-. ... ...-- -.-. ----- -.. ...-- .---- ... ..-. ..- -. ..--- ..--- -.... ..... ----. ...-- --... -.... -.... ...-- } 
```

We get the flag after [decoding](https://www.dcode.fr/code-morse) the morse message: `PICOCTF{M0RS3C0D31SFUN2265937663}`
