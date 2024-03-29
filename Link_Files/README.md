# Types of Link Files

There are 2 types of link files:

1. **Hard Link Files:**
   - It is just another name of the same exact file.
   - We can create a hard link file by using the `ln` command.
     ```
     ln originalfile hardlinkfile
     ```
     Eg: `ln file1.txt file2.txt`
     Here `file1.txt` is the original file and `file2.txt` is the hard link file.
   - **Important conclusions about hard link files:**
     1. Both original file and hardlink file have the same inode number, same size, same timestamp.
     2. If we delete the original file, then there is no effect on the hardlink file.

2. **Soft Link File:**
   - A softlink is a pointer to another file. It is just like a Windows shortcut.
   - It is also known as a symbolic link.
   - We can create a soft link file by using the `ln` command but with the `-s` option.
     ```
     ln -s originalfile softlinkfile
     ```
     Eg: `ln -s file1.txt file2.txt`
     Here `file1.txt` is the original file and `file2.txt` is the link file.
   - **Important conclusions about softlink files:**
     1. Original file and softlink file have different inode numbers, different file sizes, and different timestamps.
     2. Usually, softlink file has a smaller file size than the original file size.
     3. If we delete the original file, then softlink files will become useless.


## Link Files for Directories:

We cannot create hard links for directories because it breaks the Linux File System. Having two root directories is meaningless.

```bash
$ ln dir1 dir2
ln: dir1: hard link not allowed for directory
```
We can create soft links for directories:
```bash
$ ln -s dir1 dir2
```

Note: For files, we can create both hard and soft links. But for directories, we can create only soft links but not hard links.

Case Study:
Assume dir1 contains dir2.
dir2 contains a soft link dir3 pointing to dir1.

```
$ mkdir -p dir1/dir2
$ cd dir1/dir2
$ ln -s ~/Desktop/dir1 dir3
```


It will form a loop.

Note: While creating link files, there may be a chance of forming loops. Take a bit of special care.
