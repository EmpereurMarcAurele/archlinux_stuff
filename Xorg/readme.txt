/********/
/********/
This year i have a bug on my laptop with xorg.
I update my kernel via pacman and xorg stop working, invoke some errors with my
video card device nvidia (see that on /var/log/Xorg.0.log)

Yeah, long time haven't update kernel. Anyway, will be a good debug execise.
My xorg configuration use a deprecated conf file (xorg.conf). So, rtfm and see a new way
to configure all the stuff on /etc/X11/xorg.conf.d/

Each devices have his .conf file and the number set the execution priority
for example the keyboard conf file looks: 10-keyboard.conf

For my video card, i don't use nvidia anymore but the integrate graphics chips (intel)

So, first of all, update your system:
-pacman -Syu  

Of course, i'm not a luck personne and update fail on a certificate.
solution:
-pacman -Syuw
-rm /etc/ssl/certs/ca-certificates.crt
-pacman -Su
/!\ pacman -Syu --force DON'T work.

Okay, so next step was to remove all nvidia stuff
-pacman -R nvidia

check if xorg is really install
-pacman -S xorg
check if intel driver install
-pacman -S xf86-video-intel

Now, we need to remove xorg.conf file (/etc/X11/) and create conf files for 
each following devices:
-keyboard-layout
-monitor
-screen
-intel

Just read the archlinux wiki to how write a good .conf, good explanation.
-startx

/!\ ofc it works well for me, but each bug was diffrent,depends of your system config and
	don't have the same solution has mine.
/!\ the good way to resolve bugs was to READ logs, use your brain and at least google.
/***********/
/***********/
