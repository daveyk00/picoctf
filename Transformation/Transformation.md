Author: madStacks

#### Description

I wonder what this really is... [enc](https://mercury.picoctf.net/static/a757282979af14ab5ed74f0ed5e2ca95/enc) `''.join([chr((ord(flag[i]) << 8) + ord(flag[i + 1])) for i in range(0, len(flag), 2)])`

#### Solution

Download the file and place into https://gchq.github.io/CyberChef/
Trying a number of recipes, `Text Encoding Brute Force` shows us `UTF-16BE (1201)` gives the correct format.

Answer: `picoCTF{16_bits_inst34d_of_8_d52c6b93}`