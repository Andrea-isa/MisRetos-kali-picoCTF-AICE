# PW Crack 1
## Objetivo  
Can you crack the password to get the flag? Download the password checker [here](https://artifacts.picoctf.net/c/52/level1.py) and you'll need the encrypted [flag](https://artifacts.picoctf.net/c/52/level1.flag.txt.enc) in the same directory too.
## Solución  
Vemos el archivo .py descargado con `cat` y analizamos en còdigo, vemos que si es ejecutado nos va a pedir una contraseña, por lo que debemos ver cual es la contraseña,  se encuentra en una de las lìneas del còdigo, la guardamos, ejecutamos el archivo con `python`, ingresamos la contraseña e inmediatamente nos da la flag para este reto.

```shell
┌──(kali㉿kali)-[~/…/RetosKali-exam--editar/CarpetaKali-exam/picoCTF/2022]
└─$ ls
'01- runme.py.md'      '06- Glitch Cat.md'   code.py               level1.py
'02- convertme.py.md'  '07- PW Crack 1.md'   convertme.py          runme.py
'03- Codebook.md'      '08- PW Crack 2.md'   fixme1.py
'04- fixme1.py.md'     '09- PW Crack 3.md'   fixme2.py
'05- fixme2.py.md'      codebook.txt         level1.flag.txt.enc
┌──(kali㉿kali)-[~/…/RetosKali-exam--editar/CarpetaKali-exam/picoCTF/2022]
└─$ python level1.py
Please enter correct password for flag: s
That password is incorrect
   
┌──(kali㉿kali)-[~/…/RetosKali-exam--editar/CarpetaKali-exam/picoCTF/2022]
└─$ cat level1.py
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


flag_enc = open('level1.flag.txt.enc', 'rb').read()



def level_1_pw_check():
    user_pw = input("Please enter correct password for flag: ")
    if( user_pw == "1e1a"):
        print("Welcome back... your flag, user:")
        decryption = str_xor(flag_enc.decode(), user_pw)
        print(decryption)
        return
    print("That password is incorrect")



level_1_pw_check()

┌──(kali㉿kali)-[~/…/RetosKali-exam--editar/CarpetaKali-exam/picoCTF/2022]
└─$ cat level1.flag.txt.enc
A
 Rr1w▒Q nVT_nPRVW▒                                                                                                                                                                       
┌──(kali㉿kali)-[~/…/RetosKali-exam--editar/CarpetaKali-exam/picoCTF/2022]
└─$ python level1.py                                                                                                                           
Please enter correct password for flag: 1e1a
Welcome back... your flag, user:
picoCTF{545h_r1ng1ng_fa343060}

┌──(kali㉿kali)-[~/…/RetosKali-exam--editar/CarpetaKali-exam/picoCTF/2022]
└─$ 
```
picoCTF{545h_r1ng1ng_fa343060}

## Referencias
- []()