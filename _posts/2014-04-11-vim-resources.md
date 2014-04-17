---
layout: post
title: Vim Resources
---

# General Sites
[Vimcasts](http://vimcasts.org/)

[usevim](http://usevim.com/)


# Some Plugins

Where possible, listed including link to documentation.

[vim-surround](https://github.com/tpope/vim-surround) ([documentation](https://github.com/tpope/vim-surround/blob/master/doc/surround.txt))

[auto-pairs](https://github.com/jiangmiao/auto-pairs) ([see also](http://www.vim.org/scripts/script.php?script_id=3599))

To manage plugins, see [Vundle](https://github.com/gmarik/Vundle.vim).
Configuration:

    set nocompatible
    filetype off

    " intialize Vundle
    set rtp+=~/.vim/bundle/vundle/
    call vundle#rc()

    " manage Vundle using Vundle... (it's required!)
    Plugin 'gmarik/vundle'

    " managed plugins
    Plugin 'tpope/vim-surround'
    " currently using gruvbox scheme, no need for railscasts then
    "Plugin 'jpo/vim-railscasts-theme'
    Plugin 'morhetz/gruvbox'
    Plugin 'nelstrom/vim-visual-star-search'
    Plugin 'jiangmiao/auto-pairs'

    filetype plugin indent on


