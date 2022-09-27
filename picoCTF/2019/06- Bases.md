# Bases
## Objetivo  
What does this `bDNhcm5fdGgzX3IwcDM1` mean? I think it has something to do with bases.
## Solución  
```shell
┌──(kali㉿kali)-[~]
└─$ echo "bDNhcm5fdGgzX3IwcDM1" | base64 -d
l3arn_th3_r0p35                                                                                      
┌──(kali㉿kali)-[~]
└─$ 
```
picoCTF{l3arn_th3_r0p35}

## Referencias
- [Conversiòn en CyberChef](https://gchq.github.io/CyberChef/#recipe=From_Base64('A-Za-z0-9%2B/%3D',true)&input=YkROaGNtNWZkR2d6WDNJd2NETTE)