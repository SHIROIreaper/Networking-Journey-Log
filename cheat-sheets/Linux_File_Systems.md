# 🐧 Linux Filesystem Cheat Sheet

A quick reference guide to understand Linux directory structure and their uses.
[Linux File System Tree Structure](https://i.ytimg.com/vi/bbmWOjuFmgA/maxresdefault.jpg)

---

## 📁 Root Directory `/`
- The top of the filesystem hierarchy.
- Everything starts from here.

---

## 📂 Essential Directories

### `/bin`
- Essential user binaries (commands like `ls`, `cp`, `mv`, `rm`).
- Needed in **single-user** and **rescue** modes.

### `/boot`
- Bootloader files (Linux kernel, GRUB config).
- Required to boot the system.

### `/dev`
- Represents devices as files (e.g., `/dev/sda`, `/dev/null`).

### `/etc`
- System-wide configuration files.
- Examples: `/etc/passwd`, `/etc/hosts`, `/etc/fstab`.

### `/home`
- Home directories for users (`/home/username`).

### `/lib` & `/lib64`
- Shared libraries for binaries in `/bin` and `/sbin`.
- `/lib64` holds 64-bit libraries (on 64-bit systems).

---

## 📂 Administrative & Advanced

### `/media`
- Auto-mounted removable media (USB, CD-ROM).

### `/mnt`
- Manual mount point for temporary mounts.

### `/opt`
- Optional software packages (e.g., `/opt/google/chrome`).

### `/proc`
- Virtual filesystem with process and kernel info (`/proc/cpuinfo`).

### `/root`
- Home directory of the `root` user.

### `/run`
- Runtime system info (since last boot).

### `/sbin`
- System binaries (e.g., `shutdown`, `mkfs`, `reboot`).
- Typically requires `sudo`.

### `/srv`
- Data served by system services (e.g., HTTP, FTP).

### `/sys`
- Interface to the kernel and device tree (e.g., `/sys/class/net/`).

### `/tmp`
- Temporary files (cleared at reboot).

---

## 📂 `/usr` Hierarchy (User Software)

### `/usr/bin`
- Non-essential user binaries.

### `/usr/sbin`
- Non-essential system binaries (admin tools).

### `/usr/lib`
- Libraries for `/usr/bin` and `/usr/sbin`.

### `/usr/local`
- Locally installed software (not managed by package manager).

#### `/usr/local/bin`
- User-installed executables.

#### `/usr/local/lib`
- User-installed libraries.

#### `/usr/local/etc`
- Configs for local installs.

---

## 📂 `/var` — Variable Data

### `/var/log`
- System logs.

### `/var/tmp`
- Temporary files **persistent** across reboots.

### `/var/spool`
- Queued data (print jobs, mail queue).

---

## 🧠 Tips

- Use `ls -l` to inspect permissions.
- Use `df -h` to view disk usage by filesystem.
- Use `du -sh *` inside a directory to see space usage.

---

📌 *Remember:* Always be cautious with `sudo` and avoid modifying system directories unless necessary.
