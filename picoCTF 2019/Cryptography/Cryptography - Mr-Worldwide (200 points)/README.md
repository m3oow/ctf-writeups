
# Cryptography - Mr-Worldwide (200 points)

## Challenge

*A musician left us a [message](./message.txt). What's it mean?*

`message.txt` content:

```raw
picoCTF{(35.028309, 135.753082)(46.469391, 30.740883)(39.758949, -84.191605)(41.015137, 28.979530)(24.466667, 54.366669)(3.140853, 101.693207)_(9.005401, 38.763611)(-3.989038, -79.203560)(52.377956, 4.897070)(41.085651, -73.858467)(57.790001, -152.407227)(31.205753, 29.924526)}
```

## Flag

picoCTF{KODIAK_ALASKA}

## Walkthrough

Those are GPS coordinates, using Google Maps and a little guessing:

```raw
(35.028309, 135.753082) Kyoto
(46.469391, 30.740883) Odessa
(39.758949, -84.191605) Dayton
(41.015137, 28.979530) Istanbul
(24.466667, 54.366669) Abu Dhabi
(3.140853, 101.693207) Kuala Lumpur
_
(9.005401, 38.763611) Addis-Abeba
(-3.989038, -79.203560) Loja
(52.377956, 4.897070) Amsterdam
(41.085651, -73.858467) Sleepy Hollow
(57.790001, -152.407227) Kodiak
(31.205753, 29.924526) Alexandria
```

By taking the first letter of each city / place, we got the flag: `picoCTF{KODIAK_ALASKA}`.
