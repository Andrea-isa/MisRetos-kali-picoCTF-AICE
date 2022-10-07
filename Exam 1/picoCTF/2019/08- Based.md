# Based  
## Objetivo  
To get truly 1337, you must understand different data encodings, such as hexadecimal or binary. Can you get the flag from this program to prove you are on the way to becoming 1337? Connect with `nc jupiter.challenges.picoctf.org 15130`.
## Solución  
Se hace una conecciòn directa con el comando que se nos da, ahora nos darà una serie de palabras en varias bases, en especifico el binario, octal y hexadecimal, las cuales debemos desifrar con una herramienta llamada CyberChef.
```shell
┌──(kali㉿kali)-[~]
└─$ nc jupiter.challenges.picoctf.org 15130
Let us see how data is stored
computer
Please give the 01100011 01101111 01101101 01110000 01110101 01110100 01100101 01110010 as a word.
...
you have 45 seconds.....

Input:
computer
Please give me the  154 141 155 160 as a word.
Input:
lamp
Please give me the 6e75727365 as a word.
Input:
nurse
You've beaten the challenge
Flag: picoCTF{learning_about_converting_values_02167de8}
  
┌──(kali㉿kali)-[~]
└─$
```
picoCTF{learning_about_converting_values_02167de8}

## Referencias
Las sigientes referencias son links directos a las palabras ya econtradas en la plataforma CyberChef.
- [Binary](https://gchq.github.io/CyberChef/#recipe=From_Binary('Space',8)&input=MDExMDAwMTEgMDExMDExMTEgMDExMDExMDEgMDExMTAwMDAgMDExMTAxMDEgMDExMTAxMDAgMDExMDAxMDEgMDExMTAwMTA)
- [Octal](https://gchq.github.io/CyberChef/#recipe=From_Octal('Space')&input=MTU0IDE0MSAxNTUgMTYw)
- [Hex](https://gchq.github.io/CyberChef/#recipe=From_Hex('Auto')&input=NmU3NTcyNzM2NQ)

