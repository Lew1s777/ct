systemd-boot
===

install
---
```
bootctl install
```

uninstall
---
```
bootctl remove
```

configure
---

```/boot/loader/loader.conf```
```
default arch #->arch.conf
timeout 1
editor  0
```

```/boot/loader/entries/arch.conf```
```
title Arch Linux               #name
linux   /vmlinuz-linux         #kernel
initrd  /intel-ucode.img       #cpu ucode
initrd  /initramfs-linux.img   #ramfs
options root=/dev/sdap2 rw     #/root,LABEL\PARTUUID\UUID
```

