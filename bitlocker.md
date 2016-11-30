Lock manually Bitlocker Driver
==============================================

Lock drive F: with bitlocker

Run this command with administrator

`manage-bde.exe -lock -forcedismount F:`

Use Bitlocker Volume on Ubuntu
=====================

### 1. Install `dislocker` by source

Download dislocker in link: [http://www.hsc.fr/ressources/outils/dislocker/download/](http://www.hsc.fr/ressources/outils/dislocker/download/)

```sh
sudo mkdir /media/bitlocker /media/mount

sudo apt-get install libfuse-dev

cd dislocker/src

# Ubuntu 14.04 or before
sudo apt-get install gcc cmake make libfuse-dev libpolarssl-dev ruby-dev

# Ubuntu 16.04
sudo apt-get install gcc cmake make libfuse-dev libmbedtls-dev ruby-dev


cmake .
sudo make
sudo make install
```
[http://askubuntu.com/questions/617950/use-windows-bitlocker-encrypted-drive-on-ubuntu-14-04-lts](http://askubuntu.com/questions/617950/use-windows-bitlocker-encrypted-drive-on-ubuntu-14-04-lts)

### 2. Script for auto unlock

```sh
echo (unlock password) | sudo -S dislocker -r -V /dev/sdb1 -u -- /media/bitlocker
echo (root password) | sudo -S -i
cd /media/bitlocker/
mount -o loop dislocker-file /media/mount
```
[http://askubuntu.com/questions/727977/how-to-automate-dislocker-process](http://askubuntu.com/questions/727977/how-to-automate-dislocker-process)