# LPI

## RunLevels

The service manager, wether it is `SysVinit` or `systemd`, is the first program launched by the kernel during the boot process, so its PID is always 1.

### _SysVinit_ service manager

`SysVinit` provide runlevels numbered from `0` to `6`:
- Runlevel 0 : System shutdown
- Runlevel 1 or single : Single user mode, no network or other non essential capabilities
- Runlevel 2, 3 or 4 : Multi user mode
- Runlevel 5 : Multi user mode with graphical login
- Runlevel 6 : System restart

### _systemd_ service manager

#### a. Units description

`systemd` manage system resources and services, referred as units.

Here are the type of systemd units :
- `service`
- `socket` : it can be a filesystem socket or a network socket. All socket is linked to its corresponding service
- `device`
- `mount` : a mount point in the filesystem
- `automount` : a mount point in the filesystem but mounted automatically. All `automount` unit has its linked `mount` unit.
- `target` : a group of unit managed as a single unit
- `snapshot`

#### b. `systemctl` commands

`systemctl start [service]` to start a service  
`systemctl stop [service]` to stop a service  
`systemctl restart [service]` to stop and start a service at once  
`systemctl status [service]` get the status of the service

`systemctl enable [service]`, the service will be loaded during the system initialization  
`systemctl disable [service]`, the service will not start with the system 

`systemctl is-active [service]`, show if service is running or not  
`systemctl is-enabled [service]`, show if service is enabled or not

`systemctl isolate [target]` alternates between different targets.  
`systemctl set-default [target]` to set default target