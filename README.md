# PHPMyAdmin Docker Container for WPLib Box
This is the repository for the [PHPMyAdmin](https://www.phpmyadmin.net/) Docker container implemented for [WPLib-Box](https://github.com/wplib/wplib-box).
It currently provides versions 4.6 4.7


## Supported tags and respective Dockerfiles

`4.7` , `4.7`, `latest` _([4.7/Dockerfile](https://github.com/wplib/phpmyadmin-docker/blob/master/4.7/Dockerfile))_

`4.6` , `4.6` _([4.6/Dockerfile](https://github.com/wplib/phpmyadmin-docker/blob/master/4.6/Dockerfile))_


## Setup
Simply clone this repository to your local machine

`git clone https://github.com/wplib/phpmyadmin-docker.git`


## Building
`make build` - Build Docker images. Build all versions from the base directory or specific versions from each directory.


`make list` - List already built Docker images. List all versions from the base directory or specific versions from each directory.


`make clean` - Remove already built Docker images. Remove all versions from the base directory or specific versions from each directory.


## Runtime
When you `cd` into a version directory you can also perform a few more actions.

`make start` - Spin up a Docker container with the correct runtime configs.


`make stop` - Stop a Docker container.


`make run` - Run a Docker container in the foreground, (all STDOUT and STDERR will go to console). The Container be removed on termination.


`make shell` - Run a shell, (/bin/bash), within a Docker container.


`make rm` - Remove the Docker container.


