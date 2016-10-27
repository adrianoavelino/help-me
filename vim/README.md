# Vim

`i` -  entra no modo de inserção antes do cursor
`I` - entra no modo de inserção no início da linha de conteúdo digitado

## Basic
`ZZ` - fecha e salva o arquivo atual    
`:wq` - fecha e salva arquivo atual
`ctrl-n` - autocomplete padrão
`nG` - vai para linha de número `n`. Ex: `10G`
`0` - vai para o início da linha
`$` - vai para o início da linha
`o` - cria uma linha abaixo
`O` - cria uma linha acima
`y` - copia texto selecionado
`p` -  cola texto selecionado
`:ls` - lista os arquivos abertos (buffer), onde os números são as referencias para serem abertos
`:bn` - abre o buffer de n�mero `n`
`H` - vai para o topo da tela
`M` - vai para o meio da tela
`L` - vai para o final da tela


## Movimentação entre janelas
`Ctrl-W` + setas ou (hjjkl) - mudo a janela em foco    
`Ctrl-W + SHIFT` + setas ou (hjjkl) - muda a janela para cima, baixo ou pros lados        


## Plugins

### NERDTree
`:NERDTree` - abre o NERDTree   
`cd` - entra no diretorio selecionado    
`:Bookmark nomedobookmark`   - cria um favorito da pasta selecionada    
`B` - abre os favoritos
`ctrl-ww` - altera entre as janelas    
`:pwd` - retorna o caminho do diret�rio atual

### Emmet

### vim-airline
Instalação via pathogen:
```
cd ~/vimfiles/bundle
git clone https://github.com/iamcco/markdown-preview.vim.git
```
Altere o arquivo `~\vimfiles\bundle\markdown-preview.vim\plugin\mkdp.vim` e adicione a seguinte linha:
```
    let g:mkdp_path_to_chrome = 'C:\Program Files (x86)\Google\Chrome\Application\chrome.exe'
```
onde `'C:\Program Files (x86)\Google\Chrome\Application\chrome.exe'` é o caminho absoluto do seu navegador, no meu caso estou usando o Google Chrome para Windows :(

## Dicas
Configurar vim para abrir arquivo com codificação utf-8, acrescente a seguinte linha no seu ~/.vimrc:
```
  set fileencodings=utf8
```
ou
```
:e! ++enc=utf8
```
e para salvar como utf-8
```
:w ++enc=utf-8
```

fonte: [stackoverflow](http://stackoverflow.com/questions/5166652/how-to-view-utf-8-characters-in-vim-or-gvim) e  [gustavopaes.net](https://gustavopaes.net/blog/2011/salvar-arquivos-em-utf-8-no-vim.html)
