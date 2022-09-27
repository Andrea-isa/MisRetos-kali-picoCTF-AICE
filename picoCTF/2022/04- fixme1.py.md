# fixme1.py 
## Objetivo  
Fix the syntax error in this Python script to print the flag. [Download Python script](https://artifacts.picoctf.net/c/39/fixme1.py)
## Solución  
Descargamos el archivo, desde la consola vamos a la carpeta donde lo guardamos y lo ejecutamos, nos saldrà un error de identaciòn porlo que debemo editar el archivo, eso lo hacemos con `nano fixme1.py` corregimos y guardamos, para ver que sì se guardaron los cambios hacemos `cat` y luego volvemos a ejecutar, y asì nos da la flag.
```shell
┌──(kali㉿kali)-[~]
└─$ cd /home/kali/Desktop/CarpetaCompartida.Windows/RetosKali-exam--editar/CarpetaKali-exam/picoCTF/2022/

┌──(kali㉿kali)-[~/…/RetosKali-exam--editar/CarpetaKali-exam/picoCTF/2022]
└─$ ls
'01- runme.py.md'      '05- fixme2.py.md'   '09- PW Crack 3.md'   fixme1.py
'02- convertme.py.md'  '06- Glitch Cat.md'   codebook.txt         runme.py
'03- Codebook.md'      '07- PW Crack 1.md'   code.py
'04- fixme1.py.md'     '08- PW Crack 2.md'   convertme.py

┌──(kali㉿kali)-[~/…/RetosKali-exam--editar/CarpetaKali-exam/picoCTF/2022]
└─$ python fixme1.py
  File "/home/kali/Desktop/CarpetaCompartida.Windows/RetosKali-exam--editar/CarpetaKali-exam/picoCTF/2022/fixme1.py", line 20
    print('That is correct! Here\'s your flag: ' + flag)
IndentationError: unexpected indent

┌──(kali㉿kali)-[~/…/RetosKali-exam--editar/CarpetaKali-exam/picoCTF/2022]
└─$ cat fixme1.py 

import random



def str_xor(secret, key):
    #extend key to secret length
    new_key = key
    i = 0
    while len(new_key) < len(secret):
        new_key = new_key + key[i]
        i = (i + 1) % len(key)        
    return "".join([chr(ord(secret_c) ^ ord(new_key_c)) for (secret_c,new_key_c) in zip(secret,new_key)])


flag_enc = chr(0x15) + chr(0x07) + chr(0x08) + chr(0x06) + chr(0x27) + chr(0x21) + chr(0x23) + chr(0x15) + chr(0x5a) + chr(0x07) + chr(0x00) + chr(0x46) + chr(0x0b) + chr(0x1a) + chr(0x5a) + chr(0x1d) + chr(0x1d) + chr(0x2a) + chr(0x06) + chr(0x1c) + chr(0x5a) + chr(0x5c) + chr(0x55) + chr(0x40) + chr(0x3a) + chr(0x5f) + chr(0x53) + chr(0x5b) + chr(0x57) + chr(0x41) + chr(0x57) + chr(0x08) + chr(0x5c) + chr(0x14)

  
flag = str_xor(flag_enc, 'enkidu')
 print('That is correct! Here\'s your flag: ' + flag) 

┌──(kali㉿kali)-[~/…/RetosKali-exam--editar/CarpetaKali-exam/picoCTF/2022]
└─$ python fixme1.py
  File "/home/kali/Desktop/CarpetaCompartida.Windows/RetosKali-exam--editar/CarpetaKali-exam/picoCTF/2022/fixme1.py", line 20
    print('That is correct! Here\'s your flag: ' + flag)
IndentationError: unexpected indent

┌──(kali㉿kali)-[~/…/RetosKali-exam--editar/CarpetaKali-exam/picoCTF/2022]
└─$ nano fixme1.py  

┌──(kali㉿kali)-[~/…/RetosKali-exam--editar/CarpetaKali-exam/picoCTF/2022]
└─$ cat fixme1.py 

import random



def str_xor(secret, key):
    #extend key to secret length
    new_key = key
    i = 0
    while len(new_key) < len(secret):
        new_key = new_key + key[i]
        i = (i + 1) % len(key)        
    return "".join([chr(ord(secret_c) ^ ord(new_key_c)) for (secret_c,new_key_c) in zip(secret,new_key)])


flag_enc = chr(0x15) + chr(0x07) + chr(0x08) + chr(0x06) + chr(0x27) + chr(0x21) + chr(0x23) + chr(0x15) + chr(0x5a) + chr(0x07) + chr(0x00) + chr(0x46) + chr(0x0b) + chr(0x1a) + chr(0x5a) + chr(0x1d) + chr(0x1d) + chr(0x2a) + chr(0x06) + chr(0x1c) + chr(0x5a) + chr(0x5c) + chr(0x55) + chr(0x40) + chr(0x3a) + chr(0x5f) + chr(0x53) + chr(0x5b) + chr(0x57) + chr(0x41) + chr(0x57) + chr(0x08) + chr(0x5c) + chr(0x14)

  
flag = str_xor(flag_enc, 'enkidu')
print('That is correct! Here\'s your flag: ' + flag)

┌──(kali㉿kali)-[~/…/RetosKali-exam--editar/CarpetaKali-exam/picoCTF/2022]
└─$ python fixme1.py
That is correct! Here's your flag: picoCTF{1nd3nt1ty_cr1515_182342f7}

┌──(kali㉿kali)-[~/…/RetosKali-exam--editar/CarpetaKali-exam/picoCTF/2022]
└─$
```
picoCTF{1nd3nt1ty_cr1515_182342f7}

## Referencias
- []()