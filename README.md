

Vagrant sharing failure



Vagrant was unable to mount VirtualBox shared folders. This is usually
because the filesystem "vboxsf" is not available. This filesystem is
made available via the VirtualBox Guest Additions and kernel module.
Please verify that these guest additions are properly installed in the
guest. This is not a bug in Vagrant and is usually caused by a faulty
Vagrant box. For context, the command attemped was:

set -e
mount -t vboxsf -o uid=`id -u root`,gid=`getent group root | cut -d: -f3` vagran                          t /vagrant
mount -t vboxsf -o uid=`id -u root`,gid=`id -g root` vagrant /vagrant

The error output from the command was:

/sbin/mount.vboxsf: mounting failed with the error: No such device

