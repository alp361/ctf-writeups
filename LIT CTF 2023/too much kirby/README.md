# too much kirby

## Description

> literally every single unused web chal jammed into one kirby-sized package (horrible painful amalgamation)
 
## Solution

* When I examined the source code of the website provided for this challenge, I understood that the challenge consisted of 5 stages. <br>
I needed to complete them sequentially in order to reach the flag. For the first two stages, I used the passwords disclosed in the <br>
source code of the website to pass through these stages.

![](https://github.com/alp361/ctf-writeups/blob/main/LIT%20CTF%202023/too%20much%20kirby/images/chal1.png)

<br>

![](https://github.com/alp361/ctf-writeups/blob/main/LIT%20CTF%202023/too%20much%20kirby/images/chal2.png)

* In the 3rd stage, it asked me for a username and password, but this time there was no information in the source code. <br>
I attempted a few simple SQL injection attempts over the `please dont inject me!` text on the site, but they didn't work.<br>
Then I tried a few default credentials, and among them, `test-test` worked successfully, allowing me to proceed to the next stage.

![](https://github.com/alp361/ctf-writeups/blob/main/LIT%20CTF%202023/too%20much%20kirby/images/chal3_default_creds.png)

* The 4th stage was similar to the first two, so I easily passed through it.

![](https://github.com/alp361/ctf-writeups/blob/main/LIT%20CTF%202023/too%20much%20kirby/images/chal4.png)

* In the 5th stage, I encountered a file upload section, asking me to upload a file named `kirby.txt`.

![](https://github.com/alp361/ctf-writeups/blob/main/LIT%20CTF%202023/too%20much%20kirby/images/upload.png)

* However, when I looked at the source code of the site, I noticed that there was a restriction on the file format that could be uploaded.<br>
I could only upload files in the formats of `JPG, JPEG, PNG, and GIF`.

![](https://github.com/alp361/ctf-writeups/blob/main/LIT%20CTF%202023/too%20much%20kirby/images/upload_source_code.png)

* Therefore, I uploaded a randomly named PNG file from my device and intercepted this request using Burp Suite. <br>
Then, among the headers, I found the part labeled "filename" and replaced its value with the requested file, `kirby.txt`. <br>
By sending the request in this manner, I was able to retrieve the flag.

![](https://github.com/alp361/ctf-writeups/blob/main/LIT%20CTF%202023/too%20much%20kirby/images/flag_found.png)

```
LITCTF{k1rBYl0L}
```
