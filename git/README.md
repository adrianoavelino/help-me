# help-me
## Git
- Excluindo último commit, antes do push (enviar ao servidor)

```bash
git reset HEAD~1 --hard
```
> Se já tiver feito push, o melhor é "reverter" o ultimo commit, em vez de o desfazer. "Reverter", neste contexto, significa criar um commit novo que apague as linhas introduzidas/introduza as linhas apagadas no último commit.

```bash
git revert HEAD~1
```
_Obs:O HEAD~1 para reverter o último commit e `git revert HEAD~2` para remover os 2 úlitmos commits e assim por diante._    
***fonte: ***[pt.stackoverflow](http://pt.stackoverflow.com/questions/3030/como-desfa%C3%A7o-o-%C3%BAltimo-commit-no-git)

- listar branch
```bash
git branch
```

- adicionar arquivos commitados ao ***.gitignore   ***    
Quando um arquivo já foi commitado você precisa primeiramente remove-lo do tracking do git com o seguinte comando:
```sh
git rm --cached nomedoarquivo.extensao
```
Para esconder alterações em um arquivo, como arquivos de configuração de projeto, poderá utilizar o comando abaixo:
```sh
git update-index --assume-unchanged nomedoarquivo.extensao
```
***fonte: ***[odesenvolvedor.andafter.org](http://odesenvolvedor.andafter.org/publicacoes/como-ignorar-arquivos-no-git.html)

##Erro ao dar push
```sh
Receiving objects:  13% (1309/10065), 796.00 KiB | 6 KiB/s
fatal: The remote end hung up unexpectedly
```
Correção:
```sh
git config http.postBuffer 524288000
```

##Deletar branch remoto
```sh
git branch -d branch-name
git push origin :branch-name
```
***fonte***:[stackoverflow](http://stackoverflow.com/questions/15150671/delete-branches-in-bitbucket)
