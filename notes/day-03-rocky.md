# Day 3 — users, groups, sudo

Rocky Linux 10.2 (`rocky01`).

## What I practiced

- Read `/etc/passwd` and `/etc/group`
- `useradd -m -c`, `passwd`, `userdel -r`
- Groups: `groupadd`, `usermod -aG`, `gpasswd -d`
- Why `-a` matters with `-G`
- `wheel` group = sudo on Rocky/RHEL
- Drop-in files in `/etc/sudoers.d/` instead of editing `/etc/sudoers` directly
- `visudo -c` to check syntax
- Lock/unlock: `usermod -L` / `-U`, `passwd -S`

## Commands

```bash
id
getent passwd pipo labuser
getent group webteam

sudo useradd -m -c "Helpdesk intern" intern
sudo passwd intern
sudo groupadd ops
sudo usermod -aG ops intern
sudo gpasswd -d intern ops

groups pipo
sudo usermod -aG wheel intern
su - intern
sudo whoami
exit
sudo gpasswd -d intern wheel

echo 'intern ALL=(ALL) NOPASSWD: /usr/bin/systemctl status sshd' | sudo tee /etc/sudoers.d/intern
sudo chmod 440 /etc/sudoers.d/intern
sudo visudo -c

sudo usermod -L intern
sudo passwd -S intern
sudo usermod -U intern
