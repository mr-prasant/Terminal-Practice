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

`[directory]` : The path of the directory you want to move to. This can be an absolute path or a relative path.

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

---


### 3. `mkdir` – Make Directory

The `mkdir` command is used to **create new directories (folders)** in Linux/Ubuntu. It can create single or multiple directories, nested folders, and even set permissions while creating them.


**Syntax:**
```bash
mkdir [options] directory_name
```

`[options]`: Modify the behavior (e.g., create parent directories)

`directory_name`: Name or path of the directory to create

| Feature / Example                | Description / Command                                                                 |
|----------------------------------|----------------------------------------------------------------------------------------|
| **Syntax**                       | `mkdir [options] directory_name` – Create a new directory or multiple directories      |
| **Single Directory**             | `mkdir new_folder` – Creates a directory named `new_folder` in the current location    |
| **Multiple Directories**         | `mkdir folder1 folder2 folder3` – Creates multiple directories at once                 |
| **Parent Directories**           | `mkdir -p parent/child/grandchild` – Creates nested directories in one command         |
| **Verbose Mode**                 | `mkdir -v myfolder` – Shows a message for each directory created                       |
| **Directory with Spaces**        | `mkdir "My Folder"` – Use quotes when directory name contains spaces                   |
| **Absolute Path**                | `mkdir /home/user/newfolder` – Creates a folder at the specified absolute path          |
| **Relative Path**                | `mkdir ../backup` – Creates a folder in the parent directory                           |
| **Permissions While Creating**   | `mkdir -m 755 secure_folder` – Creates a folder with specific permissions              |
| **Check Directory Creation**     | `ls -l` – Verify the created directories in the current location                       |
| **Tips**                         | Use `-p` to avoid errors if parent directories don’t exist                             |

### Examples

**3.1 Example for creating a single directory:**  
Command:  
```bash
$ mkdir new_folder
```
Result:
```bash
# Creates a directory named 'new_folder' in the current location
```

**3.2 Example for creating multiple directories at once:**  
Command:  
```bash
$ mkdir folder1 folder2 folder3
```
Result:
```bash
# Creates three directories named 'folder1', 'folder2', and 'folder3' in the current location
```

**3.3 Example for creating parent and nested directories:**  
Command:  
```bash
$ mkdir -p parent/child/grandchild
```
Result:
```bash
# Creates 'parent', 'child', and 'grandchild' directories in a nested structure
```

**3.4 Example for verbose mode while creating a directory:**  
Command:  
```bash
$ mkdir -v myfolder
```
Result:
```bash
mkdir: created directory 'myfolder'
# Displays a confirmation message when a directory is created
```

**3.5 Example for creating a directory with spaces in its name:**  
Command:  
```bash
$ mkdir "My Folder"
```
Result:
```bash
# Creates a directory named 'My Folder'
```

**3.6 Example for creating a directory using an absolute path:**  
Command:  
```bash
$ mkdir /home/user/newfolder
```
Result:
```bash
# Creates 'newfolder' inside the '/home/user' directory
```

**3.7 Example for creating a directory using a relative path:**  
Command:  
```bash
$ mkdir ../backup
```
Result:
```bash
# Creates a directory named 'backup' one level up from the current directory
```

**3.8 Example for creating a directory with specific permissions:**  
Command:  
```bash
$ mkdir -m 755 secure_folder
```
Result:
```bash
# Creates 'secure_folder' with read, write, and execute permissions for owner, and read and execute for others
```

**3.9 Example tip for avoiding parent directory errors::**  
Command:  
```bash
$ mkdir -p project/src/components
```
Result:
```bash
# Creates all required parent folders automatically if they don’t exist
```

---


### 4. `rm` – Remove

The `rm` (remove) command is used to **delete files and directories** from the file system in Linux or Ubuntu. Once removed, files **cannot be recovered** through normal means — **so use it with caution**.

**Syntax:**
```bash
rm [OPTION]... FILE...
```

`OPTION`: Modifies how `rm` behaves (e.g., force delete, recursive delete).

`FILE`: Name(s) of the file(s) or directory(ies) you want to delete.

| Option | Description | Example |
|:-------:|:-------------|:---------|
| `-f` | Force deletion **without asking for confirmation**, even if the file is write-protected. | `rm -f file1.txt` |
| `-i` | Prompts for confirmation **before deleting** each file. | `rm -i file1.txt` |
| `-r` | Recursively remove **directories and their contents**. | `rm -r folder1` |
| `-rf` or `-fr` | Combine both — **recursively** delete directories and their contents **without confirmation**. | `rm -rf folder1` |
| `-v` | **Verbose** mode — shows which files are being deleted. | `rm -v file1.txt` |

### Examples

**4.1 Example for removing a single file:**  
Command:  
```bash
$ rm file1.txt
```
Result:
```bash
# Deletes the file named 'file1.txt' from the current directory.
```


**4.2 Example for removing multiple files at once:**  
Command:  
```bash
$ rm file1.txt file2.txt file3.txt
```
Result:
```bash
# Deletes file1.txt, file2.txt, and file3.txt together.
```

**4.3 Example for removing a directory and its contents:**  
Command:  
```bash
$ rm -r myFolder
```
Result:
```bash
# Removes 'myFolder' and everything inside it recursively.
```

**4.4 Example for force delete a folder (without confirmation):**  
Command:  
```bash
$ rm -rf old_backups/
```
Result:
```bash
# Deletes the 'old_backups' folder and all files inside it without asking.
# Be careful – this action cannot be undone.
```

**4.5 Example for removing files interactively:**  
Command:  
```bash
$ rm -i *.log
```
Result:
```bash
rm: remove regular file 'error.log'? y
rm: remove regular file 'access.log'? n
# Deletes only the files you confirm with 'y'.
```

**4.6 Example for verbose deletion (see what’s being deleted):**  
Command:  
```bash
$ rm -v file1.txt file2.txt
```
Result:
```bash
removed 'file1.txt'
removed 'file2.txt'
```

**Tip**
If you want to move a file to a "trash" instead of permanent deletion, you can use:

```bash
$ gio trash filename
```

This sends the file to the system trash instead of removing it permanently.

