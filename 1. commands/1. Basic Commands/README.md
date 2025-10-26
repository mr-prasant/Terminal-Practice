# Basic Commands

## Description
This file contains fundamental Ubuntu/Linux commands used for navigating the file system, managing files and directories, and performing basic operations in the terminal.  

---

## Commands Details

### 1. `ls` – List files and directories
The `ls` command is used to list the contents of a directory in Linux/Ubuntu. It can show files, folders, hidden files, permissions, owners, sizes, and modification dates depending on the options used.

**Syntax:**
```bash
ls [options] [directory]
```

- [options] → Modify the output (e.g., show hidden files, long format)

- [directory] → Specify the directory to list; if omitted, it lists the current directory.

| Option | Description |
|--------|-------------|
| -l | Long listing format (shows permissions, owner, size, date modified) |
| -a | Show all files, including hidden files starting with . |
| -h | Human-readable file sizes (e.g., 1K, 2M) |
| -R | Recursively list all subdirectories |
| -t | Sort by modification time |
| -S | Sort by file size |

### Examples

 **1.1 Example for `$ ls -l` command:**
Command:
```bash
$ ls -l
```

Result:
```bash
total 12
-rw-r--r-- 1 user user  123 Oct 27 2025 file1.txt
drwxr-xr-x 2 user user 4096 Oct 27 2025 folder1
```

It gives the long listing format (shows permissions, owner, size, date modified) for total number of files and directories in the current directory.

**1.2 Example for `$ ls -a` command:**
Command:
```bash
$ ls -a
```

Result:
```bash
.  ..  file1.txt  folder1  .hiddenfile
```
It Show all files, including hidden files starting with `.` in the current directory.

**1.3 Example for `$ ls -lh` command:**
Command:
```bash
$ ls -lh
```

Result:
```bash
total 4.0K
-rw-r--r-- 1 user user    0 Oct 27 01:07 file1.txt
drwxr-xr-x 2 user user 4.0K Oct 27 01:08 folder1
```
The `-h` option is used with ls `-l` to display file sizes in a human-readable format, instead of bytes. This makes it easier to quickly understand the size of files and directories. Sizes are automatically converted to KB, MB, GB, etc. depending on the file size.

**1.4 Example for `$ ls -R` command:**
Command:
```bash
$ ls -R
```

Result:
```bash
.:
file1.txt  folder1

./folder1:
file2.txt
```
The `-R` option with `ls` lists all files and directories recursively, meaning it shows the contents of the current directory as well as all its subdirectories and their contents. This is useful for getting a full overview of a directory tree.

- **Explanation of Output:**

    `.` → Represents the current directory (.), showing `file1.txt` and `folder1`.

    `./folder1:` → Shows the contents of the subdirectory `folder1`, which contains `file2.txt`.

    This output continues recursively for any nested subdirectories.

- **Tips:**

    Combine with `-l` for detailed information: `ls -lR`

    Combine with `-a` to include hidden files: `ls -aR`

    Useful for exploring large directory structures quickly.

**1.5 Example for `$ ls -t` command:**
Command:
```bash
# for long listing, we merge -t with -l
$ ls -lt
```

Result:
```bash
-rw-r--r-- 1 user user  456 Oct 27 2025 file2.txt
-rw-r--r-- 1 user user  123 Oct 26 2025 file1.txt
```

Files are displayed in descending order of last modification time.

**1.6 Example for `$ ls -S` command:**
Command:
```bash
# for long listing, we merge -S with -l
$ ls -lS
```

Result:
```bash
-rw-r--r-- 1 user user 1024 Oct 27 2025 bigfile.txt
-rw-r--r-- 1 user user  123 Oct 27 2025 file1.txt
```

Sorts files by size, displaying the largest files first.

**1.7 Combination Options:**

You can combine multiple options for more powerful listings:
Command:

```bash
$ ls -lha   # Hidden files, long format, human-readable sizes
$ ls -lRt   # Long format, recursive, sorted by modification time
```


**Tips**

Use `man ls` to explore all available options.

Practice in different directories to understand file structure.

Use `tab completion` to save time when typing file or directory names.

---

### 2. `cd` – Change Directory

The `cd` command stands for **"change directory"**. It is used to navigate between directories in the Linux/Ubuntu terminal.


**Syntax:**
```bash
cd [directory]
```

`directory` : The path of the directory you want to move to. This can be an absolute path or a relative path.

| Feature / Example                | Description / Command                                                                 |
|---------------------------------|--------------------------------------------------------------------------------------|
| **Syntax**                       | `cd [directory]` – Change to the specified directory (absolute or relative path)     |
| **Absolute Path**                | `cd /home/user/Documents` – Moves to the `Documents` directory                        |
| **Relative Path**                | `cd Documents` – Moves to `Documents` inside the current directory                    |
| **Parent Directory**             | `cd ..` – Moves one level up in the directory hierarchy                               |
| **Home Directory**               | `cd ~` or `cd` – Moves to the user's home directory                                   |
| **Previous Directory**           | `cd -` – Moves back to the directory you were in previously                           |
| **Directory with Spaces**        | `cd "My Folder"` – Use quotes when the directory name contains spaces                 |
| **Check Current Directory**      | `pwd` – Prints the current working directory                                          |
| **Tips**                         | Tab completion can be used to automatically complete directory names                 |

### Examples

**2.1 Example for moving to an absolute path:**
Command:
```bash
$ cd /home/user/Documents
```

Result:
```bash
# Moves directly to the Documents folder inside /home/user
```

**2.2 Example for moving to a relative path:**
Command:
```bash
$ cd Documents
```

Result:
```bash
# Moves into the Documents folder inside the current directory
```

**2.3 Example for moving to the parent directory:**
Command:
```bash
$ cd ..
```

Result:
```bash
# Moves one level up in the directory hierarchy
```

**2.4 Example for moving to the home directory:**
Command:
```bash
$ cd ~
```

Result:
```bash
# Takes you to the user's home directory
```

**2.5 Example for moving to the home directory (alternative):**
Command:
```bash
$ cd
```

Result:
```bash
# Takes you to the user's home directory
```

**2.6 Example for moving to the previous directory:**
Command:
```bash
$ cd -
```

Result:
```bash
# Returns to the directory you were in just before the current one

**2.7 Example for a directory with spaces in the name:**
Command:
```bash
$ cd "My Folder"
```

Result:
```bash
# Moves into a folder named 'My Folder' inside the current directory
```

**2.8 Example for checking the current directory:**
Command:
```bash
$ pwd
```

Result:
```bash
/home/user/Documents
# Prints the full path of the current working directory
```

**2.9 Example for navigating to a nested folder structure:**
Command:
```bash
$ cd /home/user/Documents/Projects/Code
```

Result:
```bash
# Moves directly into the nested 'Projects/Code' folder
```

**2.10 Example for going up one level and then entering another folder:**
Command:
```bash
$ cd ../Downloads
```

Result:
```bash
# Moves one level up, then enters the 'Downloads' folder
```
