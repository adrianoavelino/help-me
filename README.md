# help-me
Conteúdos de ajudas do cotidiano

- [node](./node)
- [disqus](#)
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
Problemas com maven exclua ~/.m2

#github
Erro ao dar clone após adicionar ssh-keygen
`ssh-add ~/.ssh/id_rsa`
