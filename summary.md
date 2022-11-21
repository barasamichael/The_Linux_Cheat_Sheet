## Linux Commands Cheat Sheet

### Download Managers
Command | Description
------- | -----------
wget | Non-interactive download of files from the web

### File Management
Command | Description
------- | -----------
touch | Change file times
stat | Display file or file system status
cp | Copy files and directories
mv | Move/rename files and directories
rm | Remove files and directories
ln | Create hard and symbolic links

### Shell Navigation
Command | Description
------- | -----------
pwd | Print name of current working directory
cd | Change directory
ls | List directory contents

### Searching for Files
Command | Description
------- | -----------
locate | Find files by name
find | Search for files in a directory hierarchy
xargs | Build and execute command lines from standard input

### Disk Management
Command | Description
------- | -----------
df | Report file system disk system usage
ncdu | See what directories are using your disk space (Curses-based version of du)
mount | Mount a file system
umount | Unmount a file system
fsck | Check and repair a file system
fdisk | Manipulate disk partition table
mkfs | Create a file system
dd | Convert and copy a file
genisoimage (mkisofs) | Create an ISO 9660 image file
wodim (cdrecord) | Write data to optical storage media
md5sum | Calculate an MD5 checksum

### Package Management
Distribution | Low-level tools | High-level tools
------------ | --------------- | ----------------
Debian-style | dpkg, pkg | apt, apt-get, aptitude, apt-cache
Fedora, Red Hat Enterprise Linux, CentOS | rpm | yum, dnf

### Networking
Command | Description
------- | -----------
ping | Send an ICMP ECHO_REQUEST to network hosts
traceroute | Print the route packets trace to a network host
ip | Show/manipulate routing, devices, policy routing, and tunnels
netstat | Print network connections, routing tables, interface statistics, masquerade connections, and multicast memberships
ftp | Internet file transfer program
ssh | OpenSSH SSH client (remote login program)

### Environment Management
Command | Description
------- | -----------
printenv | Print part or all of the environment
set | Set shell options
export | Export environment to subsequently executed programs
alias | Create an alias for a command

### Processes Management
Command | Description
------- | -----------
ps | Report a snapshot of current processes
top | Display tasks
jobs | List active jobs
bg | Place a job in the background
fg | Place a job in the foreground
kill | Send a signal to a process
killall | Kill processes by name
shutdown | Shut down or reboot the system

### Common Utilities
Command | Description
------- | -----------
clear | Clear the terminal screen
history | Display or manipulate the history list
echo | Display a line of text
type | Display how a command name is interpreted
which | Display which executable program will be executed
help | Get help for shell builtins
man | Display a command's manual page
apropos | Display a list of appropriate commands
info | Display a command's info entry
whatis | Display one-line manual page descriptions
ls | List directory contents
cal | Display calendar of current month
date | Display current date and time

### File Manipulation
Command | Description
------- | -----------
cat | Concatenate files
sort | Sort lines of text
file | Determine file type
uniq | Report or omit repeated lines
grep | Print lines matching a pattern
wc | Print newline, word, and byte counts for each file
head | Output the first part of a file
tail | Output the last part of a file
tee | Read from the standard input and write to the standard output and files
less | View file contents

### User Management
Command | Description
------- | -----------
id | Display user identity
chmod | Change a file's mode
umask | Set the default file permissions
su | Run a shell as another user
sudo | Execute a command as another user
chown | Change a file's owner
chgrp | Change a file's group ownership
passwd | Change a user's password
whoami | display name of current user
groups | Display groups of current user
lastcomm | Display commands executed by user
exit | Terminate current user session
