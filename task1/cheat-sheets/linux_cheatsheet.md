# Linux & Networking Fundamentals Cheat-Sheet

## 1. File System Navigation & Inspection
- `pwd` : Print Current Working Directory.
- `ls -la` : List all files including hidden files, with long permissions formatting.
- `cd /path/to/dir` : Change directory.
- `tree -L 2` : Display tree structure up to depth 2.
- `cat file.txt` : Output entire content of file.
- `less file.txt` : Interactive pager for reading large logs.
- `head -n 20 file.txt` : View first 20 lines.
- `tail -f /var/log/syslog` : Follow log additions in real time.

## 2. File & Directory Permissions
- `chmod 755 script.sh` : Owner (rwx), Group (rx), Others (rx).
- `chmod 600 id_rsa` : Owner (rw-), Group (---), Others (---).
- `chmod +x run.sh` : Add executable flag to current file.
- `chown user:group filename` : Change file ownership and group.
- `umask` : Display or set default file creation permissions mask.

## 3. Package Management
- `sudo apt update && sudo apt upgrade -y` : Synchronize repository lists and upgrade packages.
- `sudo apt install <package> -y` : Install designated software.
- `sudo apt remove --purge <package>` : Remove software along with configuration files.
- `dpkg -i package.deb` : Install a standalone Debian binary package.
- `dpkg -l | grep <name>` : Search installed packages list.

## 4. Networking Diagnostic Commands
- `ip a` / `ifconfig` : View assigned IP and network interface hardware states.
- `ip route show` : Display active routing table and default gateway.
- `ping -c 4 <ip>` : Send 4 ICMP echo requests to verify node reachability.
- `traceroute <ip>` : Identify network hops and routing paths to target.
- `netstat -tulnp` / `ss -tulnp` : Display all listening TCP/UDP ports and associated PIDs.
- `arp -a` : Display local system ARP cache table.

## 5. Security & Network Debugging Tools
- `nc -lvnp <port>` : Initialize Netcat listening socket.
- `nc -vn <ip> <port>` : Connect to target IP and port to grab service banners.
- `nmap -sn <subnet>` : Perform ARP ping discovery scan across subnet.
- `tcpdump -i any -nn port 80` : Capture and stream plaintext HTTP traffic from CLI.