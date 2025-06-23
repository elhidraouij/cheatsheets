# LPI

## Design hard disk layout

### _disk_ vs _partitions_ vs _filesystems_ vs _volumes_

A _disk_ is a physical container of data

A _partition_ is a logical subset of the physical _disk_.

Each _partition_ has a _filesystem_. The _filesystem_ describe the way the information is stored on the _disk_.

_Logical volumes_ abstract the limitations of a physical device and let you workwith pool of _disks_.

### Mount points

The mount point must exist before mounting a filesystem.

If the mount point exists and contains files, those files will be unavailable until you unmount the filesystem.

`/mnt` was traditionnally the directory where the external devices would be mounted

`/media` is now the default mount for removable media (USB key, disks, memory card...). They are automatically mounted under `/media/[username]/[device_label]`.

The best practice is to manually mount filesystem under `/mnt`.