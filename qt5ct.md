qt5-styleplugins
===

- QT theme manager

Installtion
---
```
paru -S --rebuild qt5-styleplugins
```

If you did't add ```--rebuild``` argument,it will broken qt5.

configuration
---
add content below to ```/etc/environment``` .
```
QT_QPA_PLATFORMTHEME=qt5ct
```
Then reboot.
