# unsecure

## Description

> As it turns out, the admin who runs our website is quite insecure. They use password123 as their password. <br>
> (Wrap the flag in LITCTF{}) <br>
> http://litctf.org:31776/
 
## Solution

When I entered the website provided for this challenge, I encountered a message that said, `Try going to /welcome instead of here.`

![](https://github.com/alp361/ctf-writeups/blob/main/LIT%20CTF%202023/unsecure/images/website.png)

When I navigated to this path, a login page appeared. Following the description provided for the challenge, I entered `admin` for the <br>
username and `password123` for the password credentials. It redirected me several times to different paths, ultimately leading to the <br>
Wikipedia URL redirection page.

![](https://github.com/alp361/ctf-writeups/blob/main/LIT%20CTF%202023/unsecure/images/redirect_after_login.png)

After logging in, I intercepted the request using Burp Suite and examined the sequence of redirects. The path of the page just before <br>
reaching the mentioned Wikipedia page had the flag format. This way, I was able to obtain the flag.

![](https://github.com/alp361/ctf-writeups/blob/main/LIT%20CTF%202023/unsecure/images/flag_found.png)


```
LITCTF{0k4y_m4yb3_1_l13d}
```
