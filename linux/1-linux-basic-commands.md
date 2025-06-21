# Linux system cheatsheet

## Basic commands

### 1. Move in your file system

#### a. Perceive your system

- Display the current directory: `pwd`
- Display the content in the current directory: `ls`
- Display every content, even the hidden files: `ls -a`
- Display detailed content: `ls -l`

#### b. Move into your system

- Change directory: `cd`  
- Go to home dir: `cd ~`

### 2. Create, copy, move and delete file / directories

- To create directory: `mkdir [dir_name]`
- To create a file: `touch [file_name]`
- To copy a file: `cp [src] [dst]`
- To move a file: `mv [src] [dst]`
- To delete a file: `rm [filte_path]`

### 3. Display and kill processes

- To display all processes running on your system: `ps -aux`
- To kill a process: `kill [pid]`
- Brutally kill a process: `kill -9 [pid]`

### 4. Manage permissions

#### a. The digits patterns

Three digits going from 0 to 7 modelize your access rights :
- The first is for the owner of the file _(=u)_
- The second for the group of the file _(=g)_
- The third for the other users _(=o)_

#### b. Meaning of the digits

Meaning of the digits :
- `4` : read
- `2` : write
- `1` : execute

You can add them up, to know what are the applied access rights.  
In example, _6_ equals _2 (write)_ + _4 (read)_ which means that the corresponding category has both writing and reading but not executing access on the file/directory.

### Change the access rights

#### a. Manage permissions with _chmod_

- To display the access rights of your files: `ls -l`
- To change the access rights following the three digits patterns: `chmod [xxx] [file_name]`, ie `chmoed 764 /home/filename.txt`
- User has all access, group can only read, other can't do anything: `chmod u=rwx,g=r,o= file.txt`

#### b. Manage ownerships

- Set the owner of file.txt to be alice: `sudo chown alice file.txt`
`sudo chown alice:user file.txt`
- Set the group of file.txt to be user: `sudo chgrp user file.txt`

### 5. SUID, GUID, StickyBit

- The _SUID_ bit means that the file will be executed as the owner
- The _GUID_ bit means that the file will be executed as the group
- The _StickyBit_ bit means that the file can only be delete by either the owner of the file or the root

`ls -l` allow you to display wether any of this bits is activated or not

### 6. Managing network

- To manage the network on old systems: `ifconfig`
- To maange the network on recent systems: `ip`
- To display networking stats on old systems: `netstat`
- To display networking stats on recent systems: `ss`
- To debug connectivity: `ping`
- To describe the packet taken path: `traceroute`

### 7. Manage users and groups

- To display info on a specific user: `id` 
- Display informations on the user elhidraouij: `id elhidraouij`

#### a. Create, edit and delete users

- To create a new user: `useradd [username]`, ie to create the user elhidraouij type `useradd elhidraouij`
- To edit a user  `usermod [username]`, ie to add the user elhidraouij in the sudo group `usermod -aG sudo elhidraouij`
- To remove a user `userdel [username]`, ie to delete the user elhidraouij `userdel elhidraouij`
- To change the password of a user: `passwd [username]`, ie to change the password of the user elhidraouij type `passwd elhidraouij`. The system will ask you to type two times the password before replacing it.

#### b. Create, edit and delete groups

- To create a new group: `groupadd [group_name]`, ie to create a group called devops `groupadd devops`
- To edit a group : `groupmod`, ie `groupmod -n automationers devops` to rename the group devops to automationers
- To delete a group `groupdel [group_name]`, ie `groupdel devops` will delete the devops group

- To administer the group members: `gpasswd`, ie:
    - `gpasswd -a elhidraouij devops` add the user elhidraouij to the devops group  
    - `gpasswd -d elhidraouij devops` remove the user elhidraouij to the devops group
