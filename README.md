## How to Enable /etc/rc.local for Running Commands on Linux Boot
If you are running a Linux distribution that use Systemd, then you may find that your command in /etc/rc.local file would not run on system boot. The rc-local.service already exists in systemd and, if rc.local exists and is executable, it gets pulled automatically into multi-user.target.

You can check the status if you type the following command in terminal:

sudo systemctl status rc-local

First you need to create /etc/rc.local file, if it doesn't exists.
```
sudo nano /etc/rc.local
```

Make sure /etc/rc.local file is executable.
```
sudo chmod +x /etc/rc.local
```

Finally, enable the service on system boot.
```
sudo systemctl enable rc-local
```

Contents of rc.local File
```
#!/bin/sh -e
#
# rc.local
#
# This script is executed at the end of each multiuser runlevel.
# Make sure that the script will "exit 0" on success or any other
# value on error.
#
# In order to enable or disable this script just change the execution
# bits.
#
# By default this script does nothing.

<Add terminal commands here without sude>

exit 0
```
