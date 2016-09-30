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

## Erro ao instalar java
Erro: 
```
Important!!! For now, you should continue to use Java 8 because Oracle Java 9 is available as an early access release (it should be released in 2016)! You should only use Oracle Java 9 if you explicitly need it, because it may contain bugs and it might not include the latest security patches! Also, some Java options were removed in JDK9, so you may encounter issues with various Java apps. More information and installation instructions (Ubuntu / Linux Mint / Debian): http://www.webupd8.org/2015/02/install-oracle-java-9-in-ubuntu-linux.html
```

Correção:
```
sudo add-apt-repository ppa:webupd8team/java
sudo apt-get update
sudo apt-get install oracle-java8-installer
```

fonte: [http://www.webupd8.org/2012/09/install-oracle-java-8-in-ubuntu-via-ppa.html](http://www.webupd8.org/2012/09/install-oracle-java-8-in-ubuntu-via-ppa.html)

#usuário do FTP (Proftpd) visualiza hierarquia dos diretórios
```sh
vim /etc/proftpd/proftpd.conf 
```
altere a linha `#DefaultRoot ` para: `DefaultRoot ~`    
```sh
/etc/init.d/proftpd restart
```
fonte:[vivaolinux](https://www.vivaolinux.com.br/dica/ProFTPD-Enjaulando-usuarios-no-diretorio-HOME/)

