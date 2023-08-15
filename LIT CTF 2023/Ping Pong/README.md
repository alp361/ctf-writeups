# Ping Pong

## Description

> I made this cool website where you can ping other websites!
 
## Solution

In the website provided for this challenge, it was possible to send a ping to a hostname entered in the input field. <br>
In the source code, I realized that there were no restrictions on this action, which led me to believe that other <br>
commands could also be executed.

![](https://github.com/alp361/ctf-writeups/blob/main/LIT%20CTF%202023/Ping%20Pong/images/source_code_rce.png)

To test this, I tried a simple payload and it worked.

![](https://github.com/alp361/ctf-writeups/blob/main/LIT%20CTF%202023/Ping%20Pong/images/rce_found.png)

As a result, I was able to obtain the flag by executing the command `google.com&cat flag.txt`.

![](https://github.com/alp361/ctf-writeups/blob/main/LIT%20CTF%202023/Ping%20Pong/images/flag_found.png)

```
LITCTF{I_sh0uld_b3_m0r3_c4r3ful}
```


