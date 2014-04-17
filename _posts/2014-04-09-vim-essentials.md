---
layout: post
title: Vim Essentials
---

## Recognize md files as Markdown
To have vim automatically use the _markdown_ filetype upon finding the
`.md` file name extension, add to `.vimrc`

    au BufRead,BufNewFile *.md set filetype=markdown

Without this, vim defaults to using _modula_ as the file type.


## Enter special characters
Use `C-v` or `C-q` to quote the next character. Then enter 3 decimal
digits, or `x` followed by 2 hexadecimal digits. For Unicode support,
enter `u` and then 4 hexadecimal digits. Further details at
<http://vim.wikia.com/wiki/Entering_special_characters>.

## Other bits from current configuration

    set langmenu=en_US.UTF-8
    "language messages en

    set encoding=utf-8

    " fixes slow ruby editing?
    set re=1

    let mapleader=","

    syntax on

    "colorscheme desert
    " blackboard scheme from http://www.vim.org/scripts/script.php?script_id=2280
    "colorscheme blackboard
    " molokai scheme also managed using pathogen, origin github.com/nviennot/molokai
    "colorscheme molokai
    "colorscheme railscasts
    colorscheme gruvbox
    set bg=dark
    let g:gruvbox_contrast='hard'

    " color tweaks (from desert)
    highlight clear Search
    highlight Search guibg=peru guifg=wheat

    set autoindent
    set shiftwidth=4
    set tabstop=4
    set softtabstop=4
    set expandtab
    set nowrap

    " configure display of invisible characters (colors work for blackboard and
    " molokai schemes, for desert not so much; symbols used are present in Droid Sans Mono
    " Slashed as well as Ubuntu Mono, may or may not work with other fonts)
    set list
    "set listchars=tab:›\ ,eol:¬,extends:…,precedes:…,trail:∙
    " trail characters: uF8FF from Consolas' Private Use Area (an Apple symbol...)
    " black circle u25cf (Unicode Geometric Shapes)
    " medium black circle u26ab (Unicode Miscellaneous Symbols)
    set listchars=tab:›\ ,eol:¬,extends:…,precedes:…,trail:●
     
    highlight NonText guifg=#4a4a59 guibg=bg
    highlight SpecialKey guifg=#4a4a59 guibg=bg
    "highlight NonText guifg=#4a4a59 guibg=#1b1d1e
    "highlight SpecialKey guifg=#4a4a59 guibg=#1b1d1e

    set backspace=indent,eol,start

    set wildmenu
    "set wildmode=list:full
    set wildmode=full
    set wildignore=*.o,*.obj,*.class,*.jar,*.war,*.car,.git,*.pyc
    set wildignorecase

    set hlsearch
    set incsearch
    set ignorecase
    set smartcase

    set fileformats=unix,dos
    set backup
    set backupdir=~/.backup

    set history=50

    set number
    set relativenumber
    set numberwidth=5
    set showmatch

    set ruler
    set laststatus=2
    set statusline=%<%n\ %F\ %y%h%m%r%=%q\ \ 0x%B\ %b\ \ %l,%c%V\ %P

    set whichwrap+=<,>,[,]

    set hidden

    set visualbell

    " using tags
    set tags=./tags;$HOME
    map <M-[> :tprev<CR>
    map <M-]> :tnext<CR>

    if has("autocmd")
      filetype on
      " indentation of 2 spaces for Ruby
      autocmd FileType ruby setlocal tabstop=2 shiftwidth=2 softtabstop=2 expandtab
    endif

    inoremap jj <esc>

    nnoremap <silent> <C-Tab>   :bnext<CR>
    nnoremap <silent> <C-S-Tab> :bprevious<CR>
    inoremap <silent> <C-Tab>   <ESC>:bnext<CR>
    inoremap <silent> <C-S-Tab> <ESC>:bprevious<CR>

    " copy and paste
    vmap <C-C> "+y"
    vmap <C-V> "+gP
    nmap <C-V> "+gP
    imap <C-V> <C-R>+

    " create a 'scratch' buffer at startup
    au VimEnter * if empty(expand('%')) | set buftype=nofile | endif

    " treat .md files as markdown, not modula
    au BufRead,BufNewFile *.md set filetype=markdown

