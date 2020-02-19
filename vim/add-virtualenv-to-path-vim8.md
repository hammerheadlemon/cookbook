### Vim renaissance

In Jan 2020, I went back to basics with vim and cleared out neovim and all the plugins. Installed vim8.2 from source with python3 enabled but there was an annoying bug (actually, a segfault) when running `:compiler`, so I went back to installing Vim 8.1 from apt in Debian stable.  I used the package `vim-nox` which is compiled with support for scripting languages - Python is what I want - but it is not compiled for X, so no sharing the clipboard with the X server.

So that I could do `gf` on import statements, I added a new file at ~/.vim/after/ftplugin/python.vim with the following:

```vim
python << EOF
import os
import sys
import vim
for p in sys.path:
    # Add each directory in sys.path, if it exists.
    if os.path.isdir(p):
        # Command 'set' needs backslash before each space.
        vim.command(r"set path+=%s" % (p.replace(" ", r"\ ")))
EOF
```

I got it from here: `https://vim.fandom.com/wiki/Automatically_add_Python_paths_to_Vim_path`. Thanks guy!

This doesn't deal with virtualenvs, so if I want this to work on a virtualenv package, I have to add the `site_packages` directly.

To do that, I do `:set path+=/home/lemon/.virtualenvs/project/lib64/python3.8/site_packages` or whatever. Then I can do `gf` on imports to get to source.

You can use gutentags packages in vim which creates tags files automatically. To make this work with virtualenvs, install two files in the project root:

`.gutctags`, the config file for gutentags, which includes:

```
-L .virtualenv_tags
```

The `-L` flag means to include another file which can contain paths to different directories you want ctags to use.

And inside `.virtualenv_tags` I include:

```
/home/lemon/.virtualenvs/ctrack/lib64/python3.8/site-packages/
```

By I got rid of gutentags and went manual.
