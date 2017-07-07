## FISH SHELL
INSTALL
```bash
$ brew install fish
```

Set default shell
```bash
$ chsh -s /usr/local/bin/fish
```

Set fish config file: ~/.config/fish/config.fish
```bash
# configuration required to load oh-my-fish
set -g OMF_PATH $HOME/.local/share/omf
set -g OMF_CONFIG $HOME/.config/omf
source $OMF_PATH/init.fish

# add ~/.local/bin to PATH
set PATH ~/.local/bin/ $PATH

# sqlite3 config
set -g fish_user_paths "/usr/local/opt/sqlite/bin" $fish_user_paths

# exports
set -x LC_ALL en_US.UTF-8
set -x LANG en_US.UTF-8
set -x LANGUAGE en_US.UTF-8

# alias for vi
alias vi=vim

# add /usr/local/sbin to PATH to use RabbitMQ server
set PATH /usr/local/sbin/ $PATH

# Add Go to $PATH
set PATH /usr/local/go/bin/ $PATH

# configuration required to load virtualfish (MUST keep this line at the very bottom)
eval (python -m virtualfish)
```

## OH MY FISH
https://github.com/oh-my-fish/oh-my-fish

Install
```bash
$ cd /tmp/
$ curl -L https://get.oh-my.fish | fish
```

Usage example
```bash
$ omf install integral
```
> Themes to use with FISH: https://github.com/oh-my-fish/oh-my-fish/blob/master/docs/Themes.md


## VIRTUAL FISH
https://github.com/adambrenecki/virtualfish

Usage

create a virtualenv
```bash
vf new -p python3 neoapi
```

attach to virtualenv
```bash
vf activate neoapi
```

disable virtualenv
```bash
$ vf deactivate
```


## TMUX

set tmux config file: ~/.tmux
```bash
# modern encoding and colors
set -g default-terminal screen-256color

# open new split window in the current $PWD
bind '"' split-window -c "#{pane_current_path}"
bind % split-window -h -c "#{pane_current_path}"
bind c new-window -c "#{pane_current_path}"

# List of plugins
set -g @plugin 'tmux-plugins/tpm'
set -g @plugin 'tmux-plugins/tmux-sensible'
set -g @plugin 'tmux-plugins/tmux-resurrect'

# Initialize TMUX plugin manager (keep this line at the very bottom of tmux.conf)
run '~/.tmux/plugins/tpm/tpm’
```
