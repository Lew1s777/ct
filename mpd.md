mpd
===

Music Player Daemon

Installation
---

run(as root)
```
pacman -S mpd ncmpc
```

Configuration
---
- copy default config
```
cp -v /usr/share/doc/mpd/mpdconf.example ~/.config/mpd.conf
```

- set personal file directory

- auto update
```
auto_update "yes"
auto_update_depth "3"
```

- set alsa audio input
```
audio_output {
    type            "alsa"
    name            "default"
    mixer_type      "software"      #optional
}
```

usage
---
```
mpd;ncmpc
```
