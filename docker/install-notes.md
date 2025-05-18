# Docker Installation

## Install Docker and Compose
```bash
sudo apt install docker.io docker-compose docker-doc
```

## Enable Docker to Start on Boot
Allows running docker without sudo (you'll need to log out and back in)
```bash
sudo systemctl enable docker
sudo systemctl start docker
```

## Add user to docker group
```bash
sudo usermod/ -aG docker <username>
```
