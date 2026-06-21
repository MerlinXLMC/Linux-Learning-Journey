# File Permissions

## Definition:

File permissions determine who is allowed to access a specific file.
File permissions are divided into three categories of users:

- Owner: The user who owns the file.  
- Group: A group of users assigned to the file.  
- Others: Everyone else (users who are neither the owner nor in the group).

## Why Are File Permissions Important?

File permissions are crucial because they protect files from unauthorized access and misuse. Imagine an office where anyone can freely enter every room without restrictions—this would inevitably lead to chaos.  
That’s why file permissions exist: to define precisely who can access a file and within what limits.

## The Three Types of Permission:

## There are three basic permission types in Linux:

- Execute (x): Allows a user with this permission to run a script or executable file.  
- Write (w): Grants the ability to modify or edit the file’s contents.  
- Read (r): Permits viewing or reading the file’s contents.  
- Denied (-): Indicates no permission—neither execute, write, nor read access is granted.

## Numeric Notation for File Permissions:

Permissions can also be represented using numbers, which is straightforward: simply add up the values below:

- Execute = 1  
- Write = 2  
- Read = 4

Example: 624

- 6 (Owner): Read (4) + Write (2) = 6 → can read and write.  
- 2 (Group): Write (2) = 2 → can only write.  
- 4 (Others): Read (4) = 4 → can only read.

## Comands Related to File Permissions:

- chmod: Used to change a file’s permissions. Only the file owner or superuser (root) can use this command.  
- chown: Changes the ownership of a file to another user or group.

## My File Permission Experiments:

[Input]:

1. Create a new file named rahasia.txt and add any text to it.  
2. Change its permissions to 600 using numeric notation.  
3. Verify with ls -l, interpret the symbolic notation, and confirm it matches your expectations.  
4. Create another file named publik.txt.  
5. Set its permissions to 644.  
6. Create a simple script file that displays any text, then assign it 755 permissions so it becomes executable.  
7. Run the script to verify the permissions work correctly.  
8. Change the script’s permissions to 700, then try running it again. Does it still work? Why or why not?

[Output]:

Report issues at https://termux.dev/issues
~ $ ubuntu
root@localhost:~# cd /
root@localhost:/# ls -a
.                bin   learning      opt      sdcard   system_ext
..               boot  lib           proc     snap     tmp
.l2s             data  linkerconfig  product  srv      usr
.rock            dev   media         root     storage  var
Tempat-berlatih  etc   mnt           run      sys      vendor
apex             home  odm           sbin     system
root@localhost:/# cd Tempat-berlatih
root@localhost:/Tempat-berlatih# ls
 'File Permission'
root@localhost:/Tempat-berlatih# touch rahasia.txt
root@localhost:/Tempat-berlatih# nano rahasia.txt
root@localhost:/Tempat-berlatih#
root@localhost:/Tempat-berlatih# chmod 600 rahasia
chmod: cannot access 'rahasia': No such file or directory
root@localhost:/Tempat-berlatih# chmod 600 rahasia.txt
root@localhost:/Tempat-berlatih# ls -l
total 7
drwxr-xr-x+  3 root root 3440 Jun 19 16:48  'File Permission'
-rw-------+  1 root root   34 Jun 19 16:52  rahasia.txt
root@localhost:/Tempat-berlatih# nano publik.txt
root@localhost:/Tempat-berlatih#
root@localhost:/Tempat-berlatih# chmod 644 publik.txt
root@localhost:/Tempat-berlatih# nano file skrip skrip.sh
root@localhost:/Tempat-berlatih# ls -a
 .    'File Permission'   publik.txt    skrip
 ..   file                rahasia.txt   skrip.sh
root@localhost:/Tempat-berlatih# rm skrip
root@localhost:/Tempat-berlatih# ls
 'File Permission'   file   publik.txt   rahasia.txt   skrip.sh
root@localhost:/Tempat-berlatih# chmod 755 skrip.sh
root@localhost:/Tempat-berlatih# ./ skrip.sh
bash: ./: Is a directory
root@localhost:/Tempat-berlatih# ./skrip.sh
./skrip.sh: line 1: loh: command not found
root@localhost:/Tempat-berlatih# chmod 700 skrip.sh
root@localhost:/Tempat-berlatih# ./skrip.sh
./skrip.sh: line 1: loh: command not found
root@localhost:/Tempat-berlatih#

...

(Note: The script failed to run properly because its content was invalid—"loh" is not a valid shell command. However, the permission changes themselves were applied correctly. With proper script syntax, both 755 and 700 would allow execution by the owner; 755 additionally permits group and others to read and execute, while 700 restricts all access to the owner only.)
