EFISTUB loading linux kernel
===

My installation command

```
efibootmgr --create --disk /dev/nvme0n1 --part 1 --label "GNU/Linux" --loader /vmlinuz-linux-arch --unicode 'root=UUID=d264e431-775b-438d-82cb-f3d688eb6586 resume=UUID=d08d6a72-14e4-48b8-94ed-a16f2fe9baa3 rw loglevel=3 quiet initrd=\initramfs-linux-arch.img initrd=\amd-ucode.img'
```
