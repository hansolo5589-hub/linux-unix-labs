##########################################
#        Multiboot Linux Unix            #
#      Custom Grub config script         #
#     by Mohd Firoz (hansolo5589)        #
#                                        #
##########################################

#Copy the below script and paste it in your file editor and rename it 
#To: 40_custom and place it in your path /etc/grub.d/40_custom

#!/bin/sh
exec tail -n +3 $0

menuentry "Arch Linux (Lab External)" {
    insmod ext2
    set root='hd0,gpt3'
    linux /boot/vmlinuz-linux root=UUID=fb955c59-8742-4ba7-8304-52ba9823873a rw quiet
    initrd /boot/initramfs-linux.img
}

menuentry "Alpine Linux (Lab External)" {
    insmod part_gpt
    insmod ext2
    search --no-floppy --fs-uuid --set=root 42266e3e-3ba9-4412-b363-9fad76b434f1
    linux /boot/vmlinuz-lts root=UUID=42266e3e-3ba9-4412-b363-9fad76b434f1 modules=sd-mod,usb-storage,ext4 rootfstype=ext4 rw quiet
    initrd /boot/initramfs-lts
}

menuentry "Kali Linux (Lab External)" {
    insmod ext2
    set root='hd0,gpt7'
    linux /vmlinuz root=UUID=7d83ade9-d7a6-4706-be5b-88105c08ad3f rw quiet
    initrd /initrd.img
}

menuentry "Fedora 42 (Direct Boot)" --class fedora {
    insmod part_gpt
    insmod ext2
    search --no-floppy --fs-uuid --set=root 3c716bfe-9f00-4789-bfff-ecc25f4adb8a
    linux /boot/vmlinuz-6.19.14-108.fc42.x86_64 root=UUID=3c716bfe-9f00-4789-bfff-ecc25f4adb8a ro quiet
    initrd /boot/initramfs-6.19.14-108.fc42.x86_64.img
}

menuentry "FreeBSD (via EFI Loader)" --class freebsd {
    insmod part_gpt
    insmod fat
    search --no-floppy --fs-uuid --set=root A8F7-C7AB
    chainloader /EFI/freebsd/loader.efi
}
