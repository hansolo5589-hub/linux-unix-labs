***************************************************************************
                  MY USB EXTERNAL 1TB HARD DISK 
                 MULTIBOOT LINUX AND UNIX PROJECT 
                       BY MOHD FIROZ HANIF.
**************************************************************************

More details on how to do it available on Multiboot-manual-installation.md

Please proceed with caution if ur trying to install or do this, if you cause
a nuclear reaction i will not be held responsible for it!!

THIS IS MY PROJECT OF WHICH TOOK ME AT LEAST 5 days in total just to have all these installed
and later on to config and to run each testing and it became my daily drivers!!!!
Talk about VMS eh... haha

I do have other repo:
Hardening suite
Harware Audior -written on ASM + C + Perl
Elite Proxy
Local1-cyber range
and this LINUX UNIX-LABS-

  This is my installation of 5 linux + 1 unix with an independant EFI and GRUB tree in to a single external HDD usb.  MANUAL PARTITIONING!!!! Im extracting all these information using My debian 12. Its has been more then 6-7 months still smooth as silk.haha

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

The GRUB installation was built completely independent by physically unplugging the internal drives 
(sda and sdb where sda is Windows and sdb holds Fedora 42 grub) 
before proceeding with the installation of each distro on the external drive.

Note on Updates: When distros update, kernel updates will sometimes refresh their own grubs and
insert entries into the motherboard NVRAM. It’s totally manageable as long as you keep your 
custom grub scripts running and backed up, then proceed with the installation of each of the distros.
The first Distro i installed was debian. 

These are my Labs and my favorite of all time distro, Yet i am thinking of 
installing REHL or ROCKY LINUX on this but that is for later. As you can see i have also installed
Arch linux on my Chrome Book which was previously chromeOs. It is still running smooth and fast.


I really had alot fun yet alot of troubleshooting and especially scripting (grub) when doing this. 
Please be careful when you try this type of installations as this may mess up your partitions 
If you have no idea or any clue what your doing.!! (Do some research and ask the pros out there!!!)
I will also post my grub files and others as to share with you guys later on....

ps: got another 1tb External HDD USB... shall i do it for unix perhaps... haha later..

Thank you.
God Bless..
