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
_Ou HEAD~2 para reverter os 2 últimos commits._   
**fonte: **[pt.stackoverflow](http://pt.stackoverflow.com/questions/3030/como-desfa%C3%A7o-o-%C3%BAltimo-commit-no-git)

- listar branch
```bash
git branch
```
