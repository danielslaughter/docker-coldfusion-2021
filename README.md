# Docker, Commandbox & ColdFusion 2021

This implementation works on Apple Silicon (M1/M2) and likely other systems. 🍎 💻 

## Initializing

Create the Docker volume "cf2021_volume".
```bash
docker volume create cf2021_volume
```

Build the Docker image.
```bash
docker-compose build --no-cache
```

Start the Docker container. The first time the container is started the ColdFusion Package Manager will download its dependencies. Subsequent starts will initialize faster.
```bash
docker-compose up
```
Public URL: http://localhost/ \
Admin URL: http://localhost/CFIDE/administrator/