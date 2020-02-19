## Using ctags in vim

As part of my recent drive to purge unnecessary bloat from my configurations, I am experimenting with using tags files in projects to aid with navigation and autocomplete in vim.

For python projects, of course I want tags for all my virtualenv packages as well as for my own code, so I need to ensure that happens with the following:

`ctags -R . ~/.virtualenvs/project/lib64/python3.8/site_packages`

Install ctrags from exuberant tags in Debian.
