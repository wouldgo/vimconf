vimconf
=======

* Super easy to install and extend
* Everything in the vimrc is explained
* A universal configuration with a syntax checker, plugin manager and more

Installation
------------

**Dependencies:** [exuberant](http://ctags.sourceforge.net/)/[universal](https://github.com/universal-ctags/ctags) ctags (tagbar)

```sh
git clone https://github.com/timss/vimconf.git
ln -s vimconf/.vimrc ~/.vimrc
```

Run vim and it'll download and install all plugins automatically!

Configuration
-------------

If you choose to symlink your `~/.vimrc` you can easily maintain an updated
version of this vim configuration by using the local additions.

* `~/.vimrc.plugins` - Add your personal plugins here
* `~/.vimrc.first` - Prerequisites only, as it will be overwritten by whatever below
* `~/.vimrc.last` - Overrides everything, generally use this

I've chosen to include mostly universal plugins and configuration, meaning that
not a lot is language specific and should be suitable for most use cases. If
you want additional plugins for autocomplete and more you can do so easily
using your local files mentioned above.

Some useful plugins could be:

* [clang\_complete](https://github.com/xavierd/clang_complete) - C/C++ autocompletion using Clang
* [jedi-vim](https://github.com/davidhalter/jedi-vim) - Python autocompletion using the Jedi library
* [YouCompleteMe](https://github.com/ycm-core/YouCompleteMe) - Autocompletion for several languages (C/C++, Python, ..)

My personal configuration can be found in [timss/dotfiles](https://github.com/timss/dotfiles).

### Disabling plugins

If you want to disable any of the plugins included in the main configuration
either `UnPlug` them:

```viml
UnPlug 'ervandew/supertab'
UnPlug 'vim-syntastic/syntastic'
```

Or define a list of repo names to be disabled:

```viml
let g:plugs_disabled = ['supertab', 'syntastic']
```

Both should be added to `~/.vimrc.plugins`.

Preview
-------

![Preview](http://i.imgur.com/jpevpU7.png "Vim screenshot")

**Video:** [Writing a small perl-script using Vim](http://youtu.be/DrzAuLsxgwU) (rather outdated)

Disclaimer
----------

Even if this configuration can be used out of the box or tweaked using the
local files, I urge you to build your own if you have the time and energy to do
so. Only then will you be able to properly understand the reasoning behind each
setting and tailor it to your personal workflow.

However I still believe my Vim setup will help you get a basis configuration
for your own, introducing core ideas such as a plugin manager and
`.vimrc` structure. Use this configuration well, but do not blindly trust it to
suit you perfectly. It's intended to be played with!

Todo
----

* Update preview (gifs)
* Extract some language/plugin specific configuration to an example file (wiki)?
* Lazy loading
    * Analyze `--startuptime`
    * Add conditional plugin loading for plugins that don't properly lazy load
    * Move functions to `$HOME/.vim/autoload`?  
    See [How can I reduce startup time for vim?](http://stackoverflow.com/a/21197543/1076493)
