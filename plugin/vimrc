if v:lang =~ "utf8$" || v:lang =~ "UTF-8$"
   set fileencodings=utf-8,latin1
endif

"source $VIMRUNTIME/vimrc_example.vim
source $VIMRUNTIME/mswin.vim
behave mswin


if has("gui_running")
colorscheme desert
else
colorscheme darkblue
endif

"for taglist
let Tlist_Exit_OnlyWindow=1
let Tlist_File_Fold_Auto_Close=1 
let Tlist_Auto_Open=1
let Tlist_Use_Right_Window=1

" Minimal number of screen lines to keep above and below the cursor.
"set scrolloff=999

" Status line
set laststatus=2
set statusline=
set statusline+=%-3.3n\ " buffer number
set statusline+=%f\ " filename
set statusline+=%h%m%r%w " status flags
set statusline+=\[%{strlen(&ft)?&ft:'none'}] " file type
set statusline+=%= " right align remainder
set statusline+=0x%-8B " character value
set statusline+=%-14(%l,%c%V%) " line, character
set statusline+=%<%P " file position

" Show line number, cursor position.
set ruler

" Display incomplete commands.
set showcmd

" Search as you type.
set incsearch
" Ignore case when searching.
set ignorecase

" Font. Very important.
if has('win32') || has('win64')
set guifont=Consolas:h12:cANSI
elseif has('unix')
let &guifont="Monospace 10"
endif


"au GUIEnter * simalt ~x

set nocompatible	" Use Vim defaults (much better!)
set bs=indent,eol,start	 " allow backspacing over everything in insert mode
set nobackup	 " do not keep a backup file
set viminfo='20,\"50	" read/write a .viminfo file, don't store more
" than 50 lines of registers
set history=50	 " keep 50 lines of command line history
set ruler	 " show the cursor position all the time

" Only do this part when compiled with support for autocommands
if has("autocmd")
  " In text files, always limit the width of text to 78 characters
  autocmd BufRead *.txt set tw=78
  " When editing a file, always jump to the last cursor position
  autocmd BufReadPost *
  \ if line("'\"") > 0 && line ("'\"") <= line("$") |
  \   exe "normal! g'\"" |
  \ endif
endif

" set mouse=a

set shiftwidth=2
set expandtab
set tabstop=2
set ai!
set nu!
set fileformat=unix
if has("cscope") && filereadable("/usr/bin/cscope")
   set csprg=/usr/bin/cscope
   set csto=0
   set cst
   set nocsverb
   " add any database in current directory
   if filereadable("cscope.out")
      cs add cscope.out
   " else add database pointed to by environment
   elseif $CSCOPE_DB != ""
      cs add $CSCOPE_DB
   endif
   set csverb
endif

" Switch syntax highlighting on, when the terminal has colors
" Also switch on highlighting the last used search pattern.
if &t_Co > 2 || has("gui_running")
  syntax on
  set hlsearch
endif

if &term=="xterm"
     set t_Co=8
     set t_Sb=[4%dm
     set t_Sf=[3%dm
endif
