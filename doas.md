doas
===

installation
---

install package ```opendoas```

configure
---

- make ur config ```/etc/doas.conf``` is accessible for every one
```
chown -c root:root /etc/doas.conf
chmod -c 0400 /etc/doas.conf
```
check again:
```
doas -C /etc/doas.conf && echo "config ok" || echo "config error" 
```

- edit config ```/etc/doas.conf```
```
permit persist :wheel
permit nopass :plugdev as root cmd /usr/bin/smartctl
```

bash tab complete
---
edit ```~/.bashrc```
```
complete -cf doas
```
