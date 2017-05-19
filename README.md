# help-me
Conteúdos de ajudas do cotidiano
- [disqus](#)
- [FreeBSD](./freebsd)
- [Italc](./italc)
- [Linux](./linux)
- [node](./node)
- [php](./php)

Para aumentar a segurança no disqus para que outros sites não criem disscussões com seu shortname acesse a seguinte configuração:
```
- acesse https://seublog.disqus.com/admin/settings/
- Disqus admin > Settings > Advanced.
No campo Trusted Domains: adicione o dominio do seu blog
Ex: nomdedosite.com.br
```
Fonte: https://help.disqus.com/customer/portal/articles/1261429


C:\xampp\htdocs\hexo\aaa\teste\_config.yml
disqus_shortname: adrianoavelinoblog

<% if (page.title){ %>
  var disqus_title = '<%=page.title%>';
<% } %>

#testar Boot pendrive no vbox

```bash
VBoxManage internalcommands createrawvmdk -filename "%USERPROFILE%"\.VirtualBox\usb.vmdk -rawdisk \\.\PhysicalDrive#
```
substitua # pelo disco do pendrive em diskmgmt.msc



#Java
1- Problemas com maven exclua ~/.m2

-2
```
The superclass “javax.servlet.http.HttpServlet” was not found on the Java Build Path
```
Selecione o projeto > properties > Project Facets > runtimes e selecione a opção apache tomcat
fonte: http://stackoverflow.com/questions/22756153/the-superclass-javax-servlet-http-httpservlet-was-not-found-on-the-java-build


#github
Erro ao dar clone após adicionar ssh-keygen
`ssh-add ~/.ssh/id_rsa`

#ativar varias áreas de trabalho no Elementary OS (após atualização)
sudo apt-get install docnf-editor

conf -> org.gnome.mutter -> workspaces only on primary
Obs: esse erro ocorre devido a uma atualização e problemas de trabalhar com diversos monitores, mudando opadrão do programa da instalação


#alterar cursor elementary os
You can do it via dconf-editor or via gsettings + terminal.

Open terminal and type in following:

# gsettings set org.pantheon.terminal.settings cursor-shape 'I-Beam'
To rollback run following:

# gsettings set org.pantheon.terminal.settings cursor-shape 'Block'
Open dconf-editor and navigate to org.pantheon.terminal.settings, open cursor-shape and set it to I-Beam.


# desinstalar netbeans
```
cd /usr/local/netbeansx.x.x
sh uninstall.sh 
```
font: [viva o linux](https://www.vivaolinux.com.br/dica/Como-desinstalar-NetBeans)


# backup de banco no mysql com mysqldump
```
 mysqldump -u <usuario> -p<senha> mysql > mysql.sql
```    
font: [devmedia](http://www.devmedia.com.br/backup-no-mysql-com-mysqldump-parte-1/7483)

# Configuração de powerline font no putty windows
So, here is what I did to make it work:
Follow the installation instructions for powerline
Download and install the DejaVu font in Windows.  Some of the other fonts in the site worked, and others didn't.  PuTTY seems to be picky on what fonts it will use, and the DejaVu font is a nice looking mono-spaced font, so it is a good starting point.
(Re)run PuTTY and create a new session with the following settings
Window-Appearance-Font = DejaVu Sans Mono for Powerline
Window-Appearance-Font Quality = ClearType 
Window-Translation-Character Set = UTF-8
Verify your linux locale LANG=en_US.UTF-8  (mine was out of the box)
Verify that your .vimrc has "set encoding=utf-8"
Verify your term session is capable of 256 colors (TERM=xterm-256color)

font: http://pdalinis.blogspot.com.br/2013/08/putty-powerline.html
