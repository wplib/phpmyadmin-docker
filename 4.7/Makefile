#
# Makefile for Docker
# 

PROJECT		?= wplib
NAME		?= phpmyadmin
VERSION		?= 4.7
MAJORVERSION	?= 
PORTS		?= -p 8081:80
VOLUMES		?= 
ENV		?= -e PMA_HOST=172.18.0.1
# ENV		?= -e PMA_HOST=dbhost --add-host "dbhost:172.18.0.1"

LATEST		?= 1

IMAGE_NAME	?= $(PROJECT)/$(NAME)
CONTAINER_NAME	?= $(PROJECT)_$(NAME)_$(VERSION)


.PHONY: build push release clean shell run start stop rm

################################################################################
# Image related commands.

build: Dockerfile
	-docker build -t $(IMAGE_NAME):$(VERSION) --build-arg MYPHPADMIN_VERSION=$(VERSION) .
ifneq ($(MAJORVERSION),)
	-docker build -t $(IMAGE_NAME):$(MAJORVERSION) --build-arg MYPHPADMIN_VERSION=$(MAJORVERSION) .
endif
ifeq ($(LATEST),1)
	docker build -t $(IMAGE_NAME):latest --build-arg MYPHPADMIN_VERSION=latest .
endif

push:
	-docker push $(IMAGE_NAME):$(VERSION)
ifneq ($(MAJORVERSION),)
	-docker push $(IMAGE_NAME):$(MAJORVERSION)
endif
ifeq ($(LATEST),1)
	docker push $(IMAGE_NAME):latest
endif

release: build
	make push -e VERSION=$(VERSION)

clean:
	docker image rm $(IMAGE_NAME):$(VERSION)
ifneq ($(MAJORVERSION),)
	docker image rm $(IMAGE_NAME):$(MAJORVERSION)
endif
ifeq ($(LATEST),1)
	docker image rm $(IMAGE_NAME):latest
endif

list:
	docker image ls $(IMAGE_NAME):$(VERSION)
ifneq ($(MAJORVERSION),)
	docker image ls $(IMAGE_NAME):$(MAJORVERSION)
endif
ifeq ($(LATEST),1)
	docker image ls $(IMAGE_NAME):latest
endif


################################################################################
# Container related commands.

shell:
	docker run --rm --name $(CONTAINER_NAME) -i -t --network wplibbox $(PORTS) $(VOLUMES) $(ENV) $(IMAGE_NAME):$(VERSION) /bin/bash

run:
	docker run --rm --name $(CONTAINER_NAME) --network wplibbox $(PORTS) $(VOLUMES) $(ENV) $(IMAGE_NAME):$(VERSION)

start:
	docker run -d --name $(CONTAINER_NAME) --restart unless-stopped --network wplibbox $(PORTS) $(VOLUMES) $(ENV) $(IMAGE_NAME):$(VERSION)

stop:
	docker stop $(CONTAINER_NAME)

rm:
	docker container rm $(CONTAINER_NAME)


################################################################################
default: build

