# NGINX Docker Setup

## Folder Setup
```bash
sudo mkdir -p /hdds/swraid/nginx/www
sudo chown $USER:$USER /hdds/swraid/nginx/www
```

## Running the Container
```bash
docker run --name alethkar-nginx \
  -v /hdds/swraid/nginx/www:/hmnt/www:ro \
  -p 80:80 -d nginx
```

## Notes
Static files are placed in /hdds/swraid/nginx/www
