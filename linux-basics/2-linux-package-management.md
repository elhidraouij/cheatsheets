# Linux

## Package Management

### 1. Packages management for Debian / Ubuntu with APT

#### a. Install and remove

- Install a package : `apt install [package]`
- Remove a package :
    - keep configurations files : `apt remove [package]`
    - remove with configurations files : `apt purge [package]`
    - remove unused dependencies : `apt autoremove`

#### b. Update a package

- Update the index : `apt update`
- Update the packages : `apt upgrade`
- Update package and dependencies : `apt full-upgrade`

#### c. Search and detail

- To look for a package : `apt search [package]`
- To display the package details : `apt show [package]`

### 2. Packages management for Redhat / Fedora with dnf

#### a. Install and remove

- Install a package : `dnf install [package]`
- Remove a package : `dnf remove [package]`
- Install a group of packages : `dnf group install [group_name]`

#### b. Update a package

- Display updatable packages : `dnf check-update`
- Update the packages : `dnf upgrade`

#### c. Search and detail

- To look for a package : `dnf search [package]`
- To display the package details : `dnf info [package]`
- List available package group: `dnf group list`
- Display the package group details : `dnf group info [group_name]`