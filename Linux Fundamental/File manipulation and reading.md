File Manipulation and Reading

I have learned about "File manipulation and reading." Through this, I gained additional knowledge such as commands, flags, and other related concepts.

Commands I've Learned:

- cat: Displays or reads a file's contents directly in the terminal. However, it has a drawback: if the file is very long, its content scrolls continuously without giving you time to read it properly.

- less:  
  While cat dumps the entire file content at once (making it hard to read), less provides a solution.  
  less allows navigation while viewing or reading file contents. For example:  
  - Up/down arrow keys scroll line by line.  
  - Spacebar jumps forward one page.  
  - b moves backward one page.  
  - /word searches for a specific word within the file.  
  - n finds the next occurrence of the searched keyword.  
  - q quits/exits less.

- head and tail:  
  If you only need to view a specific portion of a file without displaying everything at once:  
  - head: Shows the top part of a file.  
  - tail: Shows the bottom part of a file.  

  Examples:  
    head -n 5 /var/log/dpkg.log
  tail -n 5 /var/log/dpkg.log
  tail -f /var/log/dpkg.log
  
  - -n 5 means display 5 lines of the file.  
  - Without the -n flag, the default is 10 lines.  
  - The -f flag enables real-time output—continuously updating as new data is written to the file.

- touch:  
  A very brief and simple command.  
  touch creates an empty file.

- nano:  
  Similar to touch, but more powerful: nano can both create files and edit their contents interactively.

- cp:  
  Stands for "copy." Used to duplicate files or directories, often for backup purposes.  
  Flag:  
  - -r (recursive): Copies directories along with all their contents.

- mv:  
  Stands for "move." Used to rename files or move them to different locations.

- rm:  
  Stands for "remove." Used to delete files or directories.  
  Flags:  
  - -r: Deletes directories and all their contents recursively.  
  - -f (force): Deletes files without prompting for confirmation.  

  ⚠️ Be extremely careful with this command—Linux does not have a recycle bin!

Practice I Conducted

[Input]

1. Create a new directory named latihan-file inside your home directory.  
2. Create three empty files inside it: file1.txt, file2.txt, and file3.txt using a single command.  
3. Write different text into each file using nano.  
4. Display the contents of all three files at once using a single cat command.  
5. Copy file1.txt to the location ~/belajar/linux/dasar/.  
6. Rename file2.txt to catatan-penting.txt.  
7. Delete file3.txt.  
8. Verify the final result using ls -la.

[Output]

root@localhost:~# pwd
/root
root@localhost:~# mkdir latihan-file
root@localhost:~# cd latihan-file
root@localhost:~/latihan-file# touch file1.txt file2.txt file3.txt
root@localhost:~/latihan-file# ls -la
total 6
drwxr-xr-x+     2 root root 3440 Jun 14 13:34 .
drwx------+     7 root root 3440 Jun 14 13:33 ..
-rw-r--r--+     1 root root    0 Jun 14 13:34 file1.txt
-rw-r--r--+     1 root root    0 Jun 14 13:34 file2.txt
-rw-r--r--+     1 root root    0 Jun 14 13:34 file3.txt
root@localhost:~/latihan-file# nano file1.txt
root@localhost:~/latihan-file# nano file2.txt
root@localhost:~/latihan-file# nano file3.txt
root@localhost:~/latihan-file# cat file1.txt file2.txt file3.txt
Isi file1 text hohoho
Isi teks file2 hoho, tidak ada yang menarik ygy
Hoho, ini terakhir. File3 woiX

root@localhost:~/latihan-file# cp file1.txt /mnt/storage/Documents/Termux/Linux-Learning/Journey
cp: cannot create regular file '/mnt/storage/Documents/Termux/Linux-Learning/Journey': No such file or directory
root@localhost:~/latihan-file# ls -a
.  ..  file1.txt  file2.txt  file3.txt
root@localhost:~/latihan-file# /.
bash: /.: Is a directory
root@localhost:~/latihan-file# cd /.
root@localhost:/# ls -a
.      bin   home          mnt      root    storage     usr
..     boot  learning      odm      run     sys         var
.l2s   data  lib           opt      sbin    system      vendor
.rock  dev   linkerconfig  proc     sdcard  system_ext
apex   etc   media         product  srv     tmp
root@localhost:/# /~
bash: /~: No such file or directory
root@localhost:/# / ~
bash: /: Is a directory
root@localhost:/# cd / ~
bash: cd: too many arguments
root@localhost:/# cd /
root@localhost:/# pwd
/
root@localhost:/# cd /root
root@localhost:~# pwd
/root
root@localhost:~# ls -a
.              .basharc  .gitconfig  .profile   belajar
..             .bashrc   .lesshst    .ssh       latihan-file
.bash_history  .config   .local      README.md
root@localhost:~# cd /root/latihan-file
root@localhost:~/latihan-file# cp file1.txt /root/belajar
root@localhost:~/latihan-file# ls /root/belajar
file1.txt  linux
root@localhost:~/latihan-file# mv file2.txt catatan-penting.txt
root@localhost:~/latihan-file# rm file3.txt
root@localhost:~/latihan-file# ls -la
total 14
drwxr-xr-x+    2 root root 3440 Jun 14 13:46 .
drwx------+    7 root root 3440 Jun 14 13:33 ..
-rw-r--r--+    1 root root   48 Jun 14 13:36 catatan-penting.txt
-rw-r--r--+    1 root root   22 Jun 14 13:35 file1.txt
root@localhost:~/latihan-file#

...

As you can see and read, I made several mistakes—such as forgetting to include proper commands and placing files in incorrect locations.
