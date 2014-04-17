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


