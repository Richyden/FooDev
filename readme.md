# DEV env: docker-compose

This is a generated README by the [BeCode CLI tool](https://github.com/becodeorg/cli).

If you are completely new to Docker we recommend you to read the [Docker Survival Guide](https://github.com/becodeorg/cli/tree/develop/docs/docker-survival-guide).

## Install `docker` & `docker-compose`

### For macOS

Follow the procedure on [this page](https://docs.docker.com/docker-for-mac/install/)

### For Windows

#### Pro, Enterprise or Education versions

Follow the procedure on [this page](https://docs.docker.com/docker-for-windows/install/)

#### Home version

To use docker on Windows Home, you need to use the [Docker Toolbox](https://docs.docker.com/toolbox/overview/), which use VirtualBox to run docker on your machine.  

##### ⚠️ Important notes for Windows Home version

The Docker Toolbox and the VirtualBox env will change two important things when you use docker : 

1. The host to access the containers isn't `localhost`, but the IP `192.168.99.100` (by default)
2. Due to the nature of VirtualBox, the *volumes* binding between your local system and the containers are kinda limited. Please ensure that **your working folder** is inside the `C:/Users` path.

### For Linux

1. Follow the procedure on [this page](https://docs.docker.com/install/linux/docker-ce/ubuntu/)
1. Run the following command to fix a possible right issue : `sudo usermod -a -G docker $USER`
1. Follow the procedure on [the page](https://docs.docker.com/compose/install/#install-compose)
1. Restart your computer

To test your installation, run the command `docker run hello-world`.

## Run `docker`

When starting your env for the first time, run the following command in yhour repo:

	docker-compose build
	
> **NOTE:** thus you don't need to run this command each time, it may be useful to *re*build your services when you change the configuration of your services.

Then, simply run the following command to get started:

    docker-compose up

The details for all your services is detailed bellow.

## Your services

### App: Wordpress

#### What is Wordpress?

WordPress is a free and open source blogging tool and a content management system (CMS) based on PHP and MySQL, which runs on a web hosting service. Features include a plugin architecture and a template system. WordPress is used by more than 22.0% of the top 10 million websites as of August 2013. WordPress is the most popular blogging system in use on the Web, at more than 60 million websites. The most popular languages used are English, Spanish and Bahasa Indonesia.

* **Website:** [wordpress.org](https://wordpress.org)
* **Documentation:** [codex.wordpress.org](https://codex.wordpress.org)

#### Container

* **Image used:** [library/wordpress](https://hub.docker.com/_/wordpress/)

##### Usage

Access it with your browser at address [localhost](http://localhost).


* * *

### Database: MySQL

#### What is MySQL?

MySQL is the world's most popular open source database. With its proven performance, reliability and ease-of-use, MySQL has become the leading database choice for web-based applications, covering the entire range from personal projects and websites, via e-commerce and information services, all the way to high profile web properties including Facebook, Twitter, YouTube, Yahoo! and many more.

* **Website:** [mysql.com](https://www.mysql.com)
* **Documentation:** [dev.mysql.com/doc/](https://dev.mysql.com/doc/)

#### Container

* **Image used:** [library/mysql:5](https://hub.docker.com/_/mysql/)

##### Usage

**IMPORTANT:** the first startup of this container is long : the db server needs to be initialized.

**NOTE:** the container don't create a database at startup - create it within your code (or with phpMyAdmin)

###### Access from another container

You can access the database **from another container** with the following informations:

* **host:** `mysql`
* **port:** `3306`
* **user:** `root`
* **pass:** `root`

###### Access from your host

You can access the database  **from your host** with the following informations:

* **host:** `localhost`
* **port:** `3306`
* **user:** `root`
* **pass:** `root`


* * *

### Tools: phpMyAdmin

#### What is phpMyAdmin?

A web interface for MySQL and MariaDB.

* **Website:** [phpmyadmin.net](https://www.phpmyadmin.net/)
* **Documentation:** [phpmyadmin.net/docs](https://www.phpmyadmin.net/docs/)

#### Container

* **Image used:** [phpmyadmin/phpmyadmin](https://hub.docker.com/r/phpmyadmin/phpmyadmin/)

##### Usage

The container is already configured to use the MySQL/MariaDB credentials.  
Access **phpMyAdmin** with your browser at address [localhost:8001](http://localhost:8001).