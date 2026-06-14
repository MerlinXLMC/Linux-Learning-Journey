# My First Experience Touching LinuxX


## When I first entered Linux, I was momentarily confused by the CLI—I didn’t know what to do. At the beginning of my Linux learning journey, I spent most of my time searching for learning resources to understand what steps I should take.
Eventually, I found a highly relevant learning resource: using AI (Claude AI) as my "mentor."
This helped me discover the right approach to learning Linux and gave me a clear learning roadmap.
To document my Linux learning journey, I’ve decided to record everything in my repository.

## My Purpose for Learning Linux

Of course, I have a clear purpose for learning Linux—it’s not just random experimentation.
My goal is to become a Cloud Engineer in the future.
That’s why I’m learning Linux: because cloud-related jobs require Linux skills (among other things).

## My First Steps in Learning Linux

This note will cover topics such as the filesystem, commands I’ve learned, my experiments with Linux, and questions I have.

## The Linux Filesystem

In my opinion, the Linux filesystem is quite unique because it uses an inverted tree structure—like a tree whose roots grow downward instead of upward.
Other operating systems might organize their filesystems more like grouped categories rather than an inverted tree.
Moreover, in Linux, everything is treated as a file, making all entities fundamentally equivalent.
Linux Filesystem Structure:

/ (Root)
├── etc/
├── home/
├── var/
├── tmp/
├── usr/
└── bin/

- Root:  
  In Linux, "root" refers to the superuser account (administrator) with the highest level of system access and privileges.
- Etc:  
  The /etc directory serves as the central control hub for configuring the operating system’s behavior.
- Home:  
  This directory contains users’ personal data files.
- Var:  
  /var stores dynamic or frequently changing data generated during system operation (e.g., logs, caches).
- Tmp:  
  /tmp holds temporary files used by the operating system.
- Usr:  
  /usr is the main storage location for applications, libraries, and user programs.
- Bin:  
  /bin contains essential command binaries (executable programs).

## Linux Commands (Ubuntu)

I’ve learned several basic commands, including:

- pwd: Shows your current location in the filesystem.  
- ls: Lists the contents of a directory.  
- cd: Changes to another directory.  
- mkdir: Creates a new directory.

## Experiments I’ve Conducted

- I experimented with flags for each basic command and discovered they produce different outputs depending on the flag used.
- I realized that "Home" and "Root" are not the same. When the AI instructed me to navigate to the home directory (cd), I mistakenly thought "Home" referred to a directory literally named "Home." That was incorrect—the term "home" actually refers to the user's personal home directory, which is distinct from the root (/) directory.

[Input]

1. Navigate to the /var/log directory and list its contents.  
2. Return to your home directory using a method different from your usual approach.  
3. Create the following directory structure in a single command: ~/belajar/linux/dasar  
4. While inside /etc, display the contents of your home directory without leaving /etc.

[Output]

root@localhost:/# cd /var/log
root@localhost:/var/log# ls -a
.  ..  alternatives.log  apt  bootstrap.log  btmp  dpkg.log  lastlog  wtmp
root@localhost:/var/log# cd /
root@localhost:/# mkdir -p learning/linux/one
root@localhost:/# cd etc
root@localhost:/etc# ls /
apex  dev       lib           odm      root    srv      system_ext  vendor
bin   etc       linkerconfig  opt      run     storage  tmp
boot  home      media         proc     sbin    sys      usr
data  learning  mnt           product  sdcard  system   var
root@localhost:/etc#

## My Questions:

- Why is the filesystem structured like an inverted tree?  
- Why does Linux treat everything as a file?
