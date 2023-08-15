# My boss left

## Description

> My boss left... Guess I can be a bit more loose on checking people. <br>
> http://litctf.org:31784/
 
## Solution

When we visited the website provided for this challenge, a login page appeared. <br>
In the source code, I found a password assigned to the variable `$valid_password`.

![](https://github.com/alp361/ctf-writeups/blob/main/LIT%20CTF%202023/My%20boss%20left/images/password.png)

I used this password for logging in, and I was able to reach the flag.

![](https://github.com/alp361/ctf-writeups/blob/main/LIT%20CTF%202023/My%20boss%20left/images/flag_found.png)



```
LITCTF{oOps_sh0uld_h4v3_us3d_str1ct_c0mp4r1sons}
```

