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

fazendo um teste com c9
