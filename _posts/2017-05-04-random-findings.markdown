---
published: true
title: Random findings
layout: post
---
Secure GPG key generation using `gpg`:

~~~
gpg2 --gen-key
gpg2 --list-keys
gpg2 -K --keyid-format long --with-colons --with-fingerprint
gpg2 --export -a $ID
~~~

Other useful GPG commands;
~~~
gpg2 --delete-secret-key $email
gpg2 --delete-key $email
gpg --armor --export $email > "${email}.asc"
~~~

Long ssh key generation using `ssh-keygen`:

~~~
ssh-keygen -b 16384
~~~

Setting fedora docker directories permission using `chcon`:

~~~
sudo chcon -Rt svirt_sandbox_file_t /var/lib/docker/volumes/
chcon -Rt svirt_sandbox_file_t $volume_dir
~~~

Burning Ubuntu to USB using `dd`:

~~~
lsblk -f
umount /dev/sdb1
dd if=ubuntu-16.04.2-desktop-amd64.iso of=/dev/sdb bs=4M status=progress
sync
~~~

Ignoring changes for file in `git`:

~~~
git update-index --(no-)assume-unchanged
~~~

Removing project containers using `docker-compse`:

~~~
docker-compose down --rmi all --remove-orphans
~~~

Rebuilding project containers using `docker-compose`:

~~~
docker-compose up --build
~~~

Updating all globally installed gems using `gem` and `cut`:

~~~
sudo gem update `gem list | cut -d ' ' -f 1`
~~~

Upgrading to Fedora 26 using `system-upgrade`:

~~~
dnf upgrade --refresh
dnf install --assumeyes dnf-plugin-system-upgrade
dnf system-upgrade download --refresh --releasever=26
dnf system-upgrade reboot
~~~
