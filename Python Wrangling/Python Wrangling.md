Author: syreal

#### Description

Python scripts are invoked kind of like programs in the Terminal... Can you run [this Python script](https://mercury.picoctf.net/static/325a52d249be0bd3811421eacd2c877a/ende.py) using [this password](https://mercury.picoctf.net/static/325a52d249be0bd3811421eacd2c877a/pw.txt) to get [the flag](https://mercury.picoctf.net/static/325a52d249be0bd3811421eacd2c877a/flag.txt.en)?

#### Solution

Download https://mercury.picoctf.net/static/325a52d249be0bd3811421eacd2c877a/ende.py, https://mercury.picoctf.net/static/325a52d249be0bd3811421eacd2c877a/pw.txt and https://mercury.picoctf.net/static/325a52d249be0bd3811421eacd2c877a/flag.txt.en

Looking at ende.py it requires arguments:

```shell
daveyk00-picoctf@webshell:~$ python ende.py
Usage: ende.py (-e/-d) [file]
daveyk00-picoctf@webshell:~$   
```


Runningj pythong ende.py -d flat.txt.en asks for a password, entering the contents of pw.txt, reveals the flag

Additionally we can redirect stdin
`python ende.py -d flag.txt.en < pw.txt`

Answer: `picoCTF{4p0110_1n_7h3_h0us3_ac9bd0ff}`

