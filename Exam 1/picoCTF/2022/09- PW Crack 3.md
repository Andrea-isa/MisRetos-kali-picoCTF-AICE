# PW Crack 3
## Objetivo  
Can you crack the password to get the flag? Download the password checker [here](https://artifacts.picoctf.net/c/23/level3.py) and you'll need the encrypted [flag](https://artifacts.picoctf.net/c/23/level3.flag.txt.enc) and the [hash](https://artifacts.picoctf.net/c/23/level3.hash.bin) in the same directory too. There are 7 potential passwords with 1 being correct. You can find these by examining the password checker script.
## Solución  
Es casi similar a PW Crack 1 y PW Crack 2, sòlo hay que analizar el còdigo al hacer un `cat`, podemos ver que en las ùltimas lìneas viene 7 contraseñas, y una de ellas es la correcta, asì que debemos ingresar cada una de ellas hasta que nos de la flag, es decir, si encontramos cual es la correcta, se ingresa directamente y de inmediato nos da la flag.
```shell
┌──(kali㉿kali)-[~/…/RetosKali-exam--editar/CarpetaKali-exam/picoCTF/2022]
└─$ ls           
'01- runme.py.md'      '04- fixme1.py.md'   '07- PW Crack 1.md'   codebook.txt   fixme1.py             level1.py             level3.flag.txt.enc   runme.py
'02- convertme.py.md'  '05- fixme2.py.md'   '08- PW Crack 2.md'   code.py        fixme2.py             level2.flag.txt.enc   level3.hash.bin
'03- Codebook.md'      '06- Glitch Cat.md'  '09- PW Crack 3.md'   convertme.py   level1.flag.txt.enc   level2.py             level3.py

┌──(kali㉿kali)-[~/…/RetosKali-exam--editar/CarpetaKali-exam/picoCTF/2022]
└─$ cat level3.py
import hashlib

### THIS FUNCTION WILL NOT HELP YOU FIND THE FLAG --LT ########################
def str_xor(secret, key):
    #extend key to secret length
    new_key = key
    i = 0
    while len(new_key) < len(secret):
        new_key = new_key + key[i]
        i = (i + 1) % len(key)        
    return "".join([chr(ord(secret_c) ^ ord(new_key_c)) for (secret_c,new_key_c) in zip(secret,new_key)])
###############################################################################

flag_enc = open('level3.flag.txt.enc', 'rb').read()
correct_pw_hash = open('level3.hash.bin', 'rb').read()


def hash_pw(pw_str):
    pw_bytes = bytearray()
    pw_bytes.extend(pw_str.encode())
    m = hashlib.md5()
    m.update(pw_bytes)
    return m.digest()


def level_3_pw_check():
    user_pw = input("Please enter correct password for flag: ")
    user_pw_hash = hash_pw(user_pw)
    
    if( user_pw_hash == correct_pw_hash ):
        print("Welcome back... your flag, user:")
        decryption = str_xor(flag_enc.decode(), user_pw)
        print(decryption)
        return
    print("That password is incorrect")



level_3_pw_check()


# The strings below are 7 possibilities for the correct password. 
#   (Only 1 is correct)
pos_pw_list = ["6997", "3ac8", "f0ac", "4b17", "ec27", "4e66", "865e"]

 
┌──(kali㉿kali)-[~/…/RetosKali-exam--editar/CarpetaKali-exam/picoCTF/2022]
└─$ python level3.py
Please enter correct password for flag: 6997
That password is incorrect

┌──(kali㉿kali)-[~/…/RetosKali-exam--editar/CarpetaKali-exam/picoCTF/2022]
└─$ python level3.py
Please enter correct password for flag: 3ac8
That password is incorrect

┌──(kali㉿kali)-[~/…/RetosKali-exam--editar/CarpetaKali-exam/picoCTF/2022]
└─$ python level3.py
Please enter correct password for flag: f0ac
That password is incorrect

┌──(kali㉿kali)-[~/…/RetosKali-exam--editar/CarpetaKali-exam/picoCTF/2022]
└─$ python level3.py
Please enter correct password for flag: 4b17
Welcome back... your flag, user:
picoCTF{m45h_fl1ng1ng_2b072a90}
 
┌──(kali㉿kali)-[~/…/RetosKali-exam--editar/CarpetaKali-exam/picoCTF/2022]
└─$
```
picoCTF{m45h_fl1ng1ng_2b072a90}

## Referencias
- []()