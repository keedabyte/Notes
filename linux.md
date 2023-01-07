# Linux Tutorial

## File structure of linux
    1. In linux everything is a file.
    2. BASH - Bourne Again Shell is the default shell for linux
    3. We have more shells like zsh, fish, bat, dog, giraffe, powershell(pwsh) etc.

- ```/```
    - This is the root direcotry of the linux
- ```/bin```  
    - All the binary files resides here
    - ex. ls, man etc.
- ```/sbin```
    - Super binary files resides here
    - ex. adduser etc.
- ```/local```
    - Command binaries created by user. 
    - Similar to ```/bin``` or ```/sbin```
- ```/var```
    - Contains log files
- ```/tmp```
    - Contains temporary files
- ```/lib```
    - More shared library files
- ```/home```
    - All the user related things
- ```/dev```
    - Stands for devices
    - Here we have vda, vda1 -> virtual disk
    - sda, sda1 -> disk
- ```/etc```
    - etsy files(configuration files of system or software application.)
- ```/media```
- ```/mnt```
- ```...```

## Commands
### Note
    1. Our terminal starts with something like "user@hostname$" or "user@hostname#"
    2. If the last symbol is "$" means you are logged in as a user
    3. If the last symbol is "#" means you are logged in as root

### Basic commands
```bash
id   # tells about you(user)

hostname    # tells the hostname

uname    # username(Linux)

ifconfig    # networking stuffs

ip    # more networking stuffs

netstat    # status of your network

ss    # session stuffs

ps    # process stuffs

who    # tell are you logged in as (whoami)

env    # prints the environments variables

lsblk    # list blocks

lsusb    # are there any usb plugged in

lsof    # lists all the open files

man lsblk    # prints the manual page for lsblk command

lsblk --help    # prints the help summary, we can also use -h instead of --help

apropos usb    # If we have some idea what we were doing and forget the comand then it helps

apropos compress
```

### Listing the files
```bash
ls    # used to list the content of the current directory

ls --ignore=snap    # listout all the files except snap one, we can pass any pattern in place of snap

ls --ignore snap

ls --ignore=snap --ignore=home

ls --ignore=b*    # ignore all which starts with letter b

ls -lash    # show all files in the human readable

ls -lash /usr    # list all the content inside /usr

man ls    # prints the man page of the ls command, for more flags use "ls --help"
```

### Some shortcuts of the bash terminal
- ```CTRL + A``` takes you to the beginning of the line
- ```CTRL + E``` takes you to the end of line
- ```CTRL + K``` yank everything after the cursor
- ```CTRL + U``` yank everything before the cursor
- ```CTRL + Y``` paste
- ```CTRL + R``` reverse search through history