# DevOps Docker Hand-In

The DevOps Docker Hand-In exercise

## Task 1

Toilet task link: <https://hub.docker.com/r/papatemps/toilet>

> Describe what you could do in order to:

* **Minimize the layers in the image**
  * Since the keyword RUN, COPY and ADD create layers, you want to minimize the use of these.

* **Minimize the overall image size. You are allowed to change everything, as long as the following command `docker run <yourusername>/toilet hello world` successfully displays a colorful variation of `hello world`**
  * To do this you should try to use in general lightweight images. As an example instead of using the ubuntu image in this task, we could use a alpine image, which is significantly lower in size.

## Task 2

> Describe what kind of commands you would use to delete the containers and create new ones.

* To delete the containers i would use the following command:
  * ``docker-compose down`` stops and removes containers
* To create the containers i would use the following command:
  * ``docker-compose up`` starts new containers

> Describe where you would define what exact version of mysql docker should use?

* I would do this in the .yml file where i declare what image I'm using. So right now there's no defined version of mysql, if i want to use a specific one like version 8, i would add that to the image section of the db service, and instead write the following: ``image: mysql:8``.

> What commands will give you the ip addresses of the containers in the described network.

* To see the ip addresses of the containers in the network i would use the following command:
  * `docker network inspect network1`

## Task 3

> Write in the hand-in the chain of images that nextcloud is dependent on

* The traversal is as follows from top to down:
  * `nextcloud:19`
  * `php:7.4-apache-buster`
  * `debian:buster-slim`
  * `scratch`
