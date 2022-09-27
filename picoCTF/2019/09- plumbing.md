# plumbing  
## Objetivo  
Sometimes you need to handle process data outside of a file. Can you find a way to keep the output from this program and search for the flag? Connect to `jupiter.challenges.picoctf.org 14291`.
## Solución  
```shell
┌──(kali㉿kali)-[~]
└─$ nc jupiter.challenges.picoctf.org 14291 | grep picoCTF
picoCTF{digital_plumb3r_ea8bfec7}

┌──(kali㉿kali)-[~]
└─$ 

```
picoCTF{digital_plumb3r_ea8bfec7}

## Referencias
- [Hint de pipe](http://www.linfo.org/pipes.html)
- [Uso de grap](https://www.hostinger.x/tutoriales/comando-grep-linux)
