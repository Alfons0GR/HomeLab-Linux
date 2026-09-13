# Day 1 — Ubuntu Server

First day on the Ubuntu Server VM (VirtualBox, NAT).

## What I did

- Confirmed hostname, user, and `/etc/os-release`
- Checked network: `ip a`, `ping 8.8.8.8`
- Updated packages with `apt` (not `dnf`)
- Created `labuser` and group `webteam`
- Practiced `mkdir`, `echo`, `chmod 640`
- Installed and enabled OpenSSH (`ssh` service)
- Set `/etc/motd`
- Clean shutdown: `sudo poweroff`

## Commands

```bash
whoami
hostname
cat /etc/os-release
ip a
ping -c 3 8.8.8.8
sudo whoami

sudo apt update
sudo apt upgrade -y

sudo adduser labuser
sudo groupadd webteam
sudo usermod -aG webteam labuser
id labuser

mkdir -p ~/lab/docs
echo "hola lab" > ~/lab/docs/nota.txt
chmod 640 ~/lab/docs/nota.txt
ls -l ~/lab/docs

sudo apt install -y openssh-server
sudo systemctl enable --now ssh
systemctl status ssh

echo "Lab Ubuntu - pipo" | sudo tee /etc/motd
