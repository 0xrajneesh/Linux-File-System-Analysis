# Basic File System Analysis on Linux

## Introduction
![LINUX FILE SYSTEM ANALYSIS (2)](https://github.com/user-attachments/assets/cba57d46-96e3-4547-a980-b1b3386f7ecd)

File system analysis is a critical skill in cybersecurity, involving the examination of file structures and contents to detect anomalies, recover data, and understand system activities. This lab will guide you through basic file system analysis on a Linux system, helping you to identify, analyze, and interpret various file system components and metadata.   

`Category`: Digital Forensics and Incident Response   
`Sub-Category`: Linux Forensics   
`Level`: Beginner   

## Pre-requisites

- Basic understanding of Linux commands and file system structure.
- A Linux system or virtual machine with sudo privileges.
- Familiarity with command-line interface (CLI).

## Lab Setup and Tools

### Lab Setup

1. Install a Linux distribution (e.g., Ubuntu, Fedora) on your system or set up a virtual machine using VirtualBox or VMware.
2. Ensure you have sudo access to install necessary tools and perform analysis.

### Tools

- `ls` - List directory contents
- `stat` - Display file or file system status
- `find` - Search for files in a directory hierarchy
- `grep` - Search through text
- `file` - Determine file type
- `df` - Report file system disk space usage
- `du` - Estimate file space usage
- `mount` - Mount and unmount file systems

## Exercises

### Exercise 1: Listing and Understanding Directory Contents

#### Steps

1. **List contents of a directory:**
   ```bash
   ls -l /home
Expected Output: Detailed list of files and directories within /home including permissions, owner, group, size, and modification date.

2. View hidden files:

```bash
ls -la /home
```

Expected Output: Detailed list including hidden files (those starting with a dot).

3. Classify file types:

```bash
ls -lF /home
```
Expected Output: A list where directories, executable files, and symbolic links are indicated with /, *, and @ respectively.

### Exercise 2: Analyzing File Metadata

Step1: Display file status:

```bash
stat /home/username/file.txt
```
Expected Output: Detailed file information including inode number, access/modification/change times, size, and permissions.

Step2: Determine file type:

```bash
file /home/username/file.txt
```
Expected Output: Description of the file type (e.g., ASCII text, directory, symbolic link).

Step3: Search for specific files:

```bash
find /home -name "*.txt"
```
Expected Output: List of .txt files under /home.

Step4: Search for empty files

```bash
find /home -empty
```
Expected Output: List of all the empty files
Step5: Find Files by Size

```sh
find /home -type f -size +100M
```
Expected Output: List of all the files of size more than 100 MBs

Step5: Find Files by Modification Time:

```sh
find /home -type f -mtime -7
```
Expected Output: This command finds files modified in the last 7 days.

Step6: Find Files by Access Time

```sh
find /home -type f -atime -7

```
Expected Output: This command finds files accessed in the last 7 days.

Step7: Find Files by Access Time

```sh
find /home -type f -ctime -7

```
Expected Output: This command finds files created in the last 7 days.




### Exercise 3: Disk Usage Analysis

Step1: Report file system disk space usage:

```bash
df -h
```
Expected Output: Human-readable format of disk space usage for all mounted file systems.

Step2: Check disk usage of a specific directory:

```bash
du -sh /home/username
```
Expected Output: Total disk usage of the specified directory in a human-readable format.

Step3: List disk usage of all files and directories:

```bash
du -ah /home/username
```
Expected Output: Disk usage for each file and directory within the specified path.

### Exercise 4: Searching and Filtering File Contents

Step1: Search for a string within files:

```bash
grep "password" /home/username/*.txt
```
Expected Output: Lines containing the word "password" in any .txt file within the specified directory.

Step2: Recursive search in directories:

```bash
grep -r "password" /home/username
```
Expected Output: Lines containing the word "password" in all files within the specified directory and its subdirectories.

Step3: Count occurrences of a string:

```bash
grep -c "password" /home/username/*.txt
```
Expected Output: Number of lines containing "password" in each file.

### Exercise 5: Mounting and Unmounting File Systems

Step1: List mounted file systems:

```bash
mount | grep "^/dev"
```
Expected Output: List of currently mounted file systems.

Step2: Mount a new file system:

```bash
sudo mount /dev/sdb1 /mnt
```
Expected Output: /dev/sdb1 mounted at /mnt (no output if successful).

Step3: Unmount the file system:

```bash
sudo umount /mnt
```
Expected Outcome: /mnt unmounted (no output if successful).

By completing these exercises, you will gain a solid foundation in basic file system analysis on Linux, which is essential for more advanced cybersecurity tasks.
