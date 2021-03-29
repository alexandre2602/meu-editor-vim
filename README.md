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
Plug 'yggdroot/indentline'
Plug 'plasticboy/vim-markdown'
Plug 'dracula/vim',{'as':'dracula'}

call plug#end()

" Keybind NERDTree
map <F2> :NERDTreeToggle<CR>

" VIM Airline Theme
let g:airline_theme='papercolor'

" Indentiline
let g:indentLine_char = '.'
let g:indentLine_enabled = 0

" https://vimawesome.com/plugin/markdown-syntax
" Disable Folding
let g:vim_markdown_folding_disabled = 1

syntax on
colorscheme dracula
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

[vim-airline](https://vimawesome.com/plugin/vim-airline) adiciona uma barra de status na parte inferior do editor, permitindo uma rápida compreensão do status do arquivos e alguns informações adicionais.

[vim-airline-themes](https://vimawesome.com/plugin/vim-airline-themes) me permite aplicar alguns temas no editor. É puro capricho, mas pra mim ajuda. Utilizo o tema chamado ```papercolor```. Para saber quais os temas disponíveis basta [clicar aqui](https://github.com/vim-airline/vim-airline/wiki/Screenshots).

```
" VIM Airline Theme
let g:airline_theme='papercolor'
```

[vim-yaml](https://vimawesome.com/plugin/vim-yaml) é para melhorar o dia à dia do ```YAML Engineer```, pois garante a identação dos arquivos YAML.

[indentline](https://vimawesome.com/plugin/indentline) me permite visualizar os níveis de indentação. Dessa forma evito erros devido a má indentação nos arquivos YAML ou Python, por exemplo, que são rigorosos nesse ponto.

Por padrão essa visualização dos níveis de indentação no meu editor fica desabilitada, pois aciono apenas quando julgo ser necessário digitando o comando ```:IndentLinesEnable```.

```
" Indentiline
let g:indentLine_char = '.'
let g:indentLine_enabled = 0
```

[vim-markdown](https://vimawesome.com/plugin/markdown-syntax) se trata de syntax highlighting para escever em Markdown no editor VIM.

Utilizo a opção abaixo para desabilitar o recurso de foldind que me permite ocultar ou expandir blocos de textos organizados por indentação.

[dracula](https://draculatheme.com/vim) apenas um tema dark bonitão para utilizar no VIM.
```
colorscheme dracula
```
