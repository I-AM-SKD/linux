
# Linux Commands

---

## 1. File and Directory Management

### `ls` (List)
* **Description:** Lists directory contents (files and folders).
* **Syntax:** `ls [options] [path]`
* **Examples:**
  ```bash
  ls -l   # List in long format (permissions, owner, size, date)
  ls -la  # List all files, including hidden ones (starting with .), in long format
  ```

### `cd` (Change Directory)
* **Description:** Navigates between directories.
* **Syntax:** `cd [path]`
* **Examples:**
  ```bash
  cd /var/log  # Move to the absolute path /var/log
  cd ~         # Return to the current user's home directory
  cd ..        # Move up one directory level
  ```

### `pwd` (Print Working Directory)
* **Description:** Displays the full path of the current working directory.
* **Syntax:** `pwd`
* **Examples:**
  ```bash
  pwd  # Outputs e.g., /home/username/documents
  ```

### `mkdir` (Make Directory)
* **Description:** Creates a new directory.
* **Syntax:** `mkdir [options] [directory_name]`
* **Examples:**
  ```bash
  mkdir projects     # Creates a folder named 'projects'
  mkdir -p a/b/c     # Creates nested directories recursively
  ```

### `cp` (Copy)
* **Description:** Copies files or directories.
* **Syntax:** `cp [options] source destination`
* **Examples:**
  ```bash
  cp file.txt backup.txt          # Copies file.txt to backup.txt
  cp -r folder/ backup_folder/    # Recursively copies an entire directory
  ```

### `mv` (Move / Rename)
* **Description:** Moves files/directories or renames them.
* **Syntax:** `mv source destination`
* **Examples:**
  ```bash
  mv oldname.txt newname.txt            # Renames a file
  mv file.txt /home/user/Downloads/     # Moves a file to another directory
  ```

### `rm` (Remove)
* **Description:** Deletes files or directories.
* **Syntax:** `rm [options] [file/directory]`
* **Examples:**
  ```bash
  rm file.txt       # Deletes file.txt
  rm -rf folder/    # Force-deletes a directory and its contents recursively
  ```
> [!warning] Caution
> Be extremely careful with `rm -rf`, as it permanently deletes files and directories without confirmation.

### `touch`
* **Description:** Creates an empty file or updates an existing file’s timestamp.
* **Syntax:** `touch [filename]`
* **Examples:**
  ```bash
  touch index.html
  ```

### `ln` (Link)
* **Description:** Creates links between files (hard links or symbolic/soft links).
* **Syntax:** `ln [options] target link_name`
* **Examples:**
  ```bash
  ln -s /path/to/original symlink  # Creates a symbolic link pointing to the original file
  ```

---

## 2. Viewing and Searching Content

### `cat` (Concatenate)
* **Description:** Reads, displays, or combines file contents in the terminal.
* **Syntax:** `cat [filename]`
* **Examples:**
  ```bash
  cat notes.txt
  ```

### `head`
* **Description:** Outputs the first part (default 10 lines) of files.
* **Syntax:** `head [options] [filename]`
* **Examples:**
  ```bash
  head -n 5 log.txt  # Displays the first 5 lines of log.txt
  ```

### `tail`
* **Description:** Outputs the last part of files. Extremely useful for logs.
* **Syntax:** `tail [options] [filename]`
* **Examples:**
  ```bash
  tail -n 20 error.log        # Displays the last 20 lines
  tail -f /var/log/syslog     # Continuously monitors a log file in real-time
  ```

### `grep` (Global Regular Expression Print)
* **Description:** Searches for specific patterns or text strings within files.
* **Syntax:** `grep [options] "pattern" [filename]`
* **Examples:**
  ```bash
  grep "ERROR" app.log     # Finds all lines containing "ERROR"
  grep -i "error" app.log  # Case-insensitive search
  ```

### `whereis`
* **Description:** Locates the binary, source, and manual file paths for a command.
* **Syntax:** `whereis [command]`
* **Examples:**
  ```bash
  whereis python
  ```

### `whatis`
* **Description:** Displays a brief, one-line manual description of a command.
* **Syntax:** `whatis [command]`
* **Examples:**
  ```bash
  whatis sudo
  ```

---

## 3. System Information and Monitoring

### `uname`
* **Description:** Prints system and kernel information.
* **Syntax:** `uname [options]`
* **Examples:**
  ```bash
  uname -a  # Prints all system info, including kernel version and architecture
  ```

### `whoami`
* **Description:** Prints the username of the currently logged-in user.
* **Syntax:** `whoami`
* **Examples:**
  ```bash
  whoami
  ```

### `ps` (Process Status)
* **Description:** Displays information about active processes.
* **Syntax:** `ps [options]`
* **Examples:**
  ```bash
  ps aux  # Lists all running processes across all users in detail
  ```

### `top`
* **Description:** Displays a dynamic, real-time view of running system tasks and resource utilization (CPU, memory).
* **Syntax:** `top`
* **Examples:**
  ```bash
  top  # Press 'q' to exit
  ```

### `df` (Disk Free)
* **Description:** Reports file system disk space usage.
* **Syntax:** `df [options]`
* **Examples:**
  ```bash
  df -h  # Displays disk space in human-readable format (GB, MB)
  ```

### `service`
* **Description:** Runs System V init scripts to manage system services.
* **Syntax:** `service [service_name] [action]`
* **Examples:**
  ```bash
  sudo service nginx restart
  ```

### `kill` and `killall`
* **Description:** Terminates processes. `kill` uses Process IDs (PIDs), while `killall` uses process names.
* **Syntax:** `kill [PID]` / `killall [process_name]`
* **Examples:**
  ```bash
  kill 1422        # Terminates the process with PID 1422
  kill -9 1422     # Force-kills the process (SIGKILL)
  killall firefox  # Terminates all processes named firefox
  ```

---

## 4. Networking and Connectivity

### `ssh` (Secure Shell)
* **Description:** Securely connects to a remote server over a network.
* **Syntax:** `ssh username@hostname_or_ip`
* **Examples:**
  ```bash
  ssh ubuntu@192.168.1.50
  ```

### `ifconfig`
* **Description:** Configures or views network interface parameters (IP addresses, MAC addresses).
* **Syntax:** `ifconfig [interface]`
* **Examples:**
  ```bash
  ifconfig eth0
  ```

### `wget`
* **Description:** Non-interactive network downloader used to fetch files from the web.
* **Syntax:** `wget [URL]`
* **Examples:**
  ```bash
  wget https://example.com/archive.zip
  ```

### `ufw` (Uncomplicated Firewall)
* **Description:** User-friendly interface for managing netfilter (`iptables`) firewalls.
* **Syntax:** `ufw [action] [rule]`
* **Examples:**
  ```bash
  sudo ufw enable    # Turns on the firewall
  sudo ufw allow 22  # Opens port 22 for SSH traffic
  ```

---

## 5. Package Management and Administration

### Package Managers (`apt`, `pacman`, `yum`, `rpm`)
* **Description:** Installs, updates, and removes software packages depending on the Linux distribution.
* **Examples:**
  ```bash
  # Debian/Ubuntu (apt)
  sudo apt update && sudo apt install nginx

  # Arch Linux (pacman)
  sudo pacman -S git

  # RHEL/CentOS (yum)
  sudo yum install httpd

  # RPM Package Tool (rpm - standalone .rpm file)
  sudo rpm -ivh package.rpm
  ```

### `sudo` (Superuser Do)
* **Description:** Executes a command with administrative or root privileges.
* **Syntax:** `sudo [command]`
* **Examples:**
  ```bash
  sudo apt update
  ```

### `chmod` (Change Mode)
* **Description:** Modifies file or directory access permissions.
* **Syntax:** `chmod [permissions] [filename]`
* **Examples:**
  ```bash
  chmod 755 script.sh  # Owner: rwx (7), Group: r-x (5), Others: r-x (5)
  chmod +x script.sh   # Grants execute permission to all users
  ```

---

## 6. Archives, Compression, and Shell Utilities

### `tar` (Tape Archive)
* **Description:** Archives multiple files/directories into a single `.tar` file and handles compression (`gzip`/`bzip2`).
* **Syntax:** `tar [options] [archive_name] [files/folders]`
* **Examples:**
  ```bash
  tar -czvf backup.tar.gz folder/  # Creates a compressed gzip archive
  tar -xzvf backup.tar.gz          # Extracts a gzip archive
  ```

### `zip` and `unzip`
* **Description:** Compresses and extracts ZIP archives.
* **Syntax:** `zip archive.zip file1 file2` / `unzip archive.zip`
* **Examples:**
  ```bash
  zip -r website.zip html/  # Compresses a folder into a zip file
  unzip website.zip         # Extracts the zip archive
  ```

### `clear`
* **Description:** Clears the terminal screen.
* **Syntax:** `clear` (or keyboard shortcut `Ctrl + L`)

### `echo`
* **Description:** Prints text or variables to the terminal output.
* **Syntax:** `echo [text/variable]`
* **Examples:**
  ```bash
  echo "Hello, World!"
  echo $USER
  ```

### `export`
* **Description:** Sets environment variables for current and child processes.
* **Syntax:** `export VARIABLE_NAME=value`
* **Examples:**
  ```bash
  export PATH=$PATH:/usr/local/custom/bin
  ```

### `alias`
* **Description:** Creates custom shortcuts or alternative names for commands.
* **Syntax:** `alias shortcut_name='command'`
* **Examples:**
  ```bash
  alias cls='clear'
  alias ll='ls -la'
  ```

### `man` (Manual)
* **Description:** Displays the full manual pages/documentation for any command.
* **Syntax:** `man [command]`
* **Examples:**
  ```bash
  man grep  # Press 'q' to quit
  ```