Install commands:

```bash
# This rely on gnu mv (--backup=numbered). So alias mv=gmv on mac

# Backup existing ~/.config/tmux if it exists, using numbered backups (~1, ~2, etc.)
[ -d ~/.config/tmux ] && mv --backup=numbered ~/.config/tmux ~/.config/tmux_backup

# Clone the repository if ~/.config/tmux does not exist
git clone https://github.com/PoutineSyropErable/config_tmux ~/.config/tmux

# Backup existing ~/.tmux.conf if it exists, using numbered backups
[ -f ~/.tmux.conf ] && mv --backup=numbered ~/.tmux.conf ~/.tmux.conf.bak

# Create a symbolic link only if the cloned .tmux.conf exists
ln -s ~/.config/tmux/.tmux.conf ~/.tmux.conf

git clone --depth=1 https://github.com/tmux-plugins/tpm ~/.tmux/plugins/tpm

tmux
```

Now we need to setup tmux-sessionizer: 
 
```bash

[ -d ~/.config/tmux ] && mv --backup=numbered ~/.config/tmux-sessionizer ~/.config/tmux-sessionizer_backup

git clone https://github.com/PoutineSyropErable/config_tmux-sessionizer ~/.config/tmux-sessionizer

# And now the local executable

[ -d ~/.local/tmux-sessionizer ] && mv --backup=numbered ~/.local/tmux-sessionizer ~/.local/tmux-sessionizer_backup
git clone https://github.com/PoutineSyropErable/tmux-sessionizer --depth=1 ~/.local/tmux-sessionizer



```

then:

```bash
tmux source-file ~/.tmux.conf  # reloads the config with <prefix>, r
tmux run-shell ~/.tmux/plugins/tpm/tpm

# The way it works. You do prefix, then wait, then command key. 
# Prefix is Ctrl+b by default. Mine is Ctrl+s. You do both at once. 
# It's like a game combo. A+B then Y. 
# Ctrl+s then h. (To create an horizontal split)
# r is to reload, I is to install stuff

# or press
# C-b, r  ..... <C-b> is the default prefix. (Control + b)
#press C-s, r    ..... I changed mine to Control + s, so c-s might not work until the first reload.
#then
#C-s, I

# you can test if it work with C-s, h   ..... C-s, v   ....... C-s, x

# As in you press control s like you would to save on notepad. Then you release everyhting, the green square in the bottom left
# becomes yellow, and then you press whatever key. So it's like a combo in a game where you swing with your sword, and then shoot with your gun.
# One after another, with button release. Not at the same time.


#### Though, the copy pasting should do it by itself

```
