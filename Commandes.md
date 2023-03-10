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
  -PermitRootLogin no
sudo systemctl restart sshd
sudo adduser AllowedUser
sudo adduser AllowedUser sudo
ssh-copy-id AllowedUser@<bastion-host-ip>
ssh -i <private-key-file> <username>@<bastion-host-ip>
```

```bash
sudo nano /etc/ssh/sshd_config
Host private_network
    HostName private_network_hostname_or_IP
    User username
    ProxyJump bastion_host_username@bastion_host_IP
sudo systemctl restart sshd
```
Logs ssh
```BASH
sudo nano /etc/ssh/sshd_config
  -SyslogFacility AUTHPRIV
sudo systemctl restart sshd
sudo touch /var/log/ssh.log
sudo useradd Loguser
sudo passwd Loguser
sudo usermod -aG adm Loguser
sudo chown Loguser /var/log/ssh.log
sudo chmod 600 /var/log/ssh.log
```
tentatives de co stockées dans /var/log/ssh.log et Loguser peut les lire.
