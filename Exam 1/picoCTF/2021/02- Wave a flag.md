# Wave a flag
## Objetivo  
Can you invoke help flags for a tool or binary? [This program](https://mercury.picoctf.net/static/f95b1ee9f29d631d99073e34703a2826/warm) has extraordinarily helpful information...
## Solución  
Segùn las pistas de este reto, podemos usar el comando `./` màs el nombre del archivo que descargamos y luego `-h`para poder ver la flag màs claramente.
```shell
┌──(kali㉿kali)-[~/…/RetosKali-exam--editar/CarpetaKali-exam/picoCTF/2021]
└─$ ./warm -h                 
Oh, help? I actually don't do much, but I do have this flag here: picoCTF{b1scu1ts_4nd_gr4vy_f0668f62}

┌──(kali㉿kali)-[~/…/RetosKali-exam--editar/CarpetaKali-exam/picoCTF/2021]
└─$ 

```
picoCTF{}

## Referencias
- []()