Lost sudo access after initial VM setup / unmatch root password (Rocky Linux)

Error:
	. user is not in the sudoers file

Root cause: 
	1. unmatch root passwd 
	2. user was not added to the wheel group during initial setup

Fix-1:
	1. in GRUB select the linux & press 'e' to edit boot entry
	2. find the line starting with 'linux' add 'rd.break' at the end of the line
	3. press 'ctrl + x' to boot into emergancy shell
	4. in root shell we need to remount system
		# mount -o remount,rw /sysroot
		# chroot /sysroot
		# passwd your_username ( in my case root )
		# touch /.autorelabel
		# exit
		# reboot
	5. if /sysroot was somehow not mounted this is the way to do it properly
		# mount /dev/mapper/rl-root /sysroot
		# chroot /sysroot

Fix-2:
	1. switched to root using 'su -'
	2. added user to wheel group:
		# usermod -aG wheel <username>
	3. verified group membership:
		# groups
	4. logged out and back in

Result:
	sudo commands now work correctly


Lesson learned:
	Using GRUB to go into emergancy shell and fixing issues there
	On RHEL-based systems, sudo access is controlled via the wheel group.
	Always verify administrative privileges after VM setup.
