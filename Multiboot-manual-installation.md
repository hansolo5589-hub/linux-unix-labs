***************************************************
* Installation of multiboot linux & unix          *
* Drive: USB 1TB External Hard Disk               * 
* Disto: DEBIAN,ARCH,KALI,FEDORA,ALPINE & FREEBSD *
* BY: MOHD FIROZ HANIF (HANSOLO5589)              *
***************************************************

It took me a while to do this manual technical installation after more than 6 months while looking thru my notes.
Sorry guys. Preparing this tech manual (not much i guess) on DEBIAN 12 bookworm.

Please Know what your doing ... and those script kiddies-- GO READ OR DO SOME FUCKIN RESEARCH OR ASK THE UBER PRO
LINUX/UNIX GUYS-- NEVER TAKE AI AS BIBLICAL INSTRUCTIONS!!! YOU MAY FUCK UP EVERYTHING AND BLOW UP EVERYTHING HAHAH!!!
This is not Kiddie stuff!! 

                                             *********
                                             *Purpose*
                                             *********
I just want to check my insanity and see my curiosity about:
-If i still have the knowledge and skills i had long ago back 1999 when i started to use linux and unix.
-Always want to see how each kernel act and behaves on each distro for kernel development. 
-New Horizon for me as i can use multi linux kernels, and if i can bridge Unix and Linux.
-To find out where i am at the kernel level.
-I HATE VMS- VMS IS FOR PUSSY!!!HAHA !!

                                           **************
                                           *Prerequistes*
                                           **************
**External HDD 1 TB -working in good conditions.
**Downloaded distro: GET THE STABLE versions!!!
1.Debian 12 BOOKWORM
2.Arch Linux
3.Alpine linux
4.Kali linux
5.Fedora 42
6.FreeBSD

1 Thumb Drive- to be used as a LIVE USB 
2.Download - Balena Etcher or Fedora Media Writer! To make your Thumbe drive live usb.!


                                       *********************************
                                       *Brace and Prepare your self.!!!!*
                                        *********************************

when i thought about doing this project, i was like " im going nuts!!! " haha but it was challenging for me. The idea was to get to try the distros without the usage of Vms, as from my point of view,VMs always runs different then the 
actual Distro. So here i am ... why use Vms if i can get the distro itself right, I guess that was the idea behind it. As i was stil pondering on it, linux and unix is bare metal works like a charm- So proceeded to study 
and do my research on the distro. Heres the KEYWORD for you "DO RESEARCH PLENTY OF IT"!!.

And come on there is alot of manuals, communities and uber pro linux and unix users out there... just dont ever
rely only on AI or any videos to get you there. You will need extra knowledge and skills -as so to speak - DO PLENTY
OF READING & RESEARCH ON THE DISTRO YOU WOULD WANT TO TRY !! Dualboot Windows and linux is wayyyyy different than 
MULTIBOOT LINUX WITH DIFFERENT DISTROS + A UNIX SYSTEM. Thats my humble advice to you out there!



                                           **************************
                                           *Preparations:PARTITIONS.* 
                                           **************************

                                                     CAUTION:
            DONT MAKE A MISTAKE OF REPARTIONING OR FORMATING YOU OWN RUNNING HDD--HERES WHERE MISTAKES TAKES PLACE!!!!
           ALWAYS KNOW WHAT YOUR DOING !!!!!!!! YOU CAN FUCK UP YOUR GOOD RUNNING WINDOWS/LINUX PARTITIONS!!


                                 *************************************
                                 *Hardware: 1 TB external HDD 2.5inch*
                                 *************************************

You can use GPART,FDSIK, WINDOWS PARTITION MANAGERS, and everything else of which suits you or make it easy for you. 

         IF YOUR USING LINUX TO DO THE PARTITIONS- YEAH GREAT-- JUST KEEP YOU EYE ON THE SDA, SDB SDC...SDXXXXXX... 
         MAKE SURE YOU KNOW WHICH PARTITION YOUR CRAFTING-DUDE!!!

Okay here we are as you already decided to proceed. Remember your call!!! 

So what i did was.. I partition the HDD and label it so i could figure out where and what im doing.. I was using fedora 42 when I did this. Also I had written down the partition names or sizes or any other information that i can get from the lsblk command.


hansolo@wookie:~$ lsblk -o NAME,SIZE,FSTYPE,LABEL,MOUNTPOINT /dev/sdc

NAME      SIZE FSTYPE LABEL     MOUNTPOINT

sdc     931.5G 
├─sdc1     16M 

├─sdc2    2.9G vfat EFIBOOTOS /boot/efi

├─sdc3   78.1G ext4 

├─sdc4   78.1G ext4 

├─sdc5   78.1G ext4 

├─sdc6   78.1G ext4               /

├─sdc7   78.1G ext4   KALI

├─sdc8     78G ufs    FBSD_LAB

├─sdc9   29.3G swap              [SWAP]

├─sdc10  78.1G ext4   KERNELDEV 

└─sdc11 352.4G exfat  SHARED

hansolo@wookie:~$ 

As you can see i have partition the tables for each distro handlings should be at about 80GB (plenty eh i guess).
Then after the balance i just left it as a full partition at about 300GB. For the EFIBOOTS /boot/efi i partition it to 3GB- as for all the bootloaders , grub files will be stored here. Oh yess also swap i gave at about 30GB plenty of room there.I reckon some of you would have different partitions table break downs for your own project thats fine. But heres the thing, would we format it early or leave it empty space.Heres a TIP:--- What i did was i left it just an empty space no formating anything!!! even the fat32 partitions.Because linux/unix will detect empty partition space -- during the installation process or the setup process as you call it.

                                    *************************************
                                    *Prepare the USB Installation Media *
                                    *************************************

     Prerequisite: Check the Distro Size to download
                   BALENA ETCHER (BE) / FEDROA MEDIA WRITTER (FMW)
     Hardware   :  8gb/10gb or what ever thumbdrive you have!!!
     Predownload:  Debian Or the DIstro of your choice!!!
     Tips       :  Check and verify your downloaded distro with the website u download from 
                   and also check and verify your Installation media vs the Downloaded distro once created!!!


At this time i had only 8GB kingmax USB thumb drive for me to use it as an installation media. OH yes VENTOY, and everything else, I have tried but yet failed on my side terribly !!! lucky the setup/installation process didnt get thru. Maybe i was doing something wrong,i dont know!! The tools was great but it didnt work out for me!!!(no offence for the super developers who build the tools- the tools are great and awesome) Well.. i took the old skool method perhaps the long way- using 1 bootable usb media to install all 6 distro ... haha hell yeah that was awesome ride. All right coming back... BALENA ETCHER .... 

YES  i said it  BALENA ETCHER-  go download that here  https://etcher.balena.io/  and get the latest version 
*If you using windows to do it~ make sure u get the windows installation setup  -*.exe 
*If you using linux ~ get the linux version or you can easily install it thru CLI or download and  install it. 

Noowwww... This media, once you use it on balena etcher ~ it will write the linux files of you favorite distro on the Thumb drive. 

I have already installed and had BALENA ETCHER and also FEDORA MEDIA WRITTER. So my first choice of Distro to be installed was DEBIAN - ( i have PRE-DOWNLOADED the debian distro from their website) which is debian 12 ( i choose that stable version).

So here i used Balena Etcher on Fedora 42 hahaha... i always know fedora media writter could get it done but i just went along with balena etcher. Write the Thumb drive with the pre-downloaded Debian 12 distro and WAIT FOR IT TO FINISH.  I DONT CARE JUST WAIT FOR IT TO FINISH DUDE---> DO NOT DISTURB THE FREAKING WRITING PROCESS or other wise you will have corrupted media or damaged media!!! 

After completion of the writting process on the media! CHECK AND VERIFY!!! how do you verify...if you dont know...
gosh dude !! u shouldnt be here!!anyway...check the checksum md5 fiile of which u downlowded matches with your media device u just using BE or FMW. Use your Terminal thats why its there! For windows users...gosh ... again do some research on it before proceed. Once that verify and done completely the same....then your good to go!!! 

Pro tip: don't just download and hope. Once the download finishes, do this to check and verify if the installation distro is good ! Use this command to run on your terminal or your own known commands.

Example: ARCH LINUX Distro 
sha256sum archlinux-2026.05.01-x86_64.iso
it should return this...
┌─~/Downloads 

└─⚡  sha256sum archlinux-2026.05.01-x86_64.iso     
4af795aab6530e8344553961d0a0e8e84f9622a131ee7d44b0b86b035b2d9ff7  archlinux-2026.05.01-x86_64.iso

That is an example for arch linux-- likewise the same for debian or other distros you download. Always CHECK AND VERIFY first then proceed to write the media. Once that complete -- Verify the Media itself is it the same ?? Or if u have otherways to check,please do! ....after this you still have few more verifications and checking to be completed just to be on the safe side.

                                *****************************************
                                **Before power off: check this first...**
                                *****************************************

if your using linux, you can do it on the terminal itself.:

hansolo@wookie:~$ mokutil --sb-state

SecureBoot disabled

hansolo@wookie:~$ sudo dmesg |grep -i secureboot

[sudo] password for hansolo: 

[    0.000000] secureboot: Secure boot disabled

since your here check also for your tpm:
ls -l /dev/tpm*
sudo dmesg | grep -i tpm

• Enabled Output: You will see lines like tpm_tis ... TPM device found along with the version (e.g., TPM 2.0 device).
• Disabled Output: The command will either return nothing or show a message indicating the device failed to initialize.

If it is disabled you will see something like this:
hansolo@wookie:~$ sudo ls -l /dev/tpm*
[sudo] password for hansolo:
ls: cannot access '/dev/tpm*': No such file or directory
hansolo@wookie:~$ sudo dmesg | grep -i tpm
[    0.722511] ima: No TPM chip found, activating TPM-bypass!
[    6.314574] systemd[1]: systemd 252.39-1~deb12u2 running in system mode
(+PAM +AUDIT +SELINUX +APPARMOR +IMA +SMACK +SECCOMP +GCRYPT -GNUTLS +OPENSSL
+ACL +BLKID +CURL +ELFUTILS +FIDO2 +IDN2 -IDN +IPTC +KMOD
+LIBCRYPTSETUP +LIBFDISK +PCRE2 -PWQUALITY +P11KIT
+QRENCODE +TPM2 +BZIP2 +LZ4 +XZ +ZLIB +ZSTD -BPF_FRAMEWORK -XKBCOMMON +UTMP +SYSVINIT default-hierarchy=unified)

But for windows user: YUCKKKK!!!
run-->msinfo32 --> system summary
or 
powershell:(admin privilage!!)
Confirm-SecureBootUEFI

Then proceed if it is OFF otherwise

 ***************************************************************************************************
 *1. POWER OFF PC                                                                                ***
 ***************************************************************************************************
 *2. Unplugg the internal HDD (this is how i did mine.SAFEST!!) and plug in your external HDD.!!!***
 ***************************************************************************************************
 *3. PLUG IN YOUR MEDIA (THUMB DRIVE) WHICH YOU USE TO CREATE JUST NOW!!!                        ***
 ***************************************************************************************************

*****QUICK CHECK LIST****************
• Secure Boot: Disabled
• SATA Mode: AHCI (instead of RAID)
• CSM / Legacy: Disabled (UEFI Only)
• Fast Boot: Disabled
• Boot Priority: USB at the top
*************************************

1.--BOOT UP YOUR FREAKING PC--hit Functions KEY (WHICH EVER THAT POINTS YOU TO LOAD BIOS) to boot up BIOS

                                           ********
                                           **BIOS**
                                           ********

2.GO LOOK FOR -SECURE BOOT TURN IT OFFF!!--- JUST TURN THE THING OFFF!!!! HAHAHA
**Disable CSM / Legacy Boot: Ensure your system is set to UEFI Only.
**Fast Boot / Ultra Fast Boot: Disable this
**TPM--DISBLE THAT BITCH if you FIND IT!! hahhaha come on dude who needs TPM when you have LUKS!! 
  I was joking... DISABLE IT...

3.SWITCH YOUR BOOT OPTIONS TO LOAD YOUR USB THUMB DRIVE .!!You can already see if your usb thumb drive is detected.
--Boot Priority: Move your USB Flash Drive / USB HDD to the top of the boot order (Boot Option #1).
4.Save all those. F10 or what ever key your pc bios wanting to save. Then reboot!!!
5.After Rebooting--if it loads your thumb drive grub or linux loader... installation media... awesome...then proceed.

If it doesnt load
--check thumb drive boot options
--thumbdrive media writing process
--secureboot disabled
--check if your storage is set to RAID
--check if TPM is enabled or DISABLED---MINE I DISABLE TPM FUCK IT!!! hahah 


                                            ***************************** 
                                            *Installation / setup linux *
                                            *****************************

                                   *******************************************
                                   *1'st distro setup : Here i choose Debian *
                                   *******************************************

Your here!!! awesome glad you made it. Now... i know most of you have installed or setup linux +windows.
We use to setup linux not dual booting ..single booting!...then experimenting on dual booting..
I really do appreciate those guys out there since back in 1999s my first distro was REDHAT LINUX 5.2 and my first
unix was FREEBSD 4.4 at that time. Single booting...then to dual booting.. here i learn manual partitioning and compiling kernels and it was a hell of a ride. Thanks to the Uber Pro LINUX/UNIX Gurus out there you guys are great always!!

Here i always do this everytime i want to install linux or unix-- CHECK MEDIA INSTALLATION!! choose that..and let that run!!!Just to be on the safe side that your media is working fine and all the installation files are in perfect order!! Guys this was important to me as i have gone thru many hiccups ughhhh .... reduces error and human errors as you can narrow down your troubleshooting if anything were to go wrong -- not just by guessing!!!

Now since everything has changed... i reckon you know by now how to install or setup linux single or dual rite. if you dont ! Gosh go read dude... DONT TELL ME ABOUT AI CRAP!! So Here we dont do auto partitioning... we do manual. 
Choose the manual partitioning . UNDERSTAND HERE WHAT YOU DO AND WHAT YOU SEE at your screen.

It will help on the other distro installation. THe first one should be easy peasy lemon squeeze for you because only single installation of the distro. Proceed to install to the desired partitions of your choice . Choose EXT4 format easy for other linux to discover or mount also easy on FreeBSD. Once the setup or installation completes...proceed to remove your thumbdrive and boot your bloddy linux distro!!! hahah ... If all is good and no errors on your side... then linux should be loading and you should see a log in page to enter your desktop. 

There...congrats setting up your linux. ---now i believe you already have installed linux and on your dekstop and have an internet connection active rite now. Go and install your browser of your choice or otherwise you can just download the BALENA ETCHER (BE) straight from you CLI and install it!! Fuckin dont ask me how!!! hahaha... come on man!! Get real!!!
Once you got that installed fired it up and plug in back your thumb drive let it detect and read for you. I assume you already downloaded you 2nd distro-- of your choice--- use BE to write the thumbdrive for the 2nd distro of your choice. Once that is done -completed-- check and verify both downloaded file vs website vs thumb drive ....here comes Hell!!! hahahahahha...

                                    *********************************************
                                    *2nd distro setup: Here I choose Arch Linux *
                                     *********************************************

If you already have terminal opened up...fire at will sudo reboot!!!! hahah linux will reboot...or u jsut can reboot at the desktop icon as
you know how! ....OII...make sure you already have plugged in your usb thumb drive..otherwise...hahaha oh my lord..!!

Once reboot done... bios will autmatically detect your so called thumb drive and boot on the 2nd distro of your choice.. which is
Arch Linux in my case. I proceeded the Arch Linux installation manually- everything was partitioned manually during the installation,
here be prepared to use the command lines if in need arise. So LEARN BEFORE YOU DO SOMETHING!!!

Heres a tip format only on the choosen partitions. and /swap and /boot /efi only ONCE!!! 

For the 3rd 4th and the 5th setup you wont need to format again leave it unformatted
/boot
/swap
/efi

because the grub2 files will be on the /boot folders. so you dont want to format it!!

As you can see here once it is done correctly, you should have the following:

hansolo@wookie:~$ sudo ls -ls /boot/efi

[sudo] password for hansolo: 
total 20

4 drwx------2 root root 4096 May 10 18:47 '$RECYCLE.BIN'

4 drwx------11 root root 4096 May 13 18:14  EFI

4 -rwx------1 root root   34 May 13 09:02  mach_kernel

0 -rwx------1 root root    0 May 14 20:16  NvVars

4 drwx------3 root root 4096 May 13 09:02  System

4 drwx------2 root root 4096 May 10 17:11 'System Volume Information'

hansolo@wookie:~$ sudo ls -ls /boot/efi/EFI
total 36

4 drwx------ 2 root root 4096 May 11 11:45 ARCH

4 drwx------ 2 root root 4096 Mar 14  2025 BOOT

4 drwx------ 2 root root 4096 May 13 18:22 certs

4 drwx------ 2 root root 4096 Aug 15 23:42 debian

4 drwx------ 3 root root 4096 May 14 22:00 fedora

4 drwx------ 2 root root 4096 May 15 12:13 freebsd

4 drwx------ 2 root root 4096 May 12 09:05 GRUB

4 drwx------ 2 root root 4096 May 12 22:17 kali

4 drwx------ 2 root root 4096 May 13 18:56 tools

hansolo@wookie:~$ 

                                    *********************************************
                                    *COMPLETE INSTALL 3RD ,4TH, 5TH LINUX DISTRO*
                                    *********************************************

Now as for the subsequent setups 3rd 4th and the 5th installations are just similar with the 2nd setup but just remember dont format those partitions. HERE IN MY CASE : I PROCEEDED TO INSTALL -- ALPINE , KALI , FEDORA TO COMPLETE THE INSTALLATION/SETUP!! REMEMBER ARCH IS MINIMAL LEAN-KISS CONCEPT( KEEP IT SIMPLE STUPID!) HAHA LOVE THAT... SO YOU MIGHT NOT SEE ALL THE LOADING LINUX PROCESS BUT YET IT WILL LOAD ...THATS KIND OF NICE AND BADASS ...HAHA I LIKE THAT...

AS FOR THE ALPINE- you will see linux loading screens.. the hardware check ups and process until load.
Ahh the great FEDORA-- YES HERE YOU WILL SEE AS USUAL. AND there is a reason why i put fedora last...as fedora will grab by defaul the grub and will detect automatically.FEDORA GRUB IS YOUR BACK UP PLAN IF ALL FAIL!! HAHAH DAMNN THAT IS SCARY EH !! DONT WORRY !!!

Set 
BOOT PRIORTY - DEBIAN 1st option. (IN MY CASE )
I HAVE FEDORA 42 GRUB ALSO DETECTED ON BOOT AND ALSO KALI BOOT.Load Debian---> once loaded--- run the os-prober command and let Debian detect all the Distro installed.What you should be able to see is fedora ,Debian, Alpine Arch Kali...on the grub menu. But here in my case.. i was only able to see fedora and debian and kali only. ARCH AND ALPINE was not visible on bios boot and was not visible on grub. So you should know how to extract that and point grub2 to the current folders. WE are talking about grub2 -->> point to /boot/efi/EFI vmlinuz to load it. 

So GET USED TO wrestle and fighting with GRUB2--> 'e' command line interface etc.... Here you must remember the partitions that you create earlier to install each distro sdxN--- because in grub emergency command line you need to set root to point to the partitions of each linux. Just be prepared for that!!! The best possible way is, i have running debian and fedora to do it. So here i choose debian to handle my grub2.

******************
*Debian ----Grub2*
******************

What i did was, i let Os-Prober detect all my other distro in Debian and I create a custom GRUB to point to the rest remaining Distro. That works out fine for me , i will post my grub2 conf files maybe would help you guys out. Later... hell... that was really hell fighting and wrestling with Grub-- Once you get that done... THAT IS SATISFYING!!! TRUST ME!! YOU WILL GET IT!!

If all is good and went well with the GRUB2 configurations...

You should be able to see All your linux detected by Grub....Congrats... you freakin fuckin made it ...thats what i thought hahaha... So..here we need to test it each distro if it loads...so mind you ... you will test you grub2 config custom files. If all is good ---> all linux will load nicely and as smooth as slik.

Remember here you can choose which distro to act lead Grub on your boot bios, but here in my case i choose Debian which is far much better handling then fedora grub (no offence to you guys out there Fedora!! haha). 
I managed to install everything then comes the hell ride of all times--FREEBSD INSTALLATION.

                                           *********************
                                           *FreeBSD Installtion*
                                           *********************

Create and prepare the live usb for freebsd installer- THIS IS NOT VMS!! ACTUAL INSTALLATION!!! 

I used the complete dvd installation iso and used Balena Etcher (BE) to write the thumb drive. 

Oh yes in case your wondering... I did use the DD command to clean the thumb drive first 

sudo dd if=/dev/zero of=/dev/sdx(your humbdrive) bs=4m status=progress conv=fsync

Please do be careful when you use that command. Like i said before PLEASE KNOW WHAT YOUR DOING--> that thing will wipe out everything and non recoverable!! hahaha So use it at your own risk!!! I proceeded with the installation 
of the FreeBSD distro once all was checked and verified and good to run.

Once the Freebsd installation complete , here i would like to emphasise that MANUAL INSTALLATION is done also- 
means you choose and partition using ufs(my choice), u wil have ZFS also so choose wisely and do not format your /boot /efi /swap and others partitions!!! or you will loose everything.

Freebsd is a BEAST!! damnn love it!!! It will gain control of everything if you dont know what your doing!!.

So here Im done with the installations and completed and all succesfully rebooted. Now once reboot...
Freebsd will automatically loads--- you wil not see your debian or fedora or linux grub!!! hahaha... that really shocked me as well hahah. Dammnn im getting old for this... once first load done. Reboot again and load BIOS...and there you can see you BOOT OPTION DEBIAN IS there. All what ever boot options of other distros also will be there. In my case arch and alpine was not.

Then i went and log in to Debian and redid my GRUB2 custom again. All rite here i was wrestling with it! oncemore. There are 
other options of which available on the Internet or comunity using which rEFInd :

you can find it here:
https://www.rodsbooks.com/refind/

but instead i use manual grub writing ---hahaha. Old habbits dude im sorry !!! so i did chainloading...haha
debian script custom Grub2 chainload freebsd. That took me a while to get the script running... oh when you do grub and point it at /dev/da0p8 in my case the partition where i installed the Freebsd you will encounter filesystem error when loading freebsd. 

Freebsd will want you to repair the filesystem. So be prepared for it. 

mine was :
ufs: /dev/da0p8

remember to mount to / first. --> go read about how to repair Fsck on freebsd. Otherwise that beast of FREEBSD will not allow you to load completely!!! haha no kiddie stuff eh !!!

Please check and research first before you run the commands!!!! Open your manuals or guides or Google it for fuck sake!!!
mount -u -a -t -w / ufs 
fsck -y

Once that done. Grub2 config is done menu entry appear all Linux distro including FreeBSD. MISSION ACCOMPLISHED.!!!!
THE ONLY HIICCUPE I FACE ON FREEBSD is my usb wireless dongle not detected lucky i have an older old skool aztech usb wireless. so I manage to get internet connection and updated my freebsd and configured it. 

The final reboot-->> perfect!!!! 

Debian
ARCH
Alpine
Kali
Fedora
FreeBSD

so here it is the menu entry of my GRUB:

hansolo@wookie:~$ sudo grep -E "menuentry" /boot/efi/EFI/debian/grub.cfg

if [ x"${feature_menuentry_id}" = xy ]; then

menuentry_id_option="--id"

menuentry_id_option=""

export menuentry_id_option

menuentry 'Debian GNU/Linux' --class debian --class gnu-linux --class gnu --class os $menuentry_id_option 
'gnulinux-simple-ce45c2ea-041d-4949-b63a-29e5260749e5'

{submenu 'Advanced options for Debian GNU/Linux' $menuentry_id_option 'gnulinux-advanced-ce45c2ea-041d-4949-b63a-29e5260749e5'
{
menuentry 'Debian GNU/Linux, with Linux 6.1.0-51-amd64' --class debian --class gnu-linux --class gnu --class os
menuentry_id_option 'gnulinux-6.1.0-51-amd64-advanced-ce45c2ea-041d-4949-b63a-29e5260749e5'

{menuentry 'Debian GNU/Linux, with Linux 6.1.0-47-amd64' --class debian --class gnu-linux --class gnu --class os
$menuentry_id_option 'gnulinux-6.1.0-47-amd64-advanced-ce45c2ea-041d-4949-b63a-29e5260749e5'

{menuentry 'UEFI Firmware Settings' $menuentry_id_option 'uefi-firmware'
{menuentry "Arch Linux (Lab External)"
{menuentry "Alpine Linux (Lab External)"
{menuentry "Kali Linux (Lab External)" 
{menuentry "Fedora (Direct Boot)" --class fedora 
{menuentry "FreeBSD (via EFI Loader)" --class freebsd 
}
hansolo@wookie:~$

***CHECK THE GRUB FILE I HAVE ATTACHED. AS WHEN DOING THIS MANUAL I MIGHT MISS OUT SOME WORDINGS OR CODINGS!!

Heres my Boot Priorities:

hansolo@wookie:~$ sudo efibootmgr
[sudo] password for hansolo: 
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

hansolo@wookie:~$ sudo efibootmgr -v

BootCurrent: 0005 Timeout: 5 seconds BootOrder: 0005,0001,0002,0000,0003,0004,0006 Boot0000* Windows Boot Manager HD(2,GPT,d3c92b43-5d2a-41e3-a689-2053d7252430,0x4fc12800,0x12c000)/File(\EFI\MICROSOFT\BOOT\BOOTMGFW.EFI) WINDOWS.........x...B.C.D.O.B.J.E.C.T.=.{.9.d.e.a.8.6.2.c.-.5.c.d.d.-.4.e.7.0.-.a.c.c.1.-.f.3.2.b.3.4.4.d.4.7.9.5.}....................

Boot0001* kali HD(2,GPT,9a8f495d-2598-4e17-ae4b-446d4367f6ef,0x8000,0x5dc000)/ File(\EFI\KALI\GRUBX64.EFI)

Boot0002* Fedora HD(2,GPT,d3c92b43-5d2a-41e3-a689-2053d7252430,0x4fc12800,0x12c000)/File (\EFI\FEDORA\SHIM.EFI)..BO

Boot0003* Hard Drive BBS(HD,,0x0)..GO..NO........o.W.D.C. .W.D.1.0.E.Z.E.X.-.0.8.W.N.4.A.0....................A...........................> ..Gd-.;.A..MQ..L. . . . .W. .-.D.C.W.6.C.0.Y.K.C.D.5.8.F........BO..NO........o.W.D.C. .W.D.1.0.E.Z.R.X.-.0.0.L.4.H.B.0....................A...........................> ..Gd-.;.A..MQ..L. . . . .W. .-.D.C.W.4.C.3.J.0.4.7.5.5.6........BO

Boot0004* Fedora HD(2,GPT,9a8f495d-2598-4e17-ae4b-446d4367f6ef,0x8000,0x5dc000)/File (\EFI\FEDORA\SHIM.EFI)..BO

Boot0005* debian HD(2,GPT,9a8f495d-2598-4e17-ae4b-446d4367f6ef,0x8000,0x5dc000)/File (\EFI\DEBIAN\GRUBX64.EFI)..BO

Boot0006* USB BBS(HD,,0x0)..GO..NO........k.S.T.1.0.0.0.L.M. .0.1.5.7....................A.......................>..Gd-.; .A..MQ..L.W.D.E.6.D.X.7.6. . . . . . . . . . . . ........BO

Heres more of my Blkd id:

hansolo@wookie:~$ sudo blkid /dev/sda7 /dev/sda7: LABEL="fedora" UUID="61fbcfca-f3ea-4005-97ed-a5c645b086de" UUID_SUB="aaea3aeb-d8d9-4aa2-8513-01c586aec738" BLOCK_SIZE="4096" TYPE="btrfs" PARTUUID="8912cc10-d7ca-45cd-9953-0421db430a9f"

hansolo@wookie:~$ sudo blkid /dev/sda4 /dev/sda4: BLOCK_SIZE="512" UUID="DED8A8B5D8A88CF9" TYPE="ntfs" PARTLABEL="Basic data partition" PARTUUID="d8a85285-6b89-4e46-925f-b8aa77664094"

hansolo@wookie:~$ sudo blkid /dev/sdc3 /dev/sdc3: UUID="fb955c59-8742-4ba7-8304-52ba9823873a" BLOCK_SIZE="4096" TYPE="ext4" PARTLABEL="ARCH_LAB" PARTUUID="43b6d7a8-ab87-404f-86bd-8720b819c7fc"

hansolo@wookie:~$ sudo blkid /dev/sdc4 /dev/sdc4: UUID="42266e3e-3ba9-4412-b363-9fad76b434f1" BLOCK_SIZE="4096" TYPE="ext4" PARTLABEL="ALPINE" PARTUUID="c3855667-352b-4fb5-9bef-61d7d9442cd7"

hansolo@wookie:~$ sudo blkid /dev/sdc5 /dev/sdc5: UUID="3c716bfe-9f00-4789-bfff-ecc25f4adb8a" BLOCK_SIZE="4096" TYPE="ext4" PARTLABEL="FEDORA42" PARTUUID="3c4c950e-f121-48d2-8713-1ebf549e96a1"

hansolo@wookie:~$ sudo blkid /dev/sdc6 /dev/sdc6: UUID="ce45c2ea-041d-4949-b63a-29e5260749e5" BLOCK_SIZE="4096" TYPE="ext4" PARTLABEL="DEBIAN" PARTUUID="de18a442-6605-444b-b28c-d93d851776bb"

hansolo@wookie:~$ sudo blkid /dev/sdc7 /dev/sdc7: LABEL="KALI" UUID="7d83ade9-d7a6-4706-be5b-88105c08ad3f" BLOCK_SIZE="4096" TYPE="ext4" PARTLABEL="KALI" PARTUUID="84fd5176-0e8d-4770-a001-6a0c795e8063"

hansolo@wookie:~$ sudo blkid /dev/sdc8 /dev/sdc8: LABEL="FBSD_LAB" UUID="6a068cf19884cf2e" BLOCK_SIZE="4096" TYPE="ufs" PARTLABEL="freebsd" PARTUUID="6f686685-500a-11f1-baff-2cfda1e34753"

hansolo@wookie:~$ sudo blkid /dev/sdc9 /dev/sdc9: UUID="2ece50b9-d2ba-4cf7-9a86-7a7397862906" TYPE="swap" PARTLABEL="SWAP_FOR_ALL_OS" PARTUUID="9481f93f-9d97-4584-9446-c85f67504d38"

hansolo@wookie:~$ sudo blkid /dev/sdc10 /dev/sdc10: LABEL="KERNELDEV" UUID="5753babd-5ff0-4a9c-908e-dbf0e7439439" BLOCK_SIZE="4096" TYPE="ext4" PARTLABEL="KERNELDEV" PARTUUID="7e6b4f3a-4a4c-4055-86d7-fb4ed617fd14"

hansolo@wookie:~$ sudo blkid /dev/sdc11 /dev/sdc11: LABEL="SHARED" UUID="582B-56EB" BLOCK_SIZE="512" TYPE="exfat" PARTLABEL="SHARED_WORKSPACE" PARTUUID="95842f6f-1034-4921-b3a0-20defbfe7b9e"


I think this is and was the biggest thing and the most craziest thing i ever did!!! hahaha 
So here i can tell you READ READ READ & DO PLENTY OF RESEARCH & LEARN & TRY--->> CHECK VERIFY AND PERFORM.
Dont take AI as a biblical instructio as this will cause error on your side!!!
You can also check out my grub config files and custom grub i have added to this repo maybe it would help you out. 

                                                        ******
                                                        *PROS*
                                                        ******

For god sake man!! Its linux and unix!!! Everything Always pros about it.!!! Otherwise your not a linux UBERUSER,
hahaha eat your heart out!!! Where else you would get system wide control.!!
-DEPTH Knowledge and skills developed
-CLI is the utmost power!!!!
-Multi linux distro skills and knowledge
-Unix Freebsd knowledge and skills
-and Many more-- you need to learn how to use it only then you would know!!

                                                        ******
                                                        *CONS*
                                                        ******

The only Cons i have faced here is:
-1 usb thumbdrive for everything.8gb -- i guess this is not actually a CONs thou. Perhaps i dont know! I dont care.
-USB wireless dongle not supported on FREEBSD...REALTEK!!! damn it!!!
-Grub wrestle and scripting for each menuentry and troubleshooting
-Filesystem error on Freebsd and Arch - managed to do it and repair it.
-Oh ChainLoading freebsd to grub linux debian.
 that was something!!! didnt use any extra software or even tried it!!ALL MANUAL
-updating and grub replacement - you just need to readjust it once only- That requires knowledge and skills!

                                                     ************
                                                     *Challanges*
                                                     ************
-Freakin Realtek not supported Wireless dongle For FreeBSD--damn it!!!
-3-4 days just to install everything. and another couple of days just to configure grub scripting!
 Completion About 5 days.

                                                    ************
                                                    *Resources:*
                                                    ************

Previous Experiance using Linux and unix 20 years+- So i have the guts and knowledge and skill set to pull this things off!!! -
Method Old skool!!! Read & research!!!
-Ebook Pdfs on freebsd, debian kali alpine arch fedora.
-FreeBSD Manuals
-Arch Llinux Manuals
-Debian Manuals
-Fedora manuals
-Alpine Linux Manuals
-Kali linux manuals
-Community - FreeBSD, FEDORA, DEBIAN, KALI , ARCH, ALPINE


                                                  **************
                                                  *REPOSITORIES*
                                                  **************

OH YES DUDE...  I do want to share this also with you all:

Debian-updating & Pulling Debian repo and Kali repo    ---PURE TANK

Arch- updating & pulling Arch repo and Black arch Repo ---TOTAL POWERHOUSE

Alpine-each pulling repos and updating      ---CLOUDS CONTAINERS

Kali-each pulling repos and updating-????still thinking what the hell is this for !!! hahaha

Fedora-each pulling repos and updating      ---DEVELOPMENT

Freebsd-each pulling repos and updating     ---THE BEAST FOR EVERYTHING!!

Thats the best part.!!! Have fun trying and learning - knowledge and skills beats everything-- !!! 
I do have other repositories on hardening linux and unix also elite ghost setup script , hardware auditor, and few more of which i will make it public in time to come. Just bear with me guys. 

Thats all there is!!! Hope this manual or guide or HOWTOS  brings you ways to do it and get you there 
with some ideas on how to do it.

cheers !!!

Signing off!!!

take care and god bless.
Mohd Firoz (hansolo5589)
