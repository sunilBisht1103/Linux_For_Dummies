
## 1.Ls :list files and directories, 
Options
a)ls-l->displays the long-format listing
Input
```bash
ls -l
```
Output
-rw-r--r-- 1 labex labex 0 Apr 12 12:34 file1.txt

b)ls-a->displays all files, including hidden files (files starting with a dot)

Input
```bash
ls -a
```
Output
. .. .hidden_file file1.txt file2.txt folder1 folder2

c)Ls-h->(human-readable) option to display file sizes in a more readable format:

input

```bash
ls -lh -h
```
Output
drwxr-xr-x 2 labex labex 4.0K Apr 12 12:34 folder1

d)ls-R->list the contents of the current directory and its subdirectories, you can use the -R (recursive) option:
Input

```bash
ls -R ~/project 
```

Output
~/project: file1.txt file2.txt folder1 folder2 new_folder 

## 2. Cd- change the current working directory

```bash
cd ~ #or just cd to go to the home directory (/home/labex)
cd - #to go to the previous working directory
cd .. #to go to the parent directory of the current working directory
```


## 3.Mkdir -create new directories. 
```bash
mkdir dir1 dir2 dir3
mkdir -p #command allows you to create a directory structure with multiple levels in a single command. 
mkdir -p projects/web-app/src/components
```

## 4.touch  create new files or update the timestamps of existing files.
Options
-a: Updates the access time of the file.
-m: Updates the modification time of the file.
-d or -t: Sets the access and modification times to the specified date and time.
-c or -f: Creates the file if it doesn't exist, without issuing an error message.

```bash
touch new_file.txt
```

## 5.cp command to copy files and directories.
cp [options] source_file destination_file

-r option is used to copy directories recursively, including all the files and subdirectories within the directory.
```bash
cp ~/project/file1.txt ~/project/file2.txt ~/project/dir1
```
This will copy file1.txt and file2.txt to the dir1 directory.

## 6. mv command is used to move or rename files and directories.
mv [options] source destination
Options
-i: Interactive mode, prompts before overwriting
-f: Force mode, overwrites without prompting
-v: Verbose mode, shows the details of the move operation

Rename a file 

```bash
mv file1.txt file2.txt
```
Move a file to a new directory 


```bash
mv file1.txt ~/project/new_dir/
```

## 7.rm command to remove files and directories. 
rm [options] file(s)
Options
-f: Force removal of files and directories without prompting for confirmation.
-r: Recursively remove directories and their contents.
-i: Prompt for confirmation before removing each file or director

removing a single file using the rm command:
```bash
rm ~/project/test_dir/file1.txt
```
remove a directory and its contents, you can use the -r (recursive) option:
```bash
rm -r ~/project/test_dir
```

## 8.ln command and its practical applications for creating hard links and symbolic links. 
Hard links are essentially copies of the original file, but they share the same inode (file metadata) and physical storage location. This means that changes made to the file content will be reflected in all hard links.

```bash
ln original_file hard_link_name
```

Symbolic links, also known as soft links, are created using the -s option with the ln command. Symbolic links are pointers to the original file or directory, and they contain the path to the target. Unlike hard links, symbolic links can point to files or directories across file system boundaries

```bash
ln -s original_file symbolic_link_name
```

## 9. cat command, which is a versatile tool for concatenating and displaying the contents of text files
Cat [options] [file(s)]
Options
-n: Displays the output with line numbers.
-E: Displays a $ character at the end of each line.
-s: Squeezes multiple adjacent empty lines into one.

Concatenate the contents of file1.txt and file2.txt 

```bash
cat file1.txt file2.txt
```

append text to file3.txt  append additional text to the file:

```bash
cat >> file3.txt
```

## 10.less command allows you to view and navigate through text files efficiently.

```bash
less sample.txt
```
This is a sample text file for the less command.

The less command opens the file in a pager, allowing you to navigate through the text. Here are some basic navigation commands in less:
spacebar or pagedown: Move down one page
b or pageup: Move up one page
g: Move to the beginning of the file
G: Move to the end of the file
/ followed by a search term: Search for the term in the file
n: Move to the next occurrence of the search term
q: Quit the less pager

## 11.more command in Linux, which is a text file pager that allows you to view the contents of a file one page at a time.

```bash
more ~/project/example.txt
```
This will open the example.txt file and display its contents one page at a time. You can navigate through the file using the following commands:
Press the Space key to display the next page.
Press the Enter key to display the next line.
Press b to go back one page.
Press q to quit the more command

## 12.tree command is a powerful tool that displays the directory structure in a tree-like format, making it easier to visualize and navigate the file system.

```bash
Tree
```
```text
. 
├── project 
│ └── README.md 
└── .zshrc
```
## 13.du (disk usage) command in Linux to estimate file space usage and provide information about the disk space occupied by files and directories.
Options
-h: Display the output in human-readable format (e.g., 1.2M instead of 1234567)
-s: Display the total size of a directory, instead of the size of each file/directory within it
-c: Display the grand total at the end of the output
-x: Do not cross file system boundaries
-d <depth>: Limit the depth of the directory tree that du will display

exclude specific directories from the du measurement,

```bash
du -h -d 1 --exclude=subdir1 ~/project/main_dir
```
## 14.The df (disk free) command is an essential utility for displaying information about total, used, and available space on your system's filesystems
Input
```bash
df
```
Output
```text
Filesystem 1K-blocks Used Available Use% Mounted on overlay 20971520 128764 20842756 1% / tmpfs 65536 0 65536 0% /dev tmpfs 8052892 0 8052892 0% /sys/fs/cgroup shm 65536 0 65536 0% /dev/shm /dev/nvme1n1 104806400 20643324 84163076 20% /etc/hosts tmpfs 8052892 0 8052892 0% /proc/acpi tmpfs 8052892 0 8052892 0% /proc/scsi tmpfs 8052892 0 8052892 0% /sys/firmware
```
disk usage for the root directory, represented by /:

```bash
df -h /
```

check the disk usage for your current working directory use a dot .

```bash
df -h .
```

## 15.find command to search for files and directories based on various criteria, such as name, file type, size, and more.
find [path] [expression]

Search for all files in the current directory:
Input
```bash
find .
```
Output
. ./file1.txt ./file2.txt ./directory1 ./directory1/file3.txt

Search for all files with the .txt extension in the current directory and to search for files by name, you can use the -name

```bash
find . -name "*.txt"
```
./file1.txt ./file2.txt ./directory1/file3.txt

Search for all directories in the current directory:

```bash
find . -type d
```

Search for all files larger than 1 megabyte (MB) in the current directory:

```bash
find . -size +1M
```
Search for files by file type:
To search for files by their type, you can use the -type option followed by the file type character. The common file type characters are:
f: regular file
d: directory
l: symbolic link

Find and delete files:

```bash
find . -type f -name "*.tmp" -delete
```
-exec execute commands on matching files:

```bash
find . -type f -name "*.txt" -exec cat {} \;
```
