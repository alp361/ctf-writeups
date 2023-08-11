# Cyberpunk Cafe

## Description

> This trend of restaurants getting rid of hard copies of their menus is kinda annoying,
> but this new cyberpunk-themed cafe is taking it a bit too far. Check out what they gave me.

## Solution

When I look into the `challenge.txt` file, the content of this file reminded me of a qr code consisting of 0s and 1s instead of black and white colors. <br>

Then, I wrote a simple python code that reshaped the given array of numbers to a 41x41, and converts 0s and 1s to the black and white colors. <br>

* Output of the code:

![qrCode](https://github.com/alp361/ctf-writeups/assets/69428956/cf0110b3-b02c-4ebc-a7f6-bad218725ef2)

* Finally, I decoded this qr code and retrieve the flag:

![flag_found](https://github.com/alp361/ctf-writeups/assets/69428956/fb953dab-411b-441c-b3cd-16ecc3ce0526)


```
flag{br1ng_b4ck_phys1c4l_menu5}
```

