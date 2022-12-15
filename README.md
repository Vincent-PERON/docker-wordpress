# docker-wordpress

A Docker Compose project template for an nginx, WordPress, MariaDB and phpMyAdmin stack.

## Usage

```sh
git clone 
cd docker-wordpress  
cp .env.example .env # copy example environmental variables
vim .env             # and adjust to your needs
docker-compose up    # with `sudo` if necessary 
```

If you have configured everything correctly, WordPress should by available at [http://127.0.0.1:8000](http://127.0.0.1:8000) and phpMyAdmin at [http://127.0.0.1:8001](http://127.0.0.1:8001). It takes a bit of time for database initialization to settle down, so don't get discouraged by wordpress showing a database connection error.

It's not compatible with `podman` since both WordPress and phpMyAdmin image [listen on the same port](https://github.com/containers/podman-compose/issues/244) internally (`80`), and [I don't wanna bother looking for a proper solution](https://github.com/containers/podman-compose/blob/master/docs/Mappings.md).
