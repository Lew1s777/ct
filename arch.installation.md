```
Arch linux installation cheatsheet by Github@Lew1s777
```
- check list
  - Before installation check your boot mode(UEFI/BIOS) (and for dual-boot with other operating system,check your whether your EFI partition is enough;make sure your PC battery is enough)
- download iso
  - download iso image from "https://archlinux.org/download/" and make a installation medium(USB drive)
- boot in your installation medium
- preparation
```
##optional,change the font
#$ setfont /usr/share/kbd/consolefonnts/[whatever u want]

## optional,if you are using keymaps that are not commonly used
#$ loadkeys [ur keymap]

#connect the internet(wifi/wpa_supplicant)
$ ip link	                                        #check your network card device's name
$ ip link set [networkcard] up	                        #enable your network card
iwlist [networkcard] scan | grep ESSID			#scan the internet,find your wifi's name
wpa_passphrase [ESSID] [password] > internet.conf
wpa_supplicant -c internet.conf -i [networkcard] &
dhcpcd &

timedatectl set-ntp true				#sync time
```

- partition:

  - see "https://wiki.archlinux.org/title/Installation_guide#Partition_the_disks" "https://wiki.archlinux.org/title/Dual_boot_with_Windows#Linux_before_Windows"
```
fdisk -l						#check your disk device name
fdisk [disk]						#start making partition
#	m-help
#	p-print condition
#	g-make new gpt partition table
#	n-make new partition
#       t-change the type of ur disk
mkfs.fat -F32 [/dev/XX1]				#only UEFI user should do this step
mkswap [/dev/XX2]					#make swap
swapon []/dev/XX2]					#set swap on
```

- mount partition
```
mkdir /mnt/boot						#only UEFI user should do this step
mount /dev/XX1 /mnt/boot				#only UEFI user should do this step
mount /dev/XX2 /mnt
```

- config pacman
```
vim /etc/pacman.conf					#config your package manager(pacman);use nano if you are not a vim user,it is recommended to remove the comments of "Color"
vim /etc/pacman.d/mirrorlist				#use mirrors
```

- start installation:)
```
#install arch
pacstrap /mnt base base-devel linux-firmware linux-zen linux-zen-headers

#make fstab(for mounting partitions)
genfstab -U /mnt >> /mnt/etc/fstab                                                              
```

- configure ur band new arch linux system
```
vim /mnt/etc/pacman.conf;vim /mnt/etc/pacman.d/mirrorlist	#config pacman of new system
arch-chroot /mnt					#change root to new system
ln -fs /usr/share/zoneinfo/[ur zone] /etc/localtime		#set your zone
hwclock --systohc
pacman -S archlinux-keyrings			#install some basic tool
vim /etc/locale.gen					#delete the comment of your local
locale-gen
vim /etc/locale.conf
	#Lang=en_US.UTF-8
vim /etc/hostname					set your hostname
vim /etc/hosts
	#127.0.0.1	localhost
	#::1		localhost
	#127.0.1.1	[hostname]
passwd							#set your pc password
```

- make arcn bootable
```
pacman -S grub efibootmgr amd-ucode os-prober		#install intel-ucode if your intel processor user
mkdir /boot/grub
grub-mkconfig -o /boot/grub/grub.cfg
grub-install --target=x86_64-efi --efi-directory=/boot	--bootloader-id=GRUB#DO NOT SIMPLY FOLLOW THIS STEP!set you own architecture & boot folder
#basic installlation finished
```
- reboot ur pc
```
reboot							#reboot your pc
```

sync time
---

```
timedatectl set-ntp true
```
