# Php

- instalando xdebug
Instalando o xdebug no ubuntu
O que é Xdebug?

O Xdebug é uma extensão para ajudar no debuggin de scripts PHP, prove grande informações para debug.
Chega de :

```php
echo <pre>;    
print_r($var);
```
Para instalar o xdebug precisamos dos pacotes

- php5-dev    
- php-pear

vocês podem instalar os pacotes com o seguinte comando:

```bash
sudo apt-get install php5-dev php-pear
```

Acessem o terminal

Vamos utilizar a PECL para instalar o xdebug


```bash
pecl install xdebug
```
o xdebug vai estar instalado em :
```
/usr/lib/php5/<DATE+lfs>/xdebug.so
```
abram o arquivo php.ini que está em :

/etc/php5/cli/php.ini

adicionem as seguintes linhas:

zend_extension=/usr/lib/php5/<DATE+lfs>/xdebug.so

xdebug.remote_enable=on

xdebug.remote_handler=dbgp

xdebug.remote_host=localhost

xdebug.remote_port=9000

 fonte:[Blog Dexdev](http://blog.dexdev.com.br/desenvolvimento/125/instalando-o-xdebug-no-ubuntu/)
