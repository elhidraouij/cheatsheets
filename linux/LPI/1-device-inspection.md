# LPI

## Device Inspection

To identify connected devices in a Linux system :
-  `lspci`, to display currentli connected device to the PCI _(Peripheral Component Interconnect)_ bus.
- `lsusb`, to display USB _(Universal Serial Bus)_ connected devices.

### Focus on `lspci`

`lspci -s [device_id] -v`, display detail of a specific hardware component.

The driver in use can be identified in the line `kernel driver in use`.

Another way to verify kernel module in use is provided by the option `-k` -> `lspci -s [device_id] -k`.

### Focus on `lsusb`

`lsusb -v -d [device_id]`, display detail of a specific device.

`lsusb -t` show the hierarchical tree of the usb usage. If a matching module is known, then at the end of the line it should be written in `Driver=`

To verify which device is corresponding, `lsusb -s [bus_id]:[device_id]`.

### Modules management

`lsmod`, display all modules

To unload a module and its relatied modules as long as it is not used by a running process `modprobe -r [module_name]`

To get details about a module `modinfo [module_name]`.  
To know more about its parameter `modinfo -p [module_name]`.

### Information Files and Device Files

Those kind of information are stored in special files in `/proc` and `/sys` directories who are RAM space only available during runtime.

To inspect hardware, here are the most important files :
- `/proc/cpuinfo` -> informations about the CPUs found by the OS.
- `/proc/interrupts` -> List of numbers of the interrupts per IO device for each CPU.
- `/proc/ioports` -> Lists currently registered Input/Ouptut port regions in use.
- `/proc/dma` -> Lists the registered DMA _(Direct Memory Access)_ channels in use.

The `/dev` directory is related to storage devices.

_udev_ process is in charge of detecting and applying the corresponding changes in the `/dev` directory whether it is at booting time or running time _(Hotplug)_.