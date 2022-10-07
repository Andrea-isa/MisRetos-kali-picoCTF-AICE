# convertme.py 
## Objetivo  
Run the Python script and convert the given number from decimal to binary to get the flag. [Download Python script](https://artifacts.picoctf.net/c/31/convertme.py)
## Solución  
Vamos a la carpeta donde guardamos el archivo .py descargado desde la descripciòn de este reto y lo ejecutamos en la consola con el comando `python`, despuès nos pedira convertir un nùmero aleatorio, de decimal a binario, si ingresamos el binario correcto nos darà la flag.
```shell
┌──(kali㉿kali)-[~/…/RetosKali-exam--editar/CarpetaKali-exam/picoCTF/2022]
└─$ python convertme.py
If 56 is in decimal base, what is it in binary base?
Answer: 111000
That is correct! Here's your flag: picoCTF{4ll_y0ur_b4535_9c3b7d4d}

┌──(kali㉿kali)-[~/…/RetosKali-exam--editar/CarpetaKali-exam/picoCTF/2022]
└─$
```
picoCTF{4ll_y0ur_b4535_9c3b7d4d}

## Referencias
- [Conversiòn en CyberChef](https://gchq.github.io/CyberChef/#recipe=From_Decimal('Space',false)To_Binary('Space',6)&input=NTY)