Author: susie

#### Description

Files can always be changed in a secret way. Can you find the flag? [cat.jpg](https://mercury.picoctf.net/static/e5825f58ef798fdd1af3f6013592a971/cat.jpg)

#### Solution

Download the image, its an image of a cat.  Looking at the properties, we the license, it looks to be a hash, try base64 decoding and we get the answer.

Answer: `picoCTF{the_m3tadata_1s_modified}`
