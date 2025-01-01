# Linux Commands Explanation with Examples

## 1. `pwd` - Print Working Directory
- **Description**: Displays the current directory path.
- **Example**:
  ```bash
  $ pwd
  /home/feilzz
  ```
  Output: `/home/feilzz`
- **Options**: 
  - `--help`: Displays help information about `pwd`.

---

## 2. `whoami` - Show Current User
- **Description**: Prints the username of the current user.
- **Example**:
  ```bash
  $ whoami
  feilzz
  ```
- **Options**:
  - `--help`: Displays help information about `whoami`.

---

## 3. `date` - Display System Date and Time
- **Description**: Shows the current date and time of the system.
- **Example**:
  ```bash
  $ date
  Wed Jan 1 09:10:33 UTC 2025
  ```
- **Options**:
  - `+%Y-%m-%d`: Displays the date in `YYYY-MM-DD` format.
    ```bash
    $ date +%Y-%m-%d
    2025-01-01
    ```
  - `+%T`: Displays only the time in `HH:MM:SS` format.
    ```bash
    $ date +%T
    09:10:33
    ```

---

## 4. `ls` - List Directory Contents
- **Description**: Displays the contents of the current directory.
- **Example**:
  ```bash
  $ ls
  linux
  ```
- **Options**:
  - `-a`: Shows all files, including hidden files.
    ```bash
    $ ls -a
    .  ..  .bashrc  linux
    ```
  - `-l`: Lists files in long format with details.
    ```bash
    $ ls -l
    drwxr-xr-x 2 feilzz feilzz 4096 Jan 1 09:10 linux
    ```
  - `-h`: Human-readable sizes when used with `-l`.
    ```bash
    $ ls -lh
    drwxr-xr-x 2 feilzz feilzz 4.0K Jan 1 09:10 linux
    ```

---

## 5. `mkdir` - Make Directory
- **Description**: Creates a new directory.
- **Example**:
  ```bash
  $ mkdir linux
  ```
  Creates a directory named `linux` in the current path.
- **Options**:
  - `-p`: Creates parent directories as needed.
    ```bash
    $ mkdir -p parent/child
    ```
  - `-v`: Prints a message for each created directory.
    ```bash
    $ mkdir -v linux
    mkdir: created directory 'linux'
    ```

---

## 6. `cd` - Change Directory
- **Description**: Navigates between directories.
- **Example**:
  ```bash
  $ cd linux
  $ pwd
  /home/feilzz/linux
  ```
- **Options**:
  - No specific options, but useful shortcuts include:
    - `cd ..`: Moves to the parent directory.
    - `cd ~`: Moves to the home directory.
    - `cd -`: Switches to the previous directory.

---

## 7. `ls -a` - List All Files
- **Description**: Displays all files, including hidden ones.
- **Example**:
  ```bash
  $ ls -a
  .  ..  .bashrc  linux
  ```

---

## 8. `.bashrc` - Shell Configuration File
- **Description**: A script file executed whenever a new terminal session starts for custom shell configuration.
- **Example**:
  ```bash
  $ nano ~/.bashrc
  ```
  Add aliases or environment variables.

---

## 9. `..` - Parent Directory Shortcut
- **Description**: Used with `cd` or `ls` to refer to the parent directory.
- **Example**:
  ```bash
  $ cd ..
  $ pwd
  /home
  ```

---

## 10. `.sudo_as_admin_successful`
- **Description**: A hidden file created when a user first uses `sudo` successfully. Used for tracking purposes.

---

## Usage Notes
These commands are foundational to Linux and allow for efficient navigation and system interaction. They form the basis for more complex scripting and system management.
