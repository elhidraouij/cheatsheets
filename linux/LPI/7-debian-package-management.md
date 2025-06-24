# LPI

## Debian package management

### Debian Package Tool (`dpkg`)

`dpkg -i [package_name]`, to install or update a `.deb` package  
`dpkg -r [package_name] [package_name]...`, to remove a package unless if there is a package who depends on it  
`dpkg -P [package_name]`, to remove the package and its configuration files  
`dpkg -I [package_name]`, to inspect a `.deb` package  
`dpkg --get-selections`, list every package installed by `dpkg` on the system  
`dpkg -L [package_name]`, to get a list of every file installed by a package  
`dpkg-query -S [filepath]`, to know which package owns this specific file  
`dpkg-reconfigure [package_name]`, to reconfigure an installed package

### Advanced Package Tool (apt)

Many utilities interact with APT :
- `apt-get` to download, install or remove package from the system
- `apt-cache` to perform operations like searches in the package index
- `apt-file` to search for files inside packages

#### a. `apt-get` commands

`apt-get update` or `apt update` to update the package index

`apt-get install [package_name]` to install a package  
`apt-get remove [package_name]` to remove a package  
`apt-get purge [package_name]` to remove a package and its configuration file  
`apt-get upgrade [package_name]` to upgrade a package

`apt-get install -f [package_name]` to fix a broken dependency

#### b. `apt-cache` commands

File are downloaded to a local cache located under `/var/cache/apt/archives` and `/var/cache/apt/archives/partial`.

To delete the cache that can get quite large, use `apt-cache clean` or `apt clean`

`apt-cache search [package_name]`, to search for a specific package on the package index

`apt-cache show [package_name]` to display detail about a package

### c. Sources list

The sources are listed in the `/etc/apt/sources.list` file

A line looks like this :
```bash
deb http://us.archive.ubuntu.com/ubuntu disco main restricted universe multiverse
```

The components :
- Archive type
- URL -> url of the repository
- Distribution -> distribution codename
- Components :
    - `main` -> officialy supported, open-source package
    - `restricted`
    - `universe` -> community maintained open-source software
    - `multiverse`

To add a new repository add a new line in the `/etc/apt/sources.list` file or in the `/etc/apt/sources.list.d/*.list`, save it and reload apt with `apt-get update`

