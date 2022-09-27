# PW Crack 2
## Objetivo  
Can you crack the password to get the flag? Download the password checker [here](https://artifacts.picoctf.net/c/18/level2.py) and you'll need the encrypted [flag](https://artifacts.picoctf.net/c/18/level2.flag.txt.enc) in the same directory too.
## Solución  
Este reto tiene una soluciòn similar al PW CRACK 1, sòlo que en este la contraseña son caracteres ASCII, abrimos python y le decimos que nos imprima con un `print`, y nos da la contraseña directamente. Ingresamos la contraseña y nos da la flag.
```shell
┌──(kali㉿kali)-[~/…/RetosKali-exam--editar/CarpetaKali-exam/picoCTF/2022]
└─$ ls
'01- runme.py.md'      '04- fixme1.py.md'   '07- PW Crack 1.md'   codebook.txt   fixme1.py             level1.py             runme.py
'02- convertme.py.md'  '05- fixme2.py.md'   '08- PW Crack 2.md'   code.py        fixme2.py             level2.flag.txt.enc
'03- Codebook.md'      '06- Glitch Cat.md'  '09- PW Crack 3.md'   convertme.py   level1.flag.txt.enc   level2.py

┌──(kali㉿kali)-[~/…/RetosKali-exam--editar/CarpetaKali-exam/picoCTF/2022]
└─$ python level2.py
Please enter correct password for flag: s
That password is incorrect

┌──(kali㉿kali)-[~/…/RetosKali-exam--editar/CarpetaKali-exam/picoCTF/2022]
└─$ cat level2.flag.txt.enc
CP
pm%GKWP[fVT]^R
              TfVU\Q\    
 
┌──(kali㉿kali)-[~/…/RetosKali-exam--editar/CarpetaKali-exam/picoCTF/2022]
└─$ cat level2.py          
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

flag_enc = open('level2.flag.txt.enc', 'rb').read()



def level_2_pw_check():
    user_pw = input("Please enter correct password for flag: ")
    if( user_pw == chr(0x33) + chr(0x39) + chr(0x63) + chr(0x65) ):
        print("Welcome back... your flag, user:")
        decryption = str_xor(flag_enc.decode(), user_pw)
        print(decryption)
        return
    print("That password is incorrect")



level_2_pw_check()

┌──(kali㉿kali)-[~/…/RetosKali-exam--editar/CarpetaKali-exam/picoCTF/2022]
└─$ python          
Python 3.10.5 (main, Jun  8 2022, 09:26:22) [GCC 11.3.0] on linux
Type "help", "copyright", "credits" or "license" for more information.
>>> print(chr(0x33) + chr(0x39) + chr(0x63) + chr(0x65))
39ce
>>> exit()

┌──(kali㉿kali)-[~/…/RetosKali-exam--editar/CarpetaKali-exam/picoCTF/2022]
└─$ python level2.py
Please enter correct password for flag: 39ce
Welcome back... your flag, user:
picoCTF{tr45h_51ng1ng_502ec42e}

┌──(kali㉿kali)-[~/…/RetosKali-exam--editar/CarpetaKali-exam/picoCTF/2022]
└─$
```
picoCTF{tr45h_51ng1ng_502ec42e}

## Referencias
- []()