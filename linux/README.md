# Linux

## Converter DVD (iso) para mkv
- instalar o HandBrake pela Central de Programas

## Recuperar senha de root
Erro: 
```
$ passwd
Changing password for rinzwind.
(current) UNIX password: 
passwd: Authentication token manipulation error
passwd: password unchanged
```
Esse erro normalmente ocorre quando existe uma entrada no /etc/passwd, mas não existe no /etc/passwd (ou esse arquivo não existe).
pwconv recria o arquivo.   
font: [askubuntu](http://askubuntu.com/questions/57620/getting-an-authentication-token-manipulation-error-when-trying-to-change-my-us)
