Please proceed with caution if ur trying to install or do this, if you cause
a nuclear reaction i will not be held responsible for it!!

This is my installation of 5 linux + 1 unix with an independant EFI and
GRUB tree in to a single external HDD usb. 

hansolo@wookie:~$ lsblk
NAME    MAJ:MIN RM   SIZE RO TYPE MOUNTPOINTS

Internal 2 HDD - 1TB(sda) + 1TB(sdb)

sda       8:0    0 931.5G  0 disk 
├─sda1    8:1    0   450M  0 part 
├─sda2    8:2    0   600M  0 part 
├─sda3    8:3    0    16M  0 part 
├─sda4    8:4    0 637.5G  0 part c:windows
├─sda5    8:5    0   519M  0 part 
├─sda6    8:6    0     1G  0 part 
└─sda7    8:7    0 291.4G  0 part /Fedora42

sdb       8:16   0 931.5G  0 disk 
├─sdb1    8:17   0   100M  0 part 
├─sdb2    8:18   0 540.8G  0 part
└─sdb3    8:19   0 390.6G  0 part 

USB EXTERNAL 1TB HDD
sdc       8:32   0 931.5G  0 disk 
├─sdc1    8:33   0    16M  0 part 
├─sdc2    8:34   0   2.9G  0 part /boot/efi
├─sdc3    8:35   0  78.1G  0 part /arch
├─sdc4    8:36   0  78.1G  0 part /alpine
├─sdc5    8:37   0  78.1G  0 part /fedora42
├─sdc6    8:38   0  78.1G  0 part /Debian
├─sdc7    8:39   0  78.1G  0 part /KALI
├─sdc8    8:40   0    78G  0 part /FREEBSD
├─sdc9    8:41   0  29.3G  0 part [SWAP]
├─sdc10   8:42   0  78.1G  0 part /EMPTYSPACE FOR EXTRA DEV TESTING
└─sdc11   8:43   0 352.4G  0 part /media/hansolo/SHARED
hansolo@wookie:~$ 

Therefore 1TB USB externel HDD now running smoothly for
1-Debian
2.ARCH
3.Fedora 42
4.Kali
5.Alpine
6.freebsd 14

As you can check and see the grub pictures has been loaded also here is
efibootmgr:

hansolo@wookie:~$ sudo efibootmgr -v
BootCurrent: 0005
Timeout: 5 seconds
BootOrder: 0005,0001,0002,0000,0003,0004,0006
Boot0000* Windows Boot Manager	HD(2,GPT,d3c92b43-5d2a-41e3-a689-2053d7252430,0x4fc12800,0x12c000)/File(\EFI\MICROSOFT\BOOT\BOOTMGFW.EFI)WINDOWS.........x...B.C.D.O.B.J.E.C.T.=.{.9.d.e.a.8.6.2.c.-.5.c.d.d.-.4.e.7.0.-.a.c.c.1.-.f.3.2.b.3.4.4.d.4.7.9.5.}....................
Boot0001* kali	HD(2,GPT,9a8f495d-2598-4e17-ae4b-446d4367f6ef,0x8000,0x5dc000)/File(\EFI\KALI\GRUBX64.EFI)
Boot0002* Fedora	HD(2,GPT,d3c92b43-5d2a-41e3-a689-2053d7252430,0x4fc12800,0x12c000)/File(\EFI\FEDORA\SHIM.EFI)..BO
Boot0003* Hard Drive	BBS(HD,,0x0)..GO..NO........o.W.D.C. .W.D.1.0.E.Z.E.X.-.0.8.W.N.4.A.0....................A...........................>..Gd-.;.A..MQ..L. . . . .W. .-.D.C.W.6.C.0.Y.K.C.D.5.8.F........BO..NO........o.W.D.C. .W.D.1.0.E.Z.R.X.-.0.0.L.4.H.B.0....................A...........................>..Gd-.;.A..MQ..L. . . . .W. .-.D.C.W.4.C.3.J.0.4.7.5.5.6........BO
Boot0004* Fedora	HD(2,GPT,9a8f495d-2598-4e17-ae4b-446d4367f6ef,0x8000,0x5dc000)/File(\EFI\FEDORA\SHIM.EFI)..BO
Boot0005* debian	HD(2,GPT,9a8f495d-2598-4e17-ae4b-446d4367f6ef,0x8000,0x5dc000)/File(\EFI\DEBIAN\GRUBX64.EFI)..BO
Boot0006* USB	BBS(HD,,0x0)..GO..NO........k.S.T.1.0.0.0.L.M. .0.1.5.7....................A.......................>..Gd-.;.A..MQ..L.W.D.E.6.D.X.7.6. . . . . . . . . . . . ........BO
hansolo@wookie:~$ sudo efibootmgr
BootCurrent: 0005
Timeout: 5 seconds
BootOrder: 0005,0001,0002,0000,0003,0004,0006
Boot0000* Windows Boot Manager
Boot0001* kali
Boot0002* Fedora
Boot0003* Hard Drive
Boot0004* Fedora
Boot0005* debian
Boot0006* USB
hansolo@wookie:~$ 

The grub was independant as i unplugged the internal hdd (sda & sdb)
sda-windows
sdb-fedora 42 (grub)

then proceed with the installation of each of the distros. 

These are my Labs and my favorite of all time distro, Yet i am thinking of 
installing REHL or ROCKY LINUX on this but that is for later. As you can see i have also installed
Arch linux on my Chrome Book which was previously chromeOs. It is still running smooth and fast.


For your referal heres the blkid:

hansolo@wookie:~$ sudo blkid /dev/sda7
/dev/sda7: LABEL="fedora" UUID="61fbcfca-f3ea-4005-97ed-a5c645b086de" UUID_SUB="aaea3aeb-d8d9-4aa2-8513-01c586aec738" BLOCK_SIZE="4096" TYPE="btrfs" PARTUUID="8912cc10-d7ca-45cd-9953-0421db430a9f"
hansolo@wookie:~$ sudo blkid /dev/sda4
/dev/sda4: BLOCK_SIZE="512" UUID="DED8A8B5D8A88CF9" TYPE="ntfs" PARTLABEL="Basic data partition" PARTUUID="d8a85285-6b89-4e46-925f-b8aa77664094"
hansolo@wookie:~$ sudo blkid /dev/sdc3
/dev/sdc3: UUID="fb955c59-8742-4ba7-8304-52ba9823873a" BLOCK_SIZE="4096" TYPE="ext4" PARTLABEL="ARCH_LAB" PARTUUID="43b6d7a8-ab87-404f-86bd-8720b819c7fc"
hansolo@wookie:~$ sudo blkid /dev/sdc4
/dev/sdc4: UUID="42266e3e-3ba9-4412-b363-9fad76b434f1" BLOCK_SIZE="4096" TYPE="ext4" PARTLABEL="ALPINE" PARTUUID="c3855667-352b-4fb5-9bef-61d7d9442cd7"
hansolo@wookie:~$ sudo blkid /dev/sdc5
/dev/sdc5: UUID="3c716bfe-9f00-4789-bfff-ecc25f4adb8a" BLOCK_SIZE="4096" TYPE="ext4" PARTLABEL="FEDORA42" PARTUUID="3c4c950e-f121-48d2-8713-1ebf549e96a1"
hansolo@wookie:~$ sudo blkid /dev/sdc6
/dev/sdc6: UUID="ce45c2ea-041d-4949-b63a-29e5260749e5" BLOCK_SIZE="4096" TYPE="ext4" PARTLABEL="DEBIAN" PARTUUID="de18a442-6605-444b-b28c-d93d851776bb"
hansolo@wookie:~$ sudo blkid /dev/sdc7
/dev/sdc7: LABEL="KALI" UUID="7d83ade9-d7a6-4706-be5b-88105c08ad3f" BLOCK_SIZE="4096" TYPE="ext4" PARTLABEL="KALI" PARTUUID="84fd5176-0e8d-4770-a001-6a0c795e8063"
hansolo@wookie:~$ sudo blkid /dev/sdc8
/dev/sdc8: LABEL="FBSD_LAB" UUID="6a068cf19884cf2e" BLOCK_SIZE="4096" TYPE="ufs" PARTLABEL="freebsd" PARTUUID="6f686685-500a-11f1-baff-2cfda1e34753"
hansolo@wookie:~$ sudo blkid /dev/sdc9
/dev/sdc9: UUID="2ece50b9-d2ba-4cf7-9a86-7a7397862906" TYPE="swap" PARTLABEL="SWAP_FOR_ALL_OS" PARTUUID="9481f93f-9d97-4584-9446-c85f67504d38"
hansolo@wookie:~$ sudo blkid /dev/sdc10
/dev/sdc10: LABEL="KERNELDEV" UUID="5753babd-5ff0-4a9c-908e-dbf0e7439439" BLOCK_SIZE="4096" TYPE="ext4" PARTLABEL="KERNELDEV" PARTUUID="7e6b4f3a-4a4c-4055-86d7-fb4ed617fd14"
hansolo@wookie:~$ sudo blkid /dev/sdc11
/dev/sdc11: LABEL="SHARED" UUID="582B-56EB" BLOCK_SIZE="512" TYPE="exfat" PARTLABEL="SHARED_WORKSPACE" PARTUUID="95842f6f-1034-4921-b3a0-20defbfe7b9e"
hansolo@wookie:~$
