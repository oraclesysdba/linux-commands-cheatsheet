# LINUX-COMMANDS-CHEATSHEET
================================================================================
                    LINUX COMMANDS CHEATSHEET
          Author: Samson J
          LinkedIn: https://www.linkedin.com/in/samson-j-997403234
================================================================================

A comprehensive quick reference to fundamental Linux commands, syntax, and
advanced features. Ideal for both beginners and experienced system
administrators for efficient server management and automation.

================================================================================
 1. SYSTEM INFORMATION & STATUS
================================================================================

  uname -a            Display all system information (kernel name, version,
                      architecture, hostname, OS)
  uname -r            Show kernel release version
  lscpu               Display detailed CPU architecture information
  lsblk               List all block devices (disks, partitions)
  uptime              Show how long the system has been running, load average
  hostname            Display or set the system hostname
  hostnamectl         View or change the system hostname and related settings
  date                Display the current date and time
  timedatectl         Display and set the system date, time, and timezone
  cal                 Display a calendar for the current month
  w                   Show who is logged on and what they are doing
  who                 Display who is currently logged in
  whoami              Print the current logged-in username
  id                  Display user and group IDs
  env                 Display all environment variables
  printenv            Print all or specific environment variable values
  free -h             Display free and used memory in human-readable format
  cat /proc/cpuinfo   Display CPU information from proc filesystem
  cat /proc/meminfo   Display memory information from proc filesystem
  lspci               List all PCI devices
  lsusb               List all USB devices
  dmidecode           Display hardware information from BIOS/UEFI
  dmesg               Print kernel ring buffer messages (boot/hardware logs)

================================================================================
 2. FILE & DIRECTORY OPERATIONS
================================================================================

  ls                  List directory contents
  ls -la              List all files (including hidden) in long format
  ls -lh              List files with human-readable sizes
  ls -R               List files recursively in subdirectories
  pwd                 Print the current working directory path
  cd /path            Change to the specified directory
  cd ~                Change to the home directory
  cd ..               Move up one directory level
  cd -                Switch to the previous directory
  mkdir dirname       Create a new directory
  mkdir -p a/b/c      Create nested directories (parents included)
  rmdir dirname       Remove an empty directory
  rm filename         Remove a file
  rm -r dirname       Remove a directory and its contents recursively
  rm -rf dirname      Force remove a directory without confirmation
  rm -i filename      Remove with confirmation prompt
  cp source dest      Copy a file to destination
  cp -r src dest      Copy a directory recursively
  cp -p src dest      Preserve file attributes while copying
  mv source dest      Move or rename a file/directory
  touch filename      Create an empty file or update file timestamps
  ln -s target link   Create a symbolic (soft) link
  ln target link      Create a hard link
  stat filename       Display detailed file information (size, permissions, etc.)
  file filename       Determine the file type
  tree                Display directory structure in tree format
  tree -L 2           Display tree structure limited to 2 levels deep

================================================================================
 3. VIEWING & EDITING FILE CONTENTS
================================================================================

  cat filename        Display entire file contents
  cat -n filename     Display file contents with line numbers
  tac filename        Display file contents in reverse order
  less filename       View file contents page by page (scrollable)
  more filename       View file contents page by page (forward only)
  head filename       Display first 10 lines of a file
  head -n 20 file     Display first 20 lines of a file
  tail filename       Display last 10 lines of a file
  tail -n 20 file     Display last 20 lines of a file
  tail -f logfile     Follow a file in real-time (useful for logs)
  nano filename       Open file in the nano text editor
  vi filename         Open file in the vi text editor
  vim filename        Open file in the vim text editor (improved vi)

================================================================================
 4. FILE PERMISSIONS & OWNERSHIP
================================================================================

  chmod 755 file      Set permissions: owner=rwx, group=rx, others=rx
  chmod 644 file      Set permissions: owner=rw, group=r, others=r
  chmod u+x file      Add execute permission for the owner
  chmod g+w file      Add write permission for the group
  chmod o-r file      Remove read permission for others
  chmod -R 755 dir    Recursively set permissions on a directory
  chmod a+x file      Add execute permission for all users
  chown user file     Change file owner
  chown user:grp file Change file owner and group
  chown -R user dir   Recursively change ownership of a directory
  chgrp group file    Change the group ownership of a file
  umask               Display the current default permission mask
  umask 022           Set default permissions for new files

  --- PERMISSION REFERENCE ---
  r = 4 (read)    w = 2 (write)    x = 1 (execute)
  Owner | Group | Others    Example: 755 = rwxr-xr-x

================================================================================
 5. USER & GROUP MANAGEMENT
================================================================================

  useradd username    Create a new user account
  useradd -m user     Create user with a home directory
  useradd -s /bin/bash user   Create user with specific shell
  usermod -aG grp user  Add user to a supplementary group
  usermod -L user     Lock a user account
  usermod -U user     Unlock a user account
  userdel username    Delete a user account
  userdel -r user     Delete user and their home directory
  passwd username     Set or change a user's password
  passwd -l user      Lock a user's password
  passwd -e user      Force password expiry (user must change at next login)
  groupadd groupname  Create a new group
  groupdel groupname  Delete a group
  groupmod -n new old Rename a group
  groups username     Display groups a user belongs to
  id username         Display user UID, GID, and group memberships
  su - username       Switch to another user account
  sudo command        Execute a command with superuser privileges
  sudo -i             Open an interactive root shell
  sudo -u user cmd    Run a command as another user
  visudo              Safely edit the /etc/sudoers file
  last                Show last logged-in users
  lastlog             Show most recent login for all users
  finger username     Display detailed user information

================================================================================
 6. PROCESS MANAGEMENT
================================================================================

  ps                  Display currently running processes
  ps aux              Display all running processes in detailed format
  ps -ef              Display all processes in full format
  top                 Interactive real-time view of running processes
  htop                Enhanced interactive process viewer (if installed)
  kill PID            Terminate a process by its PID
  kill -9 PID         Force kill a process immediately
  kill -15 PID        Gracefully terminate a process (SIGTERM)
  killall name        Kill all processes by name
  pkill pattern       Kill processes matching a pattern
  pgrep pattern       List PIDs of processes matching a pattern
  jobs                List background and suspended jobs
  bg %jobid           Resume a suspended job in the background
  fg %jobid           Bring a background job to the foreground
  nohup command &     Run a command that persists after logout
  nice -n 10 cmd      Start a process with modified scheduling priority
  renice -n 5 PID     Change the priority of a running process
  systemctl start svc     Start a service
  systemctl stop svc      Stop a service
  systemctl restart svc   Restart a service
  systemctl status svc    Check the status of a service
  systemctl enable svc    Enable a service to start at boot
  systemctl disable svc   Disable a service from starting at boot
  systemctl list-units    List all active systemd units

================================================================================
 7. TEXT PROCESSING & SEARCH
================================================================================

  grep pattern file       Search for a pattern in a file
  grep -i pattern file    Case-insensitive search
  grep -r pattern dir     Recursively search in a directory
  grep -n pattern file    Show line numbers with matches
  grep -v pattern file    Show lines that do NOT match
  grep -c pattern file    Count the number of matching lines
  grep -l pattern dir/*   List filenames that contain the pattern
  grep -E "regex" file    Extended regex (egrep equivalent)
  sed 's/old/new/' file   Replace first occurrence of 'old' with 'new'
  sed 's/old/new/g' file  Replace all occurrences of 'old' with 'new'
  sed -i 's/old/new/g' f  Edit the file in-place
  sed -n '5,10p' file     Print lines 5 through 10
  sed '/pattern/d' file   Delete lines matching a pattern
  awk '{print $1}' file   Print the first column/field of each line
  awk -F: '{print $1}' f  Use ':' as field separator, print first field
  awk '/pattern/' file    Print lines matching a pattern
  awk '{sum+=$1} END {print sum}' file   Sum values in the first column
  cut -d: -f1 file        Cut first field using ':' as delimiter
  cut -c1-5 file          Cut characters 1 through 5 from each line
  paste file1 file2       Merge lines of files side by side
  sort file               Sort lines of a file alphabetically
  sort -n file            Sort numerically
  sort -r file            Sort in reverse order
  sort -u file            Sort and remove duplicates
  uniq file               Remove adjacent duplicate lines
  uniq -c file            Count occurrences of duplicate lines
  tr 'a-z' 'A-Z'         Translate lowercase to uppercase
  tr -d 'chars'           Delete specified characters
  wc file                 Count lines, words, and characters
  wc -l file              Count lines only
  wc -w file              Count words only
  diff file1 file2        Compare two files line by line
  diff -u file1 file2     Compare in unified diff format
  patch file < diff.patch Apply a patch file to a file
  tee filename            Read from stdin, write to stdout AND file
  xargs                   Build and execute commands from stdin

================================================================================
 8. SEARCHING & FINDING FILES
================================================================================

  find /path -name "*.txt"        Find files by name pattern
  find /path -type f              Find only files
  find /path -type d              Find only directories
  find /path -size +100M          Find files larger than 100MB
  find /path -mtime -7            Find files modified in last 7 days
  find /path -user username       Find files owned by a user
  find /path -perm 755            Find files with specific permissions
  find /path -name "*.log" -delete  Find and delete matching files
  find /path -exec cmd {} \;      Execute a command on found files
  locate filename                 Quickly find files using database index
  updatedb                        Update the locate database
  which command                   Show the full path of a command
  whereis command                 Locate binary, source, man pages for a cmd
  type command                    Show what type a command is (alias, builtin)

================================================================================
 9. DISK USAGE & MANAGEMENT
================================================================================

  df -h               Display disk space usage in human-readable format
  df -T               Display disk space with filesystem type
  du -sh dirname      Display total size of a directory
  du -h --max-depth=1 Show sizes of immediate subdirectories
  du -ah dir          Show sizes of all files and directories
  fdisk -l            List all disk partitions
  lsblk               List all block devices
  mount device dir    Mount a filesystem
  umount dir          Unmount a filesystem
  blkid               Display block device attributes
  mkfs.ext4 /dev/sda1 Format a partition with ext4 filesystem
  fsck /dev/sda1      Check and repair a filesystem
  parted /dev/sda     Interactive partition editor
  dd if=src of=dst    Copy and convert files/devices (disk cloning)

================================================================================
 10. ARCHIVING & COMPRESSION
================================================================================

  tar -cvf archive.tar dir        Create a tar archive
  tar -xvf archive.tar            Extract a tar archive
  tar -czvf archive.tar.gz dir    Create a gzip-compressed tar archive
  tar -xzvf archive.tar.gz        Extract a gzip-compressed tar archive
  tar -cjvf archive.tar.bz2 dir   Create a bzip2-compressed tar archive
  tar -xjvf archive.tar.bz2       Extract a bzip2-compressed tar archive
  tar -tvf archive.tar            List contents of a tar archive
  gzip filename                   Compress a file with gzip
  gunzip filename.gz              Decompress a gzip file
  bzip2 filename                  Compress a file with bzip2
  bunzip2 filename.bz2            Decompress a bzip2 file
  zip archive.zip file1 file2     Create a zip archive
  zip -r archive.zip dir          Create a zip archive of a directory
  unzip archive.zip               Extract a zip archive
  unzip -l archive.zip            List contents of a zip archive
  xz filename                     Compress a file with xz
  unxz filename.xz                Decompress an xz file
  7z a archive.7z files           Create a 7z archive
  7z x archive.7z                 Extract a 7z archive

================================================================================
 11. NETWORKING COMMANDS
================================================================================

  ping host                   Test network connectivity to a host
  ping -c 5 host              Send 5 ping packets
  ifconfig                    Display/configure network interfaces (legacy)
  ip addr show                Display IP addresses of all interfaces
  ip link show                Display network interface status
  ip route show               Display the routing table
  ssh user@host               Connect to a remote host via SSH
  ssh -p 2222 user@host       SSH on a custom port
  ssh-keygen                  Generate SSH key pair
  ssh-copy-id user@host       Copy SSH key to a remote host
  scp file user@host:/path    Securely copy a file to a remote host
  scp user@host:/path local   Securely copy a file from a remote host
  scp -r dir user@host:/path  Securely copy a directory recursively
  rsync -avz src dest         Sync files/directories efficiently
  rsync -avz -e ssh src u@h:/p  Sync over SSH
  curl url                    Transfer data from/to a URL
  curl -o file url            Download a file from a URL
  curl -I url                 Fetch HTTP headers only
  wget url                    Download a file from the web
  wget -c url                 Resume a partially downloaded file
  netstat -tulnp              Display listening ports and associated processes
  ss -tulnp                   Modern replacement for netstat
  traceroute host             Trace the route packets take to a host
  nslookup domain             Query DNS for a domain
  dig domain                  Detailed DNS lookup
  host domain                 Simple DNS lookup
  route -n                    Display routing table (legacy)
  iptables -L                 List firewall rules
  firewall-cmd --list-all     List firewalld rules (RHEL/CentOS)
  ufw status                  Check UFW firewall status (Ubuntu)
  nmap host                   Network port scanner

================================================================================
 12. PACKAGE MANAGEMENT
================================================================================

  --- APT (Debian/Ubuntu) ---
  apt update                  Update package lists
  apt upgrade                 Upgrade all installed packages
  apt install package         Install a package
  apt remove package          Remove a package
  apt search package          Search for a package
  apt show package            Show package details
  apt autoremove              Remove unused dependencies
  dpkg -i package.deb         Install a .deb package
  dpkg -l                     List all installed packages
  dpkg -r package             Remove a .deb package

  --- YUM/DNF (RHEL/CentOS/Fedora) ---
  yum install package         Install a package
  yum update                  Update all packages
  yum remove package          Remove a package
  yum search package          Search for a package
  yum list installed          List all installed packages
  dnf install package         Install with DNF (Fedora/RHEL 8+)
  dnf update                  Update with DNF
  rpm -ivh package.rpm        Install an RPM package
  rpm -qa                     List all installed RPM packages
  rpm -e package              Remove an RPM package

================================================================================
 13. I/O REDIRECTION & PIPING
================================================================================

  command > file          Redirect stdout to a file (overwrite)
  command >> file         Redirect stdout to a file (append)
  command 2> file         Redirect stderr to a file
  command 2>&1            Redirect stderr to stdout
  command &> file         Redirect both stdout and stderr to a file
  command < file          Redirect file as input to a command
  command1 | command2     Pipe: send output of cmd1 as input to cmd2
  command | tee file      Write output to both the screen and a file
  command | xargs cmd2    Use output of command as arguments for cmd2

  Examples:
  ls -la | grep ".txt"           List only .txt files
  cat file | sort | uniq         Sort and remove duplicates
  ps aux | grep nginx            Find nginx processes
  cat access.log | awk '{print $1}' | sort | uniq -c | sort -rn
                                 Count and sort IP addresses from log

================================================================================
 14. SHELL SHORTCUTS & KEYBOARD COMMANDS
================================================================================

  Ctrl + C         Cancel/interrupt the current running command
  Ctrl + Z         Suspend the current process (send to background)
  Ctrl + D         Logout / send EOF (End Of File)
  Ctrl + L         Clear the terminal screen (same as 'clear' command)
  Ctrl + A         Move cursor to the beginning of the line
  Ctrl + E         Move cursor to the end of the line
  Ctrl + U         Cut/delete from cursor to beginning of line
  Ctrl + K         Cut/delete from cursor to end of line
  Ctrl + W         Delete the word before the cursor
  Ctrl + Y         Paste previously cut text (yank)
  Ctrl + R         Reverse search through command history
  Tab              Auto-complete file names and commands
  Tab Tab          Show all possible completions
  !!               Repeat the last command
  !n               Repeat command number n from history
  !string          Repeat last command starting with 'string'
  history          Display command history
  history -c       Clear command history

================================================================================
 15. CRON JOBS & SCHEDULING
================================================================================

  crontab -l           List current user's cron jobs
  crontab -e           Edit current user's cron jobs
  crontab -r           Remove all current user's cron jobs

  --- CRON FORMAT ---
  * * * * *  command
  | | | | |
  | | | | +--- Day of Week    (0-7, 0 and 7 = Sunday)
  | | | +----- Month          (1-12)
  | | +------- Day of Month   (1-31)
  | +--------- Hour           (0-23)
  +----------- Minute         (0-59)

  Examples:
  0 2 * * *     command       Run daily at 2:00 AM
  */15 * * * *  command       Run every 15 minutes
  0 0 * * 0     command       Run every Sunday at midnight
  0 9 1 * *     command       Run at 9 AM on the first of every month
  30 18 * * 1-5 command       Run at 6:30 PM on weekdays

  at now + 5 minutes          Schedule a one-time job 5 minutes from now
  atq                         List pending at jobs
  atrm jobid                  Remove a pending at job

================================================================================
 16. SYSTEM MANAGEMENT & POWER
================================================================================

  shutdown -h now        Shut down the system immediately
  shutdown -h +10        Shut down in 10 minutes
  shutdown -r now        Reboot the system immediately
  shutdown -c            Cancel a scheduled shutdown
  reboot                 Reboot the system
  poweroff               Power off the system
  halt                   Halt the system
  init 0                 Shutdown (runlevel 0)
  init 6                 Reboot (runlevel 6)
  modprobe module        Load a kernel module
  lsmod                  List loaded kernel modules
  modinfo module         Display information about a kernel module

================================================================================
 17. LOG MANAGEMENT
================================================================================

  journalctl                     View systemd journal logs
  journalctl -u service          View logs for a specific service
  journalctl -f                  Follow journal logs in real-time
  journalctl --since "1 hour ago"  Show logs from last hour
  cat /var/log/syslog            View system log (Debian/Ubuntu)
  cat /var/log/messages          View system log (RHEL/CentOS)
  cat /var/log/auth.log          View authentication log
  cat /var/log/kern.log          View kernel log
  tail -f /var/log/syslog        Follow syslog in real-time
  logrotate                      Rotate and manage log files

================================================================================
 18. ENVIRONMENT VARIABLES
================================================================================

  echo $PATH             Display the PATH environment variable
  echo $HOME             Display the home directory path
  echo $USER             Display the current username
  echo $SHELL            Display the current shell
  export VAR=value       Set an environment variable for the session
  export PATH=$PATH:/new Add a directory to PATH
  unset VAR              Remove an environment variable
  source ~/.bashrc       Reload bash configuration
  . ~/.bashrc            Same as source (reload config)
  alias ll='ls -la'      Create a command alias
  unalias ll             Remove an alias

================================================================================
 19. SSH & REMOTE ACCESS
================================================================================

  ssh user@host              Connect to a remote server
  ssh -p 2222 user@host      Connect on a custom port
  ssh -i key.pem user@host   Connect using a private key
  ssh-keygen -t rsa -b 4096  Generate a 4096-bit RSA key pair
  ssh-keygen -t ed25519      Generate an Ed25519 key pair
  ssh-copy-id user@host      Copy public key to remote after
  ssh-agent bash             Start SSH agent
  ssh-add ~/.ssh/id_rsa      Add private key to SSH agent
  sshfs user@host:/remote /local  Mount remote directory via SSH
  ~/.ssh/config              SSH client configuration file
  ~/.ssh/authorized_keys     File for authorized public keys
  ~/.ssh/known_hosts         File of known remote host keys

================================================================================
 20. USEFUL COMMAND COMBINATIONS & TIPS
================================================================================

  --- FIND AND PROCESS ---
  find . -name "*.log" -exec rm {} \;       Find and delete all .log files
  find . -type f -name "*.py" | xargs grep "import"
                                            Search for "import" in .py files
  find / -size +500M -exec ls -lh {} \;     Find large files over 500MB

  --- MONITORING ---
  watch -n 5 'df -h'          Run 'df -h' every 5 seconds
  vmstat 1 5                  Virtual memory stats every 1s (5 times)
  iostat                      I/O statistics for devices
  sar                         System activity reporter
  strace -p PID               Trace system calls of a process
  lsof -i :80                 List processes using port 80

  --- TEXT MANIPULATION ---
  cat file | tr -s ' '        Squeeze multiple spaces to one
  echo "Hello" | rev          Reverse a string
  echo "text" | base64        Base64 encode
  echo "dGV4dA==" | base64 -d Base64 decode

  --- SYSTEM INFO ONE-LINERS ---
  cat /etc/os-release         Show OS distribution info
  lsb_release -a              Show LSB distribution info
  getconf LONG_BIT            Check if 32-bit or 64-bit
  nproc                       Show number of processing units
  arch                        Show machine architecture

  --- DISK & MEMORY ---
  sync; echo 3 > /proc/sys/vm/drop_caches   Clear memory cache (as root)
  swapon --show               Display swap usage
  free -h                     Display memory usage

================================================================================
                         END OF LINUX CHEATSHEET
       Author: Samson J
       LinkedIn: https://www.linkedin.com/in/samson-j-997403234
================================================================================
