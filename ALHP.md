ALHP
===
Buildbot for Archlinux-based repos build with different x86-64 feature levels, -O3 and LTO.

Installation
---
- Check which feature-levels your CPU supports with
```
/lib/ld-linux-x86-64.so.2 --help
```

- Install keyring & mirrorlist (from aur)
```
paru -S alhp-keyring alhp-mirrorlist
```

- Modify ```/etc/pacman.conf```
  - add content below to ```/etc/pacman.conf``` **above regular repo**
  - Replace ```x86-64-v3``` with the x86-64 feature level you want to enable.
```
[core-x86-64-v3]
Include = /etc/pacman.d/alhp-mirrorlist

[extra-x86-64-v3]
Include = /etc/pacman.d/alhp-mirrorlist

[community-x86-64-v3]
Include = /etc/pacman.d/alhp-mirrorlist
```

- Update package database and upgrade
```
pacman -Suy
```
