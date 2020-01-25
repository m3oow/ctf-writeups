
# General Skills - First Grep (100 points)

## Challenge

*Can you find the flag in file? This would be really tedious to look through manually, something tells me there is a better way. You can also find the file in /problems/first-grep_4_6b0be85ad029e98c683231bdafec396c on the shell server.*

![Challenge](./_images/general_skills_first_grep_challenge.png)

## Flag

picoCTF{grep_is_good_to_find_things_ad4e9645}

## Walkthrough

For this challenge, you have to perform a grep inside a folder :

```bash
m3oow@pico-2019-shell1:~$ grep -i "picoCTF{" /problems/first-grep_4_6b0be85ad029e98c683231bdafec396c/*
picoCTF{grep_is_good_to_find_things_ad4e9645}
```
