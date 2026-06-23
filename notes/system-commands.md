# System Administration Commands

## systemd (Services)

`systemctl status [service]`

* Show detailed status of a service.
* First command to run when troubleshooting a service.

`systemctl list-unit-files --state=enabled`

* Show services configured to start at boot.

`sudo systemctl start [service]`

* Start a service immediately.

`sudo systemctl stop [service]`

* Stop a running service.

`sudo systemctl restart [service]`

* Restart a service.

`sudo systemctl enable [service]`

* Enable a service to start automatically at boot.

`sudo systemctl disable [service]`

* Disable automatic startup at boot.

`systemctl --failed`

* Show failed services.

---

## Logs

`journalctl`

* View system logs.

`journalctl -b`

* View logs from the current boot.

`journalctl -b -1`

* View logs from the previous boot.

`journalctl -u [service]`

* View logs for a specific service.

`journalctl -f`

* Follow logs live (similar to tail -f).

---

## Processes

`htop`

* Interactive process viewer.
* Shows CPU, memory, and running processes.

`ps aux`

* List all running processes.

`pgrep NAME`

* Find process IDs by name.

`kill PID`

* Send a termination signal to a process.

`kill -9 PID`

* Force kill a process.

---

## Memory

`free -h`

* Show RAM and swap usage in human-readable format.

`vmstat`

* Show virtual memory statistics.

---

## Storage

`df -h`

* Show filesystem usage.

`du -sh DIRECTORY`

* Show total size of a directory.

`lsblk`

* Show block devices (disks and partitions).

`lsblk -f`

* Show block devices plus filesystem information.

`mount`

* Show mounted filesystems.

---

## Time

`timedatectl status`

* Show time, timezone, and synchronization status.

`sudo timedatectl set-ntp true`

* Enable automatic NTP synchronization.

`timedatectl timesync-status`

* Show which NTP server is being used.

`timedatectl list-timezones`

* List available timezones.

`sudo timedatectl set-timezone Europe/Bucharest`

* Set the system timezone.

---

## Boot Analysis

`systemd-analyze`

* Show total boot time.

`systemd-analyze blame`

* Show which services took the longest to start.

`systemd-analyze critical-chain`

* Show boot dependency chain.

---

## Hardware

`lscpu`

* Show CPU information.

`lspci`

* Show PCI devices (GPUs, network cards, etc.).

`lsusb`

* Show USB devices.

`dmesg`

* Show kernel messages.

`dmesg -w`

* Follow kernel messages live.

---

## Package Management (Arch)

`sudo pacman -Syu`

* Synchronize repositories and update the system.

`pacman -Qe`

* List explicitly installed packages.

`pacman -Qs PACKAGE`

* Search installed packages.

---

# Top 10 Commands To Memorize

`systemctl status [service]`

* Check service health.

`journalctl -u [service]`

* Check service logs.

`journalctl -b`

* Check boot logs.

`htop`

* Monitor processes and resources.

`free -h`

* Check memory usage.

`lsblk -f`

* Check disks and filesystems.

`df -h`

* Check storage usage.

`timedatectl status`

* Check time synchronization.

`systemd-analyze blame`

* Diagnose slow boot times.

`sudo pacman -Syu`

* Update the system.

