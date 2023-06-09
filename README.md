These are instructions to install Vagrant on Apple Silicon machines.

I have verified that these instructions work on an Apple Macbook M1 pro.

1. Make sure QEMU is installed, if not:

    `brew install qemu`

2. Install the QEMU vagrant plugin:

    `vagrant plugin install vagrant-qemu`

3. Prepare a Vagrantfile, and start:

    `vagrant up --provider qemu`

4. Shutdown the VM

    `vagrant halt [name[id]]`

## Troubleshooting
If you encounter an error of the following:

>"Vagrant cannot forward the specified ports on this VM, since they collide with some other 
   application that is already listening on these ports"

Use the following command to check what application is running on this port:

  `lsof -i | grep LISTEN`

Find the pid of the application and kill it:

  `kill <pid>`

Run `vagrant up` again or in this repository's case, the `./execute.sh` file.

To do custom networking configuration, ie. set a hostname for the VM, refer to [2]

## References
1. https://github.com/ppggff/vagrant-qemu
2. How to configure netwroking in vagrant - https://ostechnix.com/how-to-configure-networking-in-vagrant/
