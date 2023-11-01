## monitoring.sh
### uname 
- Prints system information.
- The `-a` option results in the following output (omitting `-p` and `-i` if the result is unknown):
    - Linux: kernel name
    - intraid42: host name
    - 6.1.0-13-amd64: kernel release
    - #1 SMP PREEMPT_DYNAMIC Debian 6.1.55-1 (2023-09-29): kernel version
    - x86_64: machine hardware name
    - GNU/Linux: operating system name

### /proc/cpuinfo
CPU information file.
- `physical id`: ID of the physical CPU.
  - The number of IDs represents the number of physical CPUs.
- `processor`: ID of the virtual processor.
  - The number of processor IDs represents the number of virtual CPUs.
- `cpu cores`: The number of physical cores per CPU.
- `siblings`: The number of virtual cores per CPU.

### free
Displays the amount of free and used memory in the system.
The information is gathered by parsing `/proc/meminfo`.
- Options: `-b`, `-k`, `-m`, `-g`...
  - Specify the display format corresponding to the order (bytes, kibibytes, mebibytes, gibibytes).
- Option `-h`
  - Displays the number of bytes with units.

## df
Reports file system disk space usage.
- Option `-B`
  - Specifies the scale size.
  - `-BM`: Prints size in units of 1,048,576 bytes.
  - `-BG`: Prints size in units of gigabytes.

## top
Displays Linux processes.
- `-b`: batch mode (default: interactive mode)
- `-n`: number of iterations

## who
Displays information about users who are currently logged in.
- `-a`: same as -b -d --login -p -r -t -T -u
- `-b`: displays time of the last system boot
- `-d`: displays dead processes
- `-u`: displays a list of users logged in
- `-s`: displays only name, line, and time (default)

## ss
ss is used to dump socket statistics.
- `-t`: displays TCP sockets
- `-u`: displays UDP sockets
- `-l`: displays only listening sockets
- `-n`: does not try to resolve service names
- `-e`: shows detailed socket information
- `-p`: shows the process using the socket
- `-o`: shows time information

## users

## hostname
Shows or sets the system's host name.
- `-I`: displays all network addresses of the host

## ip
Shows / manipulates routing, network devices, interfaces, and tunnels.

## journalctl
journalctl may be used to query the contents of the systemd(1) journal as written by systemd-journald.service(8).
