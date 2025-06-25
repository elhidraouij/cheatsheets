# LPI

## Linux as a virtualized guest

### Types of virtual machines

- Fully Virtualized -> The machine does not know it is a virtual machine. No additonal drivers needs to be installed within the guest
- Paravirtualized -> The machine know it is virtualized and use a special kernel and drivers that enhance performances
- Hybrid -> Use paravirtualized drivers on unmodified operating systems

### `libvirt` virtual machine

A virtual machine consists of a group of files. It is a XML file combined with an associated hard disk image who contains the installation of the operating system.

`ls -l /etc/libvirt/qemu`, to list XML files  
`ls -l /var/lib/libvirt/images`, to list hard disk images

### Types of disk images

-  COW -> Copy-on-write (or _thin-provisioning_ or _sparse images_) is a method where a disk file is created with a pre-defined upper size limit. The disk image only increases as new data is written to the disk.
- RAW -> A _raw_ or _full_ disk type is a file that has all of its space pre-allocated. Ie, 10GB raw disk image will consumes 10GB of actual disk space on the hypervisor which benefits performances.

### Working with Virtual Machine Templates

#### a. D-Bus Machine ID

Linux installations utilize a machine identification number generated at install time called _D-Bus machine ID_. But if a virtual machine is cloned to be used as a template, you need to make sure that a new D-Bus machine ID is created so that the hypervisor get directed to the appropriate guest system.

`dbus-uuidgen --ensure`, to make sure that a D-Bus machine ID exists for the running system

`dbus-uuidgen --get`, to desiplay the D-BUS machine ID

It is crucial to make sure that no more than one Linux machine share the same D-Bus machine ID

The D-Bus machine ID is located at `/var/lib/dbus/machine-id` who is simbolically lnked to `/etc/machine-id`

To change this id :
```bash
sudo rm -f /etc/machine-id
sudo dbus-uuidgen --ensure=/etc/machine-id
```

### Securely accessing guests in the cloud

A linux system that resides in the cloud would have a OpenSSH server running, while administrator would use a OpenSSH client

Run `ssh-keygen` to create a public and private SSH key pair. The private key remains on the admin's local system in `~/.ssh/` and the public key gets copied to the remote cloud system with `ssh-copy-id -i [public_key] [user]@[server]`.

After this, the public key will be recorder in the `~/.ssh/authorized_keys` of the cloud server.

### Preconfiguring cloud systems

The `cloud-init` utility associated with `yaml` configuration files and predefined image allows administrator to preconfigure network settings, software package selections, ssh key configuration, user account creations, locale settings and a lot of other options...

`cloud-init` is not just for virtual machines, it can also be used to preconfigure containers