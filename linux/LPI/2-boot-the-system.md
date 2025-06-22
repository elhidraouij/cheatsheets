# LPI

## Boot the system

The most popular bootloader is GRUB _(Grand Unified Bootloader)_. When called, it displays the list of the available operating systems.

From this point, it is possible to choose which kernel to boot and to pass parameters to it.

Most useful kernel parameters are :
- `acpi` - _off or on_ - Control power management, automatic device connections...
- `init` - System initiator, the first process to be run
- `systemd.unit`
- `mem` - Sets the amount of RAM available for the system. ie, you can write `mem=512M`, `mem=1G`, `mem=1024K`
- `maxcpus` - Limits the number of processors visible to the system. Ie, `maxcpus=2`
- `quiet` - Hides boot messages
- `vga`
- `root` - Sets the root partition. Ie, `root=/dev/sda3`