# Linux Commands Usage and Examples

Below is a detailed explanation of each command used, along with examples and available options.

## 1. `pwd`

### Description
The `pwd` command stands for "print working directory." It outputs the full path of the current directory you are working in.

### Example
```bash
$ pwd
/home/feilzz
```
This shows that the current directory is `/home/feilzz`.

### Options
- `-L`: Prints the logical current working directory.
- `-P`: Prints the physical directory by resolving symbolic links.

Example with options:
```bash
$ pwd -P
/home/feilzz
```

---

## 2. `whoami`

### Description
The `whoami` command displays the username of the current user.

### Example
```bash
$ whoami
feilzz
```
This indicates that the logged-in user is `feilzz`.

### Options
No options are available for `whoami`. It simply prints the username.

---

## 3. `date`

### Description
The `date` command displays or sets the system date and time.

### Example
```bash
$ date
Wed Jan  1 09:10:33 UTC 2025
```
This shows the current system date and time.

### Options
- `+"format"`: Customizes the output format.
- `-u`: Displays the time in UTC.
- `-d`: Displays the given date instead of the current date.

Example with options:
```bash
$ date -u
Wed Jan  1 09:10:33 UTC 2025
```

---

## 4. `ls`

### Description
The `ls` command lists files and directories in the current working directory.

### Example
```bash
$ ls
linux
```
This lists the `linux` directory in the current folder.

### Options
- `-a`: Displays all files, including hidden files (those starting with `.`).
- `-l`: Displays a detailed list.
- `-h`: Displays file sizes in human-readable format.

Example with options:
```bash
$ ls -al
.   .bash_history  .bashrc  .landscape   .profile  linux
..  .bash_logout   .cache   .motd_shown  .sudo_as_admin_successful
```

---

## 5. `mkdir`

### Description
The `mkdir` command creates a new directory.

### Example
```bash
$ mkdir linux
```
This creates a directory named `linux` in the current directory.

### Options
- `-p`: Creates parent directories as needed.
- `-v`: Displays a message for each created directory.

Example with options:
```bash
$ mkdir -p projects/java
```
This creates the `projects` directory and the `java` subdirectory inside it.

---

## 6. `cd`

### Description
The `cd` command changes the current working directory.

### Example
```bash
$ cd linux
```
This navigates into the `linux` directory.

### Options
No specific options, but usage examples include:
- `cd ..`: Moves to the parent directory.
- `cd ~`: Moves to the home directory.

Example:
```bash
$ cd ..
```
Moves back to the parent directory.

---

## 7. `ls -a`

### Description
The `ls -a` command lists all files and directories, including hidden files.

### Example
```bash
$ ls -a
.   .bash_history  .bashrc  .landscape   .profile  linux
..  .bash_logout   .cache   .motd_shown  .sudo_as_admin_successful
```
This shows both regular and hidden files in the current directory.

### Options
Combines options from the `ls` command.
- `-l`: Provides a detailed list.
- `-h`: Displays file sizes in human-readable format.

Example with options:
```bash
$ ls -al
```
Provides a detailed list of all files, including hidden ones.

