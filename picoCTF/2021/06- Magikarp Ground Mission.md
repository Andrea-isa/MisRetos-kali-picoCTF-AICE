# Magikarp Ground Mission
## Objetivo  
Do you know how to move between directories and read files in the shell? Start the container, `ssh` to it, and then `ls` once connected to begin. Login via `ssh` as `ctf-player` with the password, `a13b7f9d`
## Solución  
Para poder conctarnos por medio de ssh, debemos precionar el botòn que que die "Launch Instance" para iniciar una instancias de una hora para poder encontrar la flag, al presionar el botòn se inicia el conteo, ademàs de que nos da la direcciòn de ssh para que podamos acceder al usuario `ctf-player`, nos pedirà la contraseña, la cual se encuentra en la descripciòn del reto. Al acceder se nos menciona que podemos encontrar las tres partes en las que está dividida la flag, navegando atraves de los directorios de forma en se muestra a continuaciòn:
```shell
┌──(kali㉿kali)-[~]
└─$ ssh ctf-player@venus.picoctf.net -p 57629
The authenticity of host '[venus.picoctf.net]:57629 ([3.131.124.143]:57629)' can't be established.
ED25519 key fingerprint is SHA256:P1f6h95BrSVnJbm2AKhphfHHGEyAeThib/rN/AwKs24.
This key is not known by any other names
Are you sure you want to continue connecting (yes/no/[fingerprint])? yes
Warning: Permanently added '[venus.picoctf.net]:57629' (ED25519) to the list of known hosts.
ctf-player@venus.picoctf.net's password: 
Permission denied, please try again.
ctf-player@venus.picoctf.net's password: 
Welcome to Ubuntu 18.04.5 LTS (GNU/Linux 5.4.0-1041-aws x86_64)

 * Documentation:  https://help.ubuntu.com
 * Management:     https://landscape.canonical.com
 * Support:        https://ubuntu.com/advantage
This system has been minimized by removing packages and content that are
not required on a system that users do not log into.

To restore this content, you can run the 'unminimize' command.

The programs included with the Ubuntu system are free software;
the exact distribution terms for each program are described in the
individual files in /usr/share/doc/*/copyright.

Ubuntu comes with ABSOLUTELY NO WARRANTY, to the extent permitted by
applicable law.

ctf-player@pico-chall$ ls
1of3.flag.txt  instructions-to-2of3.txt
ctf-player@pico-chall$ cat 1of3.flag.txt
picoCTF{xxsh_
ctf-player@pico-chall$ cat instructions-to-2of3.txt
Next, go to the root of all things, more succinctly `/`
ctf-player@pico-chall$ cd ..
ctf-player@pico-chall$ ls
3of3.flag.txt  drop-in
ctf-player@pico-chall$ cat 3of3.flag.txt
71be5264}
ctf-player@pico-chall$ cd ..
ctf-player@pico-chall$ ls
ctf-player
ctf-player@pico-chall$ cd..
-bash: cd..: command not found
ctf-player@pico-chall$ ls
ctf-player
ctf-player@pico-chall$ cd ..
ctf-player@pico-chall$ ls
2of3.flag.txt  dev   instructions-to-3of3.txt  media  proc  sbin  tmp
bin            etc   lib                       mnt    root  srv   usr
boot           home  lib64                     opt    run   sys   var
ctf-player@pico-chall$ cat 2of3.flag.txt
0ut_0f_\/\/4t3r_
ctf-player@pico-chall$ ^C
ctf-player@pico-chall$ ^C
ctf-player@pico-chall$ Connection to venus.picoctf.net closed by remote host.
Connection to venus.picoctf.net closed.

┌──(kali㉿kali)-[~]
└─$

```
La flag se ordena de la siguiente manera:
picoCTF{xxsh_0ut_0f_`\`/`\`/4t3r_71be5264}-->sin las comillas de las diagonales invertidas.


## Referencias
- []()