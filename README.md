# `vim-monokai-tasty`

# Disclaimer

This repo is a fork of patstockwell's "vim-monokai-tasty" colorscheme with some modification of my own use.

1. Change BG color of current search result     -   from purple to white
2. Change BG color of incremental search result -   from purple to yellow

---
Monokai forever! Inspired by Sublime Text's interpretation of monokai. 

![](./images/example_main.png)

## 🔌 Installation

If you use _pathogen_
```bash
git clone https://github.com/steel911/vim-monokai-tasty.git ~/.vim/bundle/vim-monokai-tasty
```

If you use _Vundle_, add the following and run `:PluginInstall`
```vim
Plugin 'steel911/vim-monokai-tasty'
```

## 🐺 Use

Add the following to your `.vimrc` (after the Plug declaration):
```vim
colorscheme vim-monokai-tasty
```

If you use a terminal that supports italic text, add (before the colorscheme declaration):
```vim
let g:vim_monokai_tasty_italic = 1
colorscheme vim-monokai-tasty
```

If you want the slightly darker blue [variant of monokai](https://monokai.pro/) called "Machine"
```vim
let g:vim_monokai_tasty_machine_tint = 1
colorscheme vim-monokai-tasty
```

If you want to make the active window stand out, add
```vim
let g:vim_monokai_tasty_highlight_active_window = 1
colorscheme vim-monokai-tasty
```

To use the included [lightline.vim](https://github.com/itchyny/lightline.vim) theme:
```vim
let g:lightline = { 'colorscheme': 'monokai_tasty' }
```

To use the included [vim-airline](https://github.com/vim-airline/vim-airline) theme:
```vim
let g:airline_theme='monokai_tasty'
```


##  Screen shots

![](./images/example_javascript.png)
![](./images/example_vim_and_markdown.png)

##  Example `.vimrc`

```vim
call vundle#begin()
Plugin 'VundleVim/Vundle.vim'
Plugin 'steel911/vim-monokai-tasty'
Plugin 'pangloss/vim-javascript'
Plugin 'elzr/vim-json'
Plugin 'itchyny/lightline.vim'
Plugin 'vim-airline/vim-airline'
Plugin 'vim-airline/vim-airline-themes'
call vundle#end()

let g:vim_monokai_tasty_italic = 1                    " allow italics, set this before the colorscheme
let g:vim_monokai_tasty_machine_tint = 1              " use `mahcine` colour variant
let g:vim_monokai_tasty_highlight_active_window = 1   " make the active window stand out
colorscheme vim-monokai-tasty                         " set the colorscheme

" Optional themes for airline/lightline
let g:airline_theme='monokai_tasty'                   " airline theme
let g:lightline = { 'colorscheme': 'monokai_tasty' }  " lightline theme
let g:airline_section_z = airline#section#create(['%3p%%: ', 'linenr', ':%3v'])
let g:airline_section_a = airline#section#create(['paste', 'mode'])
let g:airline_symbols.paste = 'PASTE - '

function! AirlineInit()
    call airline#parts#define_raw('linenr', '%l')
    call airline#parts#define_accent('linenr', 'bold')
    let g:airline_section_z = airline#section#create(['%3p%%  ',
                \ g:airline_symbols.linenr .' ', 'linenr', ':%c'])
endfunction

autocmd VimEnter * call AirlineInit()

if !exists('g:airline_symbols')
    let g:airline_symbols = {}
endif

" unicode symbols
let g:airline_left_sep = '»'
let g:airline_left_sep = '▶'
let g:airline_right_sep = '«'
let g:airline_right_sep = '◀'
let g:airline_symbols.linenr = '␊'
let g:airline_symbols.linenr = '␤'
let g:airline_symbols.linenr = '¶'
let g:airline_symbols.branch = '⎇'
let g:airline_symbols.paste = 'ρ'
let g:airline_symbols.paste = 'Þ'
let g:airline_symbols.paste = '∥'
let g:airline_symbols.whitespace = 'Ξ'

" airline symbols
let g:airline_left_sep = ''
let g:airline_left_alt_sep = ''
let g:airline_right_sep = ''
let g:airline_right_alt_sep = ''
let g:airline_symbols.branch = ''
let g:airline_symbols.readonly = ''
let g:airline_symbols.linenr = ''

" If you don't like a particular colour choice from `vim-monokai-tasty`, you can
" override it here. For example, to change the colour of the search hightlight:
hi Search ctermbg=yellow ctermfg=black guibg=yellow guifg=black

```

## 🎨 Colour palette

| Colour name      |Colour Code | Colour
|------------------|------------|------------------------------------------------------------
| Yellow           | `#ffff87`  |![#ffff87](https://place-hold.it/100x40/ffff87/111111?text=+)
| Purple           | `#af87ff`  |![#af87ff](https://place-hold.it/100x40/af87ff/000000?text=+)
| Light Green      | `#A4E400`  |![#A4E400](https://place-hold.it/100x40/A4E400/000000?text=+)
| Light Blue       | `#62D8F1`  |![#62D8F1](https://place-hold.it/100x40/62D8F1/000000?text=+)
| Magenta          | `#FC1A70`  |![#FC1A70](https://place-hold.it/100x40/FC1A70/000000?text=+)
| Orange           | `#FF9700`  |![#FF9700](https://place-hold.it/100x40/FF9700/000000?text=+)

