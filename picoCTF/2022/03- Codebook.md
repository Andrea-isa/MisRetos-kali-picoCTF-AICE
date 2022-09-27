# Codebook
## Objetivo  
Run the Python script `code.py` in the same directory as `codebook.txt`.

-   [Download code.py](https://artifacts.picoctf.net/c/102/code.py)
-   [Download codebook.txt](https://artifacts.picoctf.net/c/102/codebook.txt)

---
## Solución  
Se deben descargar los dos archivos, luego desde la consola vamos a la carpeta donde los guardamos y ambos los analizamos con `cat`, vemos que el que està màs detallado es el code.py, por lo que lo ejecutamos con `python` y nos da la flag.
```shell
┌──(kali㉿kali)-[~/…/RetosKali-exam--editar/CarpetaKali-exam/picoCTF/2022]
└─$ ls        
'01- runme.py.md'      '05- fixme2.py.md'   '09- PW Crack 3.md'   runme.py
'02- convertme.py.md'  '06- Glitch Cat.md'   codebook.txt
'03- Codebook.md'      '07- PW Crack 1.md'   code.py
'04- fixme1.py.md'     '08- PW Crack 2.md'   convertme.py

┌──(kali㉿kali)-[~/…/RetosKali-exam--editar/CarpetaKali-exam/picoCTF/2022]
└─$ cat codebook.txt
azbycxdwevfugthsirjqkplomn

┌──(kali㉿kali)-[~/…/RetosKali-exam--editar/CarpetaKali-exam/picoCTF/2022]
└─$ cat code.py     

import random
import sys



def str_xor(secret, key):
    #extend key to secret length
    new_key = key
    i = 0
    while len(new_key) < len(secret):
        new_key = new_key + key[i]
        i = (i + 1) % len(key)        
    return "".join([chr(ord(secret_c) ^ ord(new_key_c)) for (secret_c,new_key_c) in zip(secret,new_key)])


flag_enc = chr(0x13) + chr(0x01) + chr(0x17) + chr(0x07) + chr(0x2c) + chr(0x3a) + chr(0x2f) + chr(0x1a) + chr(0x0d) + chr(0x53) + chr(0x0c) + chr(0x47) + chr(0x0a) + chr(0x5f) + chr(0x5e) + chr(0x02) + chr(0x3e) + chr(0x5a) + chr(0x56) + chr(0x5d) + chr(0x45) + chr(0x5d) + chr(0x58) + chr(0x31) + chr(0x58) + chr(0x58) + chr(0x59) + chr(0x02) + chr(0x51) + chr(0x4c) + chr(0x5a) + chr(0x0c) + chr(0x13)



def print_flag():
  try:
    codebook = open('codebook.txt', 'r').read()
    
    password = codebook[4] + codebook[14] + codebook[13] + codebook[14] +\
               codebook[23]+ codebook[25] + codebook[16] + codebook[0]  +\
               codebook[25]
               
    flag = str_xor(flag_enc, password)
    print(flag)
  except FileNotFoundError:
    print('Couldn\'t find codebook.txt. Did you download that file into the same directory as this script?')



def main():
  print_flag()



if __name__ == "__main__":
  main()

┌──(kali㉿kali)-[~/…/RetosKali-exam--editar/CarpetaKali-exam/picoCTF/2022]
└─$ python code.py  
picoCTF{c0d3b00k_455157_197a982c}

┌──(kali㉿kali)-[~/…/RetosKali-exam--editar/CarpetaKali-exam/picoCTF/2022]
└─$ 
```
picoCTF{c0d3b00k_455157_197a982c}

## Referencias
- []()