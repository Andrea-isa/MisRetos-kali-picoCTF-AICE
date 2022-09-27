# Nice netcat...
## Objetivo  
There is a nice program that you can talk to by using this command in a shell: `$ nc mercury.picoctf.net 21135`, but it doesn't speak English...
## Solución  
Al momento de introducir el comando que se nos da en la descripciòn de este reto nos regresa un còdigo que podemos descifrar en la plataforma CyberChef, y asì obteneos la flag.
```shell
┌──(kali㉿kali)-[~/…/RetosKali-exam--editar/CarpetaKali-exam/picoCTF/2021]
└─$ nc mercury.picoctf.net 21135 
112 
105 
99 
111 
67 
84 
70 
123 
103 
48 
48 
100 
95 
107 
49 
116 
116 
121 
33 
95 
110 
49 
99 
51 
95 
107 
49 
116 
116 
121 
33 
95 
97 
102 
100 
53 
102 
100 
97 
52 
125 
10 

┌──(kali㉿kali)-[~/…/RetosKali-exam--editar/CarpetaKali-exam/picoCTF/2021]
└─$ 

```
picoCTF{g00d_k1tty!_n1c3_k1tty!_afd5fda4}

## Referencias
- [CyberChef de la flag de este reto](https://gchq.github.io/CyberChef/#recipe=From_Charcode('Space',10)&input=MTEyIAoxMDUgCjk5IAoxMTEgCjY3IAo4NCAKNzAgCjEyMyAKMTAzIAo0OCAKNDggCjEwMCAKOTUgCjEwNyAKNDkgCjExNiAKMTE2IAoxMjEgCjMzIAo5NSAKMTEwIAo0OSAKOTkgCjUxIAo5NSAKMTA3IAo0OSAKMTE2IAoxMTYgCjEyMSAKMzMgCjk1IAo5NyAKMTAyIAoxMDAgCjUzIAoxMDIgCjEwMCAKOTcgCjUyIAoxMjUgCjEwIA)