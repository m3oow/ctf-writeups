
# Cryptography - waves over lambda (300 points)

## Challenge

*We made alot of substitutions to encrypt this. Can you decrypt it? Connect with nc 2019shell1.picoctf.com 37925.*

```bash
root@kali:~/chal# nc 2019shell1.picoctf.com 37925
-------------------------------------------------------------------------------
nfuzvmok atvt ck dflv yxmz - yvtpltund_ck_n_fjtv_xmisqm_imvksrgfgv
-------------------------------------------------------------------------------
amjcuz amq kfit ocit mo id qckgfkmx ratu cu xfuqfu, c amq jckcotq oat svcocka ilktli, muq imqt ktmvna mifuz oat sffek muq imgk cu oat xcsvmvd vtzmvqcuz ovmukdxjmucm; co amq kovlne it oamo kfit yfvteufrxtqzt fy oat nfluovd nflxq amvqxd ymcx of amjt kfit cigfvomunt cu qtmxcuz rcoa m ufsxtimu fy oamo nfluovd. c ycuq oamo oat qckovcno at umitq ck cu oat twovtit tmko fy oat nfluovd, blko fu oat sfvqtvk fy oavtt komotk, ovmukdxjmucm, ifxqmjcm muq slefjcum, cu oat icqko fy oat nmvgmoacmu ifluomcuk; fut fy oat rcxqtko muq xtmko eufru gfvocfuk fy tlvfgt. c rmk ufo msxt of xczao fu mud img fv rfve zcjcuz oat twmno xfnmxcod fy oat nmkoxt qvmnlxm, mk oatvt mvt uf imgk fy oack nfluovd mk dto of nfigmvt rcoa flv fru fvqumunt klvjtd imgk; slo c yfluq oamo sckovcoh, oat gfko ofru umitq sd nfluo qvmnlxm, ck m ymcvxd rtxx-eufru gxmnt. c kamxx tuotv atvt kfit fy id ufotk, mk oatd imd vtyvtka id itifvd ratu c omxe fjtv id ovmjtxk rcoa icum.
```

## Flag

picoCTF{frequency_is_c_over_lambda_marsbwpopr}

## Walkthrough

After some search (and a lot of dead ends), this text is encrypted using mono-alphabetical substitution (see [here](https://www.dcode.fr/substitution-monoalphabetique#q3) for more information on how to detect this).

Using [dcode.fr](https://www.dcode.fr/substitution-monoalphabetique), we found the key for the substitution: MSNQTYZACBEXIUFGPVKOLJRWDH

MSNQTYZACBEXIUFGPVKOLJRWDH

It gives us:

```raw
-------------------------------------------------------------------------------
CONGRATS HERE IS YOUR FLAG - FREQUENCY_IS_C_OVER_LAMBDA_MARSBWPOPR
-------------------------------------------------------------------------------
HAVING HAD SOME TIME AT MY DISPOSAL WHEN IN LONDON, I HAD VISITED THE BRITISH MUSEUM, AND MADE SEARCH AMONG THE BOOKS AND MAPS IN THE LIBRARY REGARDING TRANSYLVANIA; IT HAD STRUCK ME THAT SOME FOREKNOWLEDGE OF THE COUNTRY COULD HARDLY FAIL TO HAVE SOME IMPORTANCE IN DEALING WITH A NOBLEMAN OF THAT COUNTRY. I FIND THAT THE DISTRICT HE NAMED IS IN THE EXTREME EAST OF THE COUNTRY, JUST ON THE BORDERS OF THREE STATES, TRANSYLVANIA, MOLDAVIA AND BUKOVINA, IN THE MIDST OF THE CARPATHIAN MOUNTAINS; ONE OF THE WILDEST AND LEAST KNOWN PORTIONS OF EUROPE. I WAS NOT ABLE TO LIGHT ON ANY MAP OR WORK GIVING THE EXACT LOCALITY OF THE CASTLE DRACULA, AS THERE ARE NO MAPS OF THIS COUNTRY AS YET TO COMPARE WITH OUR OWN ORDNANCE SURVEY MAPS; BUT I FOUND THAT BISTRITZ, THE POST TOWN NAMED BY COUNT DRACULA, IS A FAIRLY WELL-KNOWN PLACE. I SHALL ENTER HERE SOME OF MY NOTES, AS THEY MAY REFRESH MY MEMORY WHEN I TALK OVER MY TRAVELS WITH MINA.
```
