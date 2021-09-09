Dotfiles
========

Initial creation
----------------

How this repository was created:

```bash
git init --bare $HOME/.dotfiles
echo "alias dotfiles='/usr/bin/git --git-dir=\$HOME/.dotfiles/ --work-tree=\$HOME'" >> $HOME/.bashrc
```

Open new terminal and run:

```
dotfiles config --local status.showUntrackedFiles no
```

Restore dotfiles
----------------

```
git clone --separate-git-dir=$HOME/.dotfiles https://github.com/pathob/dotfiles.git $HOME/dotfiles
shopt -s dotglob nullglob
mv dotfiles/* $HOME
rmdir dotfiles
```

References
----------

* Based on https://www.atlassian.com/git/tutorials/dotfiles
* Which is based on https://news.ycombinator.com/item?id=11071754
