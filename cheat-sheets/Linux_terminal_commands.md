# 🐧 Linux Terminal Cheat Sheet
---

##  File & Directory Commands
```
pwd             # Print current directory
ls              # List files
ls -la          # Long list incl. hidden
cd /path/       # Change directory
mkdir newdir    # Create directory
touch file.txt  # Create new file
cp src dst      # Copy file or dir
mv old new      # Move or rename
rm file.txt     # Remove file
rm -r dir/      # Remove directory
tree            # Directory structure

```

---

##  File Viewing
```
cat file        # Show contents
less file       # Scroll view
head file       # Top 10 lines
tail file       # Last 10 lines
tail -f logfile # Live log view
nano file       # Edit file (basic)
vim file        # Edit file (advanced)

```

---

##  Search & Find
```
grep "text" file          # Search text in file
grep -r "text" dir/       # Recursive grep
find . -name "*.log"      # Find by name
find / -type f -name file # Full system search
locate file_name          # Find file (needs `mlocate`)

```

---

##  Package Management (Debian)
```
sudo apt update
sudo apt install pkg
sudo apt remove pkg

```

---

## Networking
```
ip a                # IP addresses
ping host           # Ping target
curl http://site    # Fetch URL
wget URL            # Download file
scp file user@host:/path  # Secure copy
ssh user@host       # SSH login
netstat -tulpn      # Ports in use (use `ss` if deprecated)

```

---

## Permissions
```
chmod +x file       # Make executable
chmod 755 file      # Set permissions
chown user:group file  # Change owner

```

---

##  System Monitoring
```
top             # Live processes
htop            # Better top (install it)
ps aux          # All processes
kill PID        # Kill process
df -h           # Disk usage
du -sh *        # Folder sizes
free -h         # Memory usage
uptime          # System uptime
uname -a        # Kernel info
lscpu           # CPU info
lsblk           # Disk & partitions

```
## Archiving & Compression
```
tar -czf out.tar.gz dir/     # Compress dir
tar -xzf file.tar.gz         # Extract tar.gz
zip out.zip file             # Zip file
unzip file.zip               # Unzip

```
---

> Whever in disarry just use `man` for a quick manual