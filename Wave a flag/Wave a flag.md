Author: syreal

#### Description

Can you invoke help flags for a tool or binary? [This program](https://mercury.picoctf.net/static/f95b1ee9f29d631d99073e34703a2826/warm) has extraordinarily helpful information...

##### Solution
Download https://mercury.picoctf.net/static/f95b1ee9f29d631d99073e34703a2826/warm

`head warm` shows it to be an executable file
`strings warm | grep picoCTF` reveals the flag.

To look further, we `chmod +x warm` then run it `./warm`
`Hello user! Pass me a -h to learn what I can do!`

`$ ./warm -h` reveals the flag as well


Answer: `picoCTF{b1scu1ts_4nd_gr4vy_f0668f62}`