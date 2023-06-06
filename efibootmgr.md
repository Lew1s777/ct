efibootmgr
===

打开终端。

输入以下命令以查看当前的启动项列表：

```
sudo efibootmgr
```
找到要删除的启动项的编号。

输入以下命令以删除启动项：

```
sudo efibootmgr -b [启动项编号] -B
```
其中，[启动项编号] 是要删除的启动项的编号。

输入以下命令以确认启动项已被删除：

```
sudo efibootmgr
```
确认启动项已被删除后，可以关闭终端。


also see [EFISTUB booting](./EFISTUB.md)
