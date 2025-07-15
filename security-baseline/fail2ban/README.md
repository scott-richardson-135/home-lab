# fail2ban setup

fail2ban is an IPS (intrusion prevention system) that helps prevent brute force attacks. Basically it will block IPs after several failed login attempts and locks them in jail for a bit.
(Right now I only have it configured for sshd, and I also have password ssh disabled so it's not doing a whole lot but it's the thought that counts)

## Installation
Run:
```bash
sudo apt install fail2ban
```
Then it will run as a service and start automatically

## Configuration
jail.conf is the default config file. Don't edit this, instead create a jail.local file
```bash
sudo cp /etc/fail2ban/jail.conf /etc/fail2ban/jail.local
```
Then you can edit the jail.local file to change config. The changes I made are listed [here](https://github.com/scott-richardson-135/home-lab/blob/main/security-baseline/fail2ban/jail.local).

Important to note, make sure enabled is set to true underneath the service you want to enable

I had some issues with default macros for the (%(sshd_log)s, %(sshd_backend)s), so i just put in the actual values instead (/var/log/auth.log, systemd)

## Start the service
To start fail2ban and have it startup on boot:
```bash
sudo systemctl enable fail2ban
sudo systemctl start fail2ban
```
and to check my jail (just ssh for now):
```bash
sudo fail2ban-client status sshd
```
and that's it!

## More to come, probably
As I mentioned before, it's not doing a whole lot right now...
Someday I wanna expand to NGINX or Gitea jails too (if those get deployed), but right now I'm kinda just trying to learn how all this works :)
