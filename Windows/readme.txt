/********/
/********/
This week, windows 10 decide to do a greate update.
But w10 was selfish in a dual-boot system, and moved all 
my partitions to +1: (hd0,1) became (hd0,2) and so one.

So good suprise, when i boot i've a grub rescue prompt and, i'm a lucky man i
haven't live cd or usb.

Sooooo, fist of all, we need to find a unix partition where we can use to access to 
the grub.
Just check with a ls. Tipically it was the last partition (if you have 5 partition, it will be 
the 5th)

Then do:
-set prefix=(hdX,Y)/boot/grub OR set prefix=(hdX,Y)/grub
-set root=(hdX,Y)
-insmod normal
-normal

Now you have access to the boot selection. Press 'c' for enter to the grub, or boot on you unix.

/********/
/********/
