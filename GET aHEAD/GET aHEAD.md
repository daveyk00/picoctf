Author: madStacks

#### Description

Find the flag being held on this server to get ahead of the competition [http://mercury.picoctf.net:34561/](http://mercury.picoctf.net:34561/)

#### Solution

Look at the website, `Choose Red` the URL changes to `http://mercury.picoctf.net:34561/index.php?` and `Choose Blue` the URL changes to `http://mercury.picoctf.net:34561/index.php`

Looking at the source, Red is a GET and Blue is a POST HTTP

Open in Burpsuite with Proxy on.

Capture the request and copy to repeater.

We can see both the GET and POST requests.

Change the GET to a HEAD based on the hint 1 and the name of the challenge:

`HEAD /index.php HTTP/1.1`

and the flag is revealed.

Answer: `picoCTF{r3j3ct_th3_du4l1ty_8f878508}`
