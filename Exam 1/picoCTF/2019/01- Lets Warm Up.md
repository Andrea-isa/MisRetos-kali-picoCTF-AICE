# Lets Warm Up  
## Objetivo  
Si te dijera que una palabra comienza con 0x70 en hexadecimal, ¿con qué comenzaría en ASCII?
If I told you a word started with 0x70 in hexadecimal, what would it start with in ASCII?
## Solución  
```shell
Usando la consola podemos convertir el hexadecimal que nos dan a código ASCII
┌──(kali㉿kali)-[~]
└─$ echo -e "\x70"                                                                     
p
   
┌──(kali㉿kali)-[~]
└─$ printf '\x70'
p                                                                                       

┌──(kali㉿kali)-[~]
└─$

```
*picoCTF{}*

## Referencias
- [Convertir hexadecimal en ASCII](https://www.baeldung.com/linux/character-hex-to-ascii)
- []()