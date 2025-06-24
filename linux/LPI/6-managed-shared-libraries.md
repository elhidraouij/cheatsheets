# LPI

## Manage shared libraries

### Static libraries vs shared libraries

_Static libraries_ are merged with programs at link time. Thus, the program contains the libraries having no dependencies.

_Shared (or dynamic) libraries_, the linker takes care that the program references the libraries correctly. The program is lighter and the shared libraries are loaded only once in the RAM.

### Libraries convention

_Shared libraries_ follow the `[lib_name].so.[version]` pattern.

_Static libraries_ follow the `[lib_name].a` pattern

Common locations for shared libraries :
- `/lib`
- `/lib32`
- `/lib64`
- `/usr/lib`
- `/usr/local/lib`

### Dynamic linker

The references are resolved by the dynamic linker `ld.so` or `ld-linux.so`. To do so, it searches in directories specified by the _library path_ in the `/etc/ld.so.conf` file or `/etc/ld.so.conf.d` directory.

The `*.conf` file in `/etc/ls.so.conf.d/*.conf` include the absolute path to the shared library directories.

`sudo ldconfig -v`, to list the library version numbers and the link created

The `LD_LIBRARY_PATH` environment variable can be used to add new paths to shared libraries with `export LD_LIBRARY_PATH=/usr/local/mylib:/usr/local/other`.

To make the changes persistent, then write it in `/etc/bash.bashrc` or `~/.bashrc`.