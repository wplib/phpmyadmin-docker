![PHPMyAdmin 4.8.x](https://img.shields.io/badge/PHPMyAdmin-4.8.x-green.svg)
![PHPMyAdmin 4.7.x](https://img.shields.io/badge/PHPMyAdmin-4.7.x-green.svg)
![PHPMyAdmin 4.6.x](https://img.shields.io/badge/PHPMyAdmin-4.6.x-green.svg)

![WPLib-Box](https://github.com/wplib/wplib.github.io/raw/master/WPLib-Box-100x.png)


# PHPMyAdmin Docker Container for WPLib Box
This is the repository for the [PHPMyAdmin](https://www.phpmyadmin.net/) Docker container implemented for [WPLib-Box](https://github.com/wplib/wplib-box).
It currently provides versions 4.6.x 4.7.x 4.8.x


## Supported tags and respective Dockerfiles

`4.8.0`, `4.8`, `latest` _([4.8.0/Dockerfile](https://github.com/wplib/phpmyadmin-docker/blob/master/4.8.0/Dockerfile))_

`4.7.0`, `4.7` _([4.7/Dockerfile](https://github.com/wplib/phpmyadmin-docker/blob/master/4.7/Dockerfile))_

`4.6.0`, `4.6` _([4.6/Dockerfile](https://github.com/wplib/phpmyadmin-docker/blob/master/4.6/Dockerfile))_


## Using this container.
If you want to use this container as part of WPLib, then use the Docker Hub method.
Or you can use the GitHub method to build and run the container.


## Using it from Docker Hub

### Links
(Docker Hub repo)[https://hub.docker.com/r/wplib/phpmyadmin/]

(Docker Cloud repo)[https://cloud.docker.com/swarm/wplib/repository/docker/wplib/phpmyadmin/]


### Setup from Docker Hub
A simple `docker pull wplib/phpmyadmin` will pull down the latest version.


### Runtime from Docker Hub
start - Spin up a Docker container with the correct runtime configs.

`docker run -d --name wplib_phpmyadmin_4.7 --restart unless-stopped --network wplibbox -p 8081:80  wplib/phpmyadmin:4.7`

stop - Stop a Docker container.

`docker stop wplib_phpmyadmin_4.7`

run - Run a Docker container in the foreground, (all STDOUT and STDERR will go to console). The Container be removed on termination.

`docker run --rm --name wplib_phpmyadmin_4.7 --network wplibbox -p 8081:80  wplib/phpmyadmin:4.7`

shell - Run a shell, (/bin/bash), within a Docker container.

`docker run --rm --name wplib_phpmyadmin_4.7 -i -t --network wplibbox -p 8081:80  wplib/phpmyadmin:4.7 /bin/bash`

rm - Remove the Docker container.

`docker container rm wplib_phpmyadmin_4.7`


## Using it from GitHub repo

### Setup from GitHub repo
Simply clone this repository to your local machine

`git clone https://github.com/wplib/phpmyadmin-docker.git`


### Building from GitHub repo
`make build` - Build Docker images. Build all versions from the base directory or specific versions from each directory.


`make list` - List already built Docker images. List all versions from the base directory or specific versions from each directory.


`make clean` - Remove already built Docker images. Remove all versions from the base directory or specific versions from each directory.


`make push` - Push already built Docker images to Docker Hub, (only for WPLib admins). Push all versions from the base directory or specific versions from each directory.


### Runtime from GitHub repo
When you `cd` into a version directory you can also perform a few more actions.

`make start` - Spin up a Docker container with the correct runtime configs.


`make stop` - Stop a Docker container.


`make run` - Run a Docker container in the foreground, (all STDOUT and STDERR will go to console). The Container be removed on termination.


`make shell` - Run a shell, (/bin/bash), within a Docker container.


`make rm` - Remove the Docker container.


`make test` - Will issue a `stop`, `rm`, `clean`, `build`, `create` and `start` on a Docker container.


