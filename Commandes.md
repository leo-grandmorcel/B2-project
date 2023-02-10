## Reverse proxy Caddy

```bash
dnf install 'dnf-command(copr)'
dnf copr enable @caddy/caddy
dnf install caddy
dnf install caddy
```

## Bastion SSH

```bash
sudo apt update
sudo apt upgrade -y
sudo apt install openssh-server
sudo nano /etc/ssh/sshd_config
  -PasswordAuthentication no
  -PubkeyAuthentication yes
sudo systemctl restart sshd
sudo adduser AllowedUser
sudo adduser AllowedUser sudo
ssh-copy-id AllowedUser@<bastion-host-ip>
ssh -i <private-key-file> <username>@<bastion-host-ip>
```
