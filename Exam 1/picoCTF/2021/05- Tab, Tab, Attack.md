# Tab, Tab, Attack
## Objetivo  
Using tabcomplete in the Terminal will add years to your life, esp. when dealing with long rambling directory structures and filenames: [Addadshashanammu.zip](https://mercury.picoctf.net/static/9689f2b453ad5daeb73ca7534e4d1521/Addadshashanammu.zip)
## Solución  
Dscargamos el zip que nos da el reto, lo descomprimimos desde la consola, entramos hasta el final de las carpteas que contiene, encontramos un archivo el cual contiene la flag, ese le hacemos `./` para que nos la muestre.
```shell
┌──(kali㉿kali)-[~/…/RetosKali-exam--editar/CarpetaKali-exam/picoCTF/2021]
└─$ ls -la
total 58
drwxrwx--- 1 root vboxsf  4096 Sep 25 22:56  .
drwxrwx--- 1 root vboxsf     0 Sep 25 22:56  ..
-rwxrwx--- 1 root vboxsf   987 Sep 25 22:09 '01- Obedient Cat.md'
-rwxrwx--- 1 root vboxsf   741 Sep 25 22:23 '02- Wave a flag.md'
-rwxrwx--- 1 root vboxsf  1209 Sep 25 22:43 '03- Nice netcat....md'
-rwxrwx--- 1 root vboxsf  1825 Sep 25 22:54 "04- Static ain't always noise.md"
-rwxrwx--- 1 root vboxsf   342 Sep 25 22:11 '05- Tab, Tab, Attack.md'
-rwxrwx--- 1 root vboxsf   308 Sep 25 22:12 '06- Magikarp Ground Mission.md'
-rwxrwx--- 1 root vboxsf  4519 Sep 25 22:55  Addadshashanammu.zip
-rwxrwx--- 1 root vboxsf    34 Sep 25 22:01  flag
-rwxrwx--- 1 root vboxsf   785 Sep 25 22:45  ltdis.sh
-rwxrwx--- 1 root vboxsf     0 Sep 25 22:49  .ltdis.x86_64.txt
-rwxrwx--- 1 root vboxsf  8376 Sep 25 22:44  static
-rwxrwx--- 1 root vboxsf 10936 Sep 25 22:15  warm

┌──(kali㉿kali)-[~/…/RetosKali-exam--editar/CarpetaKali-exam/picoCTF/2021]
└─$ unzip Addadshashanammu.zip
Archive:  Addadshashanammu.zip
   creating: Addadshashanammu/
   creating: Addadshashanammu/Almurbalarammi/
   creating: Addadshashanammu/Almurbalarammi/Ashalmimilkala/
   creating: Addadshashanammu/Almurbalarammi/Ashalmimilkala/Assurnabitashpi/
   creating: Addadshashanammu/Almurbalarammi/Ashalmimilkala/Assurnabitashpi/Maelkashishi/
   creating: Addadshashanammu/Almurbalarammi/Ashalmimilkala/Assurnabitashpi/Maelkashishi/Onnissiralis/
   creating: Addadshashanammu/Almurbalarammi/Ashalmimilkala/Assurnabitashpi/Maelkashishi/Onnissiralis/Ularradallaku/
  inflating: Addadshashanammu/Almurbalarammi/Ashalmimilkala/Assurnabitashpi/Maelkashishi/Onnissiralis/Ularradallaku/fang-of-haynekhtnamet  

┌──(kali㉿kali)-[~/…/RetosKali-exam--editar/CarpetaKali-exam/picoCTF/2021]
└─$ cd Addadshashanammu/Almurbalarammi/Ashalmimilkala/Assurnabitashpi/Maelkashishi/Onnissiralis/Ularradallaku/  

┌──(kali㉿kali)-[~/…/Assurnabitashpi/Maelkashishi/Onnissiralis/Ularradallaku]
└─$ ls -la
total 12
drwxrwx--- 1 root vboxsf    0 Mar 15  2021 .
drwxrwx--- 1 root vboxsf    0 Mar 15  2021 ..
-rwxrwx--- 1 root vboxsf 8320 Mar 15  2021 fang-of-haynekhtnamet

┌──(kali㉿kali)-[~/…/Assurnabitashpi/Maelkashishi/Onnissiralis/Ularradallaku]
└─$ ./fang-of-haynekhtnamet
*ZAP!* picoCTF{l3v3l_up!_t4k3_4_r35t!_2bcfb2ab}

┌──(kali㉿kali)-[~/…/Assurnabitashpi/Maelkashishi/Onnissiralis/Ularradallaku]
└─$
```
picoCTF{l3v3l_up!_t4k3_4_r35t!_2bcfb2ab}

## Referencias
- []()