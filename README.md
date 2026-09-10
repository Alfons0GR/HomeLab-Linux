# HomeLab-Linux

Lab notes and hands-on practice for Linux system administration in VirtualBox.

## Lab setup

- **Host:** Windows + Oracle VirtualBox
- **VM 1:** Ubuntu Server
- **VM 2:** Rocky Linux 10.2 (`rocky01`)

Network: NAT on both VMs.

## Day 1 — Rocky Linux

- Installed Rocky Linux 10.2 (admin user, root password enabled, NAT)
- First commands: `whoami`, `hostname`, `ip a`, `dnf`
- Users, groups, and file permissions (`chmod 640`)
- Set `/etc/motd` with `sudo` and `nano`
- Clean shutdown: `sudo poweroff`

### Notes from Day 1

- `~` is the home directory. System paths like `/etc/motd` are not under `~` and need `sudo`.
- `mkdir -p` creates directories. Do not use it on a path that should be a file.
- My first mistake was using `mkdir -p ~/etc/motd` which created directories, not the intended `/etc/motd` file, I deleted them using `rmdir` then used `sudo nano /etc/motd`.
- On Rocky/RHEL the package manager is `dnf` (Ubuntu uses `apt`).
- Remove the installer ISO after install so the VM boots from disk.

## How I use this repo

I log commands, mistakes, and what I learned. No passwords, keys, or secrets.
