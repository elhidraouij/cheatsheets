# LPI

## Work on CLI

### Getting system information

`pwd`, to display the current directory  
`touch`, to create a new file  
`ls`, to list the current directory content  
`uname -a`, to display information about the Linux system  

`man`, to display documentation of a command  
`apropos kernel`, to list all available commands  
`apropos kernel | grep [package_name]`, to filter in the list of all available commands  
`type [command]` to get basic documentation  
`which [command] [other_command]` to get absolute location of a command 

### Finding your env variables

`env`, top list all environment variables  
`env | grep [env_name]`, to filter between env variables  
`echo [something_to_print]`, to print the thing, ie `echo $PATH` to print the `PATH` env variable

`export my_var=test`, to create a new env variable  
`unset my_var`, to delete a env variable

