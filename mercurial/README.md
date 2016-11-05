# Mercurial
`hg init` - inicia o controle de versão    
`hg add *` - adiciona todos os arquivos para o controle de versão    
`hg commit -m "mensagem de commit"` - Commita as alterações    
`hg status ou hg st` - verifica se há alterações no controle de versão    
`hg log` - exibe o log    
`hg log --limit x` - exibe os últimos x log, onde x é a quanntidade de logs a ser exibido    
`hg parents` - exibe o seu o changeset id atual de seu log'    
`hg update -r x` - altera de changeset id, onde `x` é o id do changeset, obtido através do comando `hg log`   
`hg update` - volta para o último changeset    
`hg tip` - exibe o último changeset
`hg log -r REV -p` - (semelhante ao git show) exibe o log de um changeset específico, onde o `REV` é o id do changeset    
`hg strip --keep -r .` - remove seu último commit, mas não perde as suas alterações (git reset --soft qwhdhshrefsgal)  [fonte](http://www.google.com)    

## Strip
É uma extensão que habilita o uso da funionalidade `git reset --soft iddocommitwweerewddfgv`.
Para habilitar adicione a seguite linha ho seu arquivo `~/.hgrc`.    
```sh
[extensions]
strip =
```
