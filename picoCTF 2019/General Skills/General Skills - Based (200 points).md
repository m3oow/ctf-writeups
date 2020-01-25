
# General Skills - Based (200 points)

## Challenge

*To get truly 1337, you must understand different data encodings, such as hexadecimal or binary. Can you get the flag from this program to prove you are on the way to becoming 1337? Connect with nc 2019shell1.picoctf.com 29594.*

![Challenge](./_images/general_skills_based_challenge.png)

## Flag

picoCTF{learning_about_converting_values_e67b1990}

## Walkthrough

For this flag, you have to perform a series of conversion from Binary, Octal and Hex to ASCII. The result of each conversion has to be entered manually, but you've got enough time to use an external tool (like [https://www.rapidtables.com/convert/number/ascii-hex-bin-dec-converter.html](https://www.rapidtables.com/convert/number/ascii-hex-bin-dec-converter.html)).

```bash
m3oow@pico-2019-shell1:/problems/strings-it_5_1fd17da9526a76a4fffce289dee10fbb$ nc 2019shell1.picoctf.com 29594
Let us see how data is stored
colorado
Please give the 01100011 01101111 01101100 01101111 01110010 01100001 01100100 01101111 as a word.
...
you have 45 seconds.....

Input:
colorado
Please give me the  154 151 172 141 162 144 as a word.
Input:
lizard
Please give me the 6f76656e as a word.
Input:
oven
You've beaten the challenge
Flag: picoCTF{learning_about_converting_values_e67b1990}
```
