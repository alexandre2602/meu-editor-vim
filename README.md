## Configurações que uso no meu editor VIM

As configurações que utilizo no VIM me ajudam a trabalhar com demandas relacionadas a SysOps/DevOps.

**01. Instalação do gerenciador de plugins.**

O [vim-plug](https://github.com/junegunn/vim-plug), que nada mais é que um gerenciador de plugins bem simples e eficiente, me permite instalar, remover e atualizar todos os plugins utilizados no vim.

Para instalar só preciso executar o comando abaixo.
```bash
curl -fLo ~/.vim/autoload/plug.vim --create-dirs https://raw.githubusercontent.com/junegunn/vim-plug/master/plug.vim
```

**02. Arquivos de configuração.**

Para configurar os comportamentos do vim gosto de utilizar um arquivo secundário ao ```/etc/vimrc``` que irá ser válido apenas para o meu usuário. Só preciso criar o arquivo ```~/.vimrc``` e inserir o conteúdo abaixo.

```
call plug#begin()

Plug 'scrooloose/nerdtree'
Plug 'vim-airline/vim-airline'
Plug 'vim-airline/vim-airline-themes'
Plug 'stephpy/vim-yaml'

call plug#end()

" Keybind NERDTree
map <F2> :NERDTreeToggle<CR>

" VIM Airline Theme
let g:airline_theme='papercolor'

" Indentiline
let g:indentLine_char = '.'
let g:indentLine_enabled = 0
```

Para ```instalar``` um ou mais plugins excuto o comando ```:PlugInstall``` diretamente no editor vim.
Para ```remover``` um ou mais plugins, primeiro removo a declaração dele do arquivo ```~/.vimrc``` e no editor vim executo o comando ```:PlugClean```.
Para atualizar um ou mais plugins executo o comando ```:PlugUpdate``` no editor vim.

Para entender melhor o ```vim-plug``` basta conferir o repositório [junegunn/vim-plug](https://github.com/junegunn/vim-plug) no Github.

**03. O porquê de cada plugin.**

Uma breve descrição acerca dos plugins declarados acima, no arquivo ```.vimrc```.

[nerdtree](https://vimawesome.com/plugin/nerdtree-red) é um explorador de arquivos. Com ele consigo navegar numa estrutura de diretórios e trabalhar com vários arquivos, semelhante ao mais famosos editores do mercado, como Visual Studio Code e Sublime Text, por exemplo.

Para esse plugin utilizo um mapeamento de tecla na qual me permite chamar o explorador de arquivos teclando ```F2```.

```
" Keybind NERDTree
map <F2> :NERDTreeToggle<CR>
```