# Linux Learning Documentation

Hi! I’m Ashton, and this repository documents my daily Linux practice and learning.
My goal is to build strong Linux fundamentals for Cloud / DevOps roles.

## What I’m Learning
- Using the shell
- Moving around the filesystem
- Working with Text Files
- Managing running processes
- Writing simple shell scripts

## Tools & Environment
- OS: Arch Linux x86_64
- Kernel: Linux 6.18.1-arch1-2
- Shell: Bash
- Editor: Vim
- Terminal: Kitty 0.44.0

## Repository Structure
```text
Linux-Learning/
├── README.md
└── bash-scripts/
    └── backup.sh

```
## 📌 Note
I studied Linux consistently before starting this log.
Daily logging begins here to keep track of progress going forward.

## Previous Topics I covered

## 📖 Learning Log

**Entry 1**
- Focus: Searching files with find, Finding files by user, Finding files by permission, Finding files by date and time, Finding files and executing commands 
- Commands / Concepts: Working with text files,`find`, `mkdir`, `chmod`, `cd`,`-ctime`, `-perm`
- Practice:
    - Created a `TEST` directory in the home directory
        - `mkdir TEST`
    - Created files `one`, `two`, and `three`
        - `cd TEST`,`touch one two three` 
    - Set full read, write, and execute permissions for user, group, and others
        - `chmod ugo+rwx one two three` 
    - Used `find` to search for files writable by others from the home directory
        - `find /home/ashton -perm 777 -ls` 
    - Used `find` to locate files under `/usr/share/doc` not modified in over 300 days
        - `find /usr/share/doc -ctime +300` 
    - Created `/tmp/FILES` directory
        - `mkdir /tmp/FILES` 
    - Used `find` with size filters to locate files between 5MB and 10MB under `/usr/share`
        - `find /usr/share -size +5M -size -10M` 
- Notes / Issues:
    - `chmod 777` grants full permissions to everyone
    - `-ctime +300` finds files older than 300 days
    - System directories like `/usr/share` often require elevated privileges
    - Copying files from `/usr/share` to `/tmp/FILES` was unsuccessful due to permission restrictions
    - Some files could not be accessed without `sudo`

**Entry 2**
- Focus: File location, searching, directory creation, and copying files/directories
- Commands / Concepts:
    - `locate` – quickly find files using the system database
    - `find` – search files/directories by path and size
    - `mkdir` – create directories
    - `cp -r -a` – copy files/directories recursively while preserving attributes
    - Absolute vs relative paths
    - Navigating system directories (`/usr/share`, `/tmp`, home directory)

Practice:
    - Used locate to search for passwd and /tmp/FILES
    - Created /tmp/FILES directory
    - Used find to list files and search by size range
    - Copied various system files (PDFs, .gir, .jar, .txt) from /usr/share into /tmp/FILES
    - Verified copied files using find
    - Copied selected files from /tmp/FILES into a hidden backup directory (.mybackup) in the home directory

Notes / Issues:
    - locate may return no results if the database is not updated
    - Some cp commands initially failed due to incorrect paths
    - Learned the importance of using full absolute paths when copying system files
    - Confirmed successful file transfers by listing contents after copying

