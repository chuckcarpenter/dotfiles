# dotfiles

I discovered dotfiles and the way to finally be more DRY when I setup a system or _have to_ start over. It's a slippery slope of all the things you can do, here's a repo of my journey.

If you're interested in the philosophy behind why projects like these are
awesome, you might want to [read Holman's post on the
subject](http://zachholman.com/2010/08/dotfiles-are-meant-to-be-forked/).

## Install

Run this:

```sh
git clone https://github.com/chuckcarpenter/dotfiles.git ~/.dotfiles
cd ~/.dotfiles
script/bootstrap
```

This will symlink the appropriate files in `.dotfiles` to your home directory.
Everything is configured and tweaked within `~/.dotfiles`.

The main file you'll want to change right off the bat is `zsh/zshrc.symlink`,
which sets up a few paths that'll be different on your particular machine.

`dot` is a simple script that installs some dependencies, sets sane OS X
defaults, and so on. Tweak this script, and occasionally run `dot` from
time to time to keep your environment fresh and up-to-date. You can find
this script in `bin/`.

## Topical

Everything's built around topic areas. If you're adding a new area to your
forked dotfiles — say, "Java" — you can simply add a `java` directory and put
files in there. Anything with an extension of `.zsh` will get automatically
included into your shell. Anything with an extension of `.symlink` will get
symlinked without extension into `$HOME` when you run `script/bootstrap`.

## What's inside

A lot of stuff. Seriously, a lot of stuff. Check them out in the file browser
above and see what components may mesh up with you.
[Fork it](https://github.com/chuckcarpenter/dotfiles/fork), remove what you don't
use, and build on what you do use.

## Components

There's a few special files in the hierarchy.

- **bin/**: Anything in `bin/` will get added to your `$PATH` and be made
  available everywhere.
- **topic/\*.zsh**: Any files ending in `.zsh` get loaded into your
  environment.
- **topic/path.zsh**: Any file named `path.zsh` is loaded first and is
  expected to setup `$PATH` or similar.
- **topic/completion.zsh**: Any file named `completion.zsh` is loaded
  last and is expected to setup autocomplete.
- **topic/\*.symlink**: Any files ending in `*.symlink` get symlinked into
  your `$HOME`. This is so you can keep all of those versioned in your dotfiles
  but still keep those autoloaded files in your home directory. These get
  symlinked in when you run `script/bootstrap`.

## Thanks

I forked this from [Zach Holman's](http://zachholman.com/) dotfiles [repo](https://github.com/holman/dotfiles) and started the journey into customizing my sytem and saving those preferences for future use. You should do something of the same, perhaps start with his or do a simple Github search for `dotfiles` and see what works for you.
