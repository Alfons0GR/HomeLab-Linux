# Day 1 – Rocky Linux 10.2

## What I did

- Installed the VM (`rocky01`), NAT, admin user
- Practiced `dnf`, users, `chmod 640`
- Edited `/etc/motd` with `sudo nano`
- Shutdown: `sudo poweroff`

## Commands

```bash
whoami
hostname
ip a
sudo dnf update -y
mkdir -p ~/lab/docs
echo "hola lab" > ~/lab/docs/nota.txt
chmod 640 ~/lab/docs/nota.txt
echo "Lab Rocky - pipo" | sudo tee /etc/motd
