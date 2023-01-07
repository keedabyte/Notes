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
clear    # clear the terminal

sudo -s    # goto super user mode

pwd    # tells the present working direcotry

id   # tells about you(user)

hostname    # tells the hostname

uname    # username(Linux)

uname -a

arch    # displays the architecture of computer

free    # display the amount of free and used memory of system

ifconfig    # networking stuffs

ip    # more networking stuffs

netstat    # status of your network

ss    # session stuffs

ps    # process stuffs

who    # tell are you logged in as (whoami)

env    # prints the environments variables

printenv    # same as above command

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

ls -lS    # sort by size of the file

ls -d */    # lists only directories

ls -R    # recursively shows directories

ls file*.txt    # mathces 0 or more characters in place of *(wildcard)

ls file?.txt    # mathces exactly one character in place of ?

ls --ignore=snap    # listout all the files except snap one, we can pass any pattern in place of snap

ls -I snap    # we can use -I instead of --ignore

ls --ignore=snap --ignore=home

ls --ignore=b*    # ignore all which starts with letter b

ls -lash    # show all files in the human readable

ls -lash /usr    # list all the content inside /usr

ls > file.txt    # prints all output to file.txt(doesn't append)

ls >> file.txt    # appends the output to file.txt

man ls    # prints the man page of the ls command, for more flags use "ls --help"
```

### Some shortcuts of the bash terminal
- ```CTRL + A``` takes you to the beginning of the line
- ```CTRL + E``` takes you to the end of line
- ```CTRL + K``` yank everything after the cursor
- ```CTRL + U``` yank everything before the cursor
- ```CTRL + Y``` paste
- ```CTRL + R``` reverse search through history

### More commands
```bash
cd    # go to the home directory(~), same as "cd ~"

cd /home    # change the directory to home

cd ..    # change the working directory one level up

tail <filename>    # prints the last 10 line of the file

tail -f <filename>    # keeps on running and shows the live content if any new added, hit CTRL + C to exit.

which firefox    # tells the location of firefox

whereis firefox    # similar to above command

cal    # calender
ncal   # similar as above
ncal 2016    # 2016 calender
ncal 2 2016    # February month 2016 calender
ncal -3    # previous 3 months calender

date    # display current date and time
date -s "11/20/2003 12:48:00"   # setting the date and time
```

### Collection of folders and files
```bash
tar -cf archive.tar textfile.txt folder1    # Creates a tar file and place textfile .txt and folder1 together but **It is not in the compressed form

tar -zcf archive.tar.gz textfile.txt folder1    # Now this is in compressed form

tar -xzf archive.tar.gz -C hello    # Extracting into hello folder, hello folder must be exist
```

### More on directories and files
```bash
touch <filename>    # Creates an empty file with the given name

touch file{1,2,3,4}.txt    # Creates file like file1.txt, file2.txt etc.

touch file-{nm, gs,}.txt    # similar to above command, file-nm.txt, file-gs.txt, file-.txt

touch file{1..30}.txt    # file1.txt, file2.txt ... upto file30.txt

touch file{a..z}.txt    # similar to above

touch file{a..z..2}.txt    # skip(gap) is now set to 2, eg: a, c, e..

touch file{z..a..2}.txt    # similar to above

echo {a..z}{1..5}    # prints all permutations a1, a2, a3 etc.

mkdir image    # creating new directory with name image

mkdir image/image1    # for creating image1, image must be exists

mkdir -p image/image1/image2    # forcefully creates the folders, doesn't matter if any one of them exists or not

mkdir -p names/{john,tom,bob}    # creates 3 directories inside names

rmdir a/b/c/d    # delete d directory only

rmdir -p a/b/c/d    # delete all folders, use -v flag to show more information

rm a/b    # remove file b

rm -rv a/b    # remove everything

rm -r a    # enough to delete all child
```

### copying, moving and renaming
```bash
cp file1.txt file2.txt    # content of file1 will be copied to file2, if file2 doesn't exists it creates

cp file1.txt dir1    # copy file to dir1 directory

cp file1.txt file2.txt dir2    # copy multiple files in dir2 directory, overrides if any exists already

cp -i file1.txt file2.txt dir2    # will confirm by interacting, dir2 could be absolute or relative path

cp ../file1.txt ../file2.txt .    # copying relative or absolute path in present directory

cp -R dir1 dir2    # all content of dir1 will be copied to dir2, if the destination doesn't exist it creates

cp -vR dir1 dir2    # if dir2 exists, it copies dir1 itself inside dir2

man cp    # know all about cp command

mv file1.txt file2.txt    # renaming the file1 to file2

mv file1.txt dir1/    # move to directory dir1, if file1.txt already exists in dir1 it will override

mv -i file1.txt dir1/    # interactive mode

mv dir1 dir2    # move dir1 to dir2, if directory doesn't exist simply rename it, use -v for more information 
```

### cat command
```bash
cat file.txt    # shows the content of the file

cat file1.txt file2.txt    # shows the content of both files

cat -b file.txt    # shows only non-blank lines

cat -n file.txt    # also shows each line number including blank lines

cat -S file.txt    # if we have multiple blank lines it shows only once

cat -E file.txt    # adds $ sign at the end of every line

man cat    # shows the man page of cat command
```

<!-- <details>
<summary>Redirection using cat command </summary>

```bash
cat > test.py    # start writing the content into test.py file, use CTRL + D to end this or save the changes

cat >> test.py    # start appendnig the content into test.py file, use CTRL + D to end this or save the changes

cat file1.txt file2.txt > file3.txt    # combine and transfer to new file

cat file1.txt >> file2.txt    # appends file1 data to file2
```
</details> -->

### redirection using cat command
```bash
cat > test.py    # start writing the content into test.py file, use CTRL + D to end this or save the changes

cat >> test.py    # start appendnig the content into test.py file, use CTRL + D to end this or save the changes

cat file1.txt file2.txt > file3.txt    # combine and transfer to new file

cat file1.txt >> file2.txt    # appends file1 data to file2
```

### Reading the file with less command
```bash
less big.txt    # read the big file
# use up-key, down-key, SHIFT + G -> end of file, 1g -> goto top
# /book -> search book up to down, n for next and p for previous
# ?book -> search book down to up, n for next and p for previous
# q -> quit from less command
man less    # manual page for less command
```

### Process related
```bash
top    # show realtime processes with process id(PID)
# press s -> and give refresh time
# press i -> if any process is idle will not displayed here
# press k -> give pid to kill the process
# press q -> quit the top command

pidof unity-control-center    # gives the process id of this service

yes > /dev/null &    # & is used at the end to run the process in background

ps -ux    # list all the processes ID

ps -aux    # list all the process used by all users

ps -U sanjay    # list all processes of sanjay user only

ps -C gnome-terminal    # list all information about gnome-terminal process

ps aux | grep yes    # seach for "yes" in all running processes

kill -l    # lists the all kill signals

kill -KILL <processid>    # kills forcefully(not recommended)

kill -9 <processid>    # kill the process by passing the process id

kill -SIGKILL <processid>    # 9 -> SIGKILL(same command as above)
```

### Memory related
```bash
df    # tells us about how much space is used or free in our machine

df -h    # human readable form

du    # tells us about disk space used by files

cd Desktop/
du -h

du -sh    # summary with human readable form

du -sh /etc/    # with directories

sudo du -sh    # if we require to do so

free    # displays the total amount of free and used physical and swap memory in the system as well as buffer used by the kernel

free -b    # shows in bytes
# -k -> kilobytes
# -m -> megabytes
# -g -> gigabytes
# -tera -> terabytes

watch free -m    # watch command is used to show repeatedely the output of any commands(free in this case), watch can be used with any commands

watch -n 1 free -m    # setting the watch frequency to 1 second, we can pass in decimal as well(0.1)
```

### File content related
```bash
head filename    # shows the first 10 lines of data of the file
head -n3 filename    # shows first 3 lines
head -3 filename
head file1 file2    # for multiple files

tail filename    # shows last 10 lines of data of the file
tail -n3 filename
tail -3 filename
tail -f filename    # it will not go out of the terminal

find /home/programming/ -name file.*    # find the file in given directories

find / -name dmesg
sudo find / -name dmesg
find /home/ -mtime -3    # will show all files within past 3 days.

wc file.txt    # word count(number of lines, number of words, number os characters)
wc -c file.txt    # count only characters
# -l -> only lines
# -w -> only words
# -L -> number of characters in longest line

```

### Changing permissions
```bash
chmod o+x file    # (o, g, u, a) -> (others, group, user, all)
# (+, -) -> (add permission, remove permission)
# (r, w, x) -> (read permission, write permission, execute permission) 

chmod ug=rwx file    # setting read, write execute permissions to user and group

chmod u+rw, g=rw, o+r file    # adding read, write permission to user, setting read, write permission for group, adding read permission for others

chmod ugo-rwx file    # removing all premission from all

chmod a-rwx file    # same as above command

# We can also user octal or numerial permission
chmod 012 file    # 000(rwx) for user, 001 for group, 010 for others
```

### Combining commands
```bash
ls; pwd    # using semicolon
date; cal; pwd    # sequence matters

ls && pwd && date && cal    # using &&, sequence matters
# ; -> runs every command reagardless of failure of particular command
# && -> stop executing if any fails

ls || pwd    # logical OR operation(if first one success then it will not go for others)

sleep 10    # sleeps 10 seconds
sleep 10 &    # sleeps 10 seconds in the background 
```