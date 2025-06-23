# LPI

## Manage shared libraries

### Static libraries vs shared libraries

_Static libraries_ are merged with programs at link time. Thus, the program contains the libraries having no dependencies.

_Shared (or dynamic) libraries_, the linker takes care that the program references the libraries correctly. The program is lighter and the shared libraries are loaded only once in the RAM.

### Libraries convention

_Shared libraries_ follow the `lib[name].so.[version]` pattern.

_Static libraries_ follow the `lib[name].a` pattern

Common locations for shared libraries :
- `/lib`
- `/lib32`
- `/lib64`
- `/usr/lib`
- `/usr/local/lib`

