tmux
===
all so see [archwiki](https://wiki.archlinuxcn.org/wiki/Tmux)

keybind
---
<kbd>ctrl</kbd>+<kbd>b</kbd> +

|key|function|
|-|-|
|<kbd>c</kbd>|**c**reate a new window|
|<kbd>n</kbd>|switch to **n**ext window|
|<kbd>p</kbd>|switch to **p**revious window|
|<kbd>"</kbd>|horizontal split|
|<kbd>%</kbd>|vertical split|
|<kbd>'</kbd>|rename window|
|<kbd>o</kbd>|switch to next panel|

vim esc lag
---
```~/.tmux.conf```
```
set -s escape-time 0
```

autostart
---
```/etc/systemd/system/tmux@[username].service```
```
[Unit]
Description=Start tmux in detached session

[Service]
Type=forking
User=%I
ExecStart=/usr/bin/tmux new-session -s %u -d
ExecStop=/usr/bin/tmux kill-session -t %u

[Install]
WantedBy=multi-user.target
WorkingDirectory=/
```

put it under ```~/.config/systemd/user/tmux.service``` to start the service only when you login
