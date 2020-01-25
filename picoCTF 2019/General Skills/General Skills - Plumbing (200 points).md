
# General Skills - Plumbing (200 points)

## Challenge

*Sometimes you need to handle process data outside of a file. Can you find a way to keep the output from this program and search for the flag? Connect to 2019shell1.picoctf.com 18944.*

![Challenge](./_images/general_skills_plumbing_challenge.png)

## Flag

picoCTF{digital_plumb3r_1d5b7de7}

## Walkthrough

The remote server *2019shell1.picoctf.com 18944* is really chatty... A grep on the flag pattern should render him far less talkative:

```bash
m3oow@pico-2019-shell1:/problems/strings-it_5_1fd17da9526a76a4fffce289dee10fbb$ nc 2019shell1.picoctf.com 18944 | grep -i "picoctf{"
picoCTF{digital_plumb3r_1d5b7de7}
```
