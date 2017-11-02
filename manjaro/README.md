# Manjaro

## Requirements

### Install ansible

    sudo pacman -S ansible
    sudo ansible-galaxy install rvm_io.ruby

### Mount the data folder

    ls /dev/disk/by-uuid # Find the uuid you need
    sudo mkdir /mnt/data

Edit the /etc/fstab file with something like this:

    UUID=your-uuid /mnt/data ext4 defaults,noatime

Then mount the volume using

    sudo mount -a

## Running the playbooks

Run the playbooks using the following command:

    ansible-playbook -i inventory playbook.yml -K

The playbooks can be ran in the following order:

* data.yml
* shell.yml
* git.yml
* ssh.yml (you can copy your keys from elsewhere if you wish)
* keychain.yml
* utils.yml
* vim.yml

Other playbooks

* docker.yml
* go.yml
* virtualbox.yml

## Not automated

* Change dolphin options
* Copy the .firefox directory (or signup to Sync)
* Copy the .config/Clementine directory

### Change Konsole & Yakuake

General > Command : /bin/bash -l
Appearance > Color Scheme > Solarized
Scrolling > Scrollback > Unlimited Scrollback

## TODO

* Install the Sophos antivirus
