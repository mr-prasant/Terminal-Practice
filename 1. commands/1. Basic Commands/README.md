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
