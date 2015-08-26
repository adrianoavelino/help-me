# help-me
Conteúdos de ajudas do cotidiano
- [disqus](#)
- [FreeBSD](./freebsd)
- [Italc](./italc)
- [node](./node)

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

#ativar varias áreas de trabalho
sudo apt-get install docnf-ediitor

conf -> org.gnome.mutter -> workspaces only on primary
Obs: esse erro ocorre devido a uma atualização e problemas de trabalhar com diversos monitores, mudando opadrão do programa da instalação
