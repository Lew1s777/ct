tar
===

backup
---
```
tar -cvpzf /media/temp/backup.tar.gz --exclude=/run --exclude=/sys --exclude=/media --exclude=/proc --exclude=/tmp --exclude=/dev --exclude=/mnt /
```
参数解释
- tar：打包命令，用来备份；

- c：创建一个备份；

- v：详细模式， tar程序将在屏幕上实时输出所有信息；

- p：保留文件的访问权限标志，这个参数很重要，因为错误的访问权限可能导致程序无法运行；

- z：用“gzip”压缩备份文件，减小备份文件体积；

- f：指定备份文件的存放路径和名称，即[path]/[name].tar.gz可以根据实际情况，任意指定备份文件的存放位置。

- exclude：除了/home和/opt目录，我不想备份打包其他目录，可以用exclude参数来指定不包含在内的文件和文件夹。

- /：指定被备份的目录。因为是整个系统备份，所以指定根目录“/”。

restore
---
```
tar -xvpzf /media/disk/backup.tar.gz -C /
```

*
---
```
#tar -cvpzf /media/moose/share/20190130_debian9.6_amd64_home_opt.tar.gz --exclude=/bin --exclude=/etc --exclude=initrd.img.old --exclude=/lost+found --exclude=/run --exclude=/sys --exclude=/var --exclude=/boot --exclude=/lib --exclude=/media --exclude=/proc --exclude=/sbin --exclude=/tmp --exclude=vmlinuz --exclude=/dev --exclude=initrd.img --exclude=/lib64 --exclude=/mnt --exclude=/root --exclude=/srv --exclude=/usr --exclude=vmlinuz.old /

#back up all
tar -cvpzf /media/temp/arch.backup.tar.gz --exclude=/run --exclude=/sys --exclude=/media --exclude=/proc --exclude=/tmp --exclude=/dev --exclude=/mnt /

#back up without boot partition
#tar -cvpzf /media/temp/arch.backup.tar.gz --exclude=/run --exclude=/sys --exclude=/media --exclude=/proc --exclude=/tmp --exclude=/dev --exclude=/mnt --exclude=/data --exclude=/src --exclude=/boot /

```

---

#### backup only a dir(to bz2)
```
tar -cjf /media/data/backup/server.tar.bz2 ./*
```
