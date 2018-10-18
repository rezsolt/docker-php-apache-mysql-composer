
# Docker Compose for Symfony 4 with PHP, Apache, mySQL and Composer
This git provides a docker infrastructure for Symfony for development.
## Configuration
You can modify PHP version, mySQL version, mySQL credentials and Apache HTTP port in the /.env environment file.
After modification please run 

    $ docker-compose build
## How to install Symphony 4?
First start the docker containers:

    $ docker-compose up -d
Then enter the *php_web* container with the *dev* user to install Symphony 4 with composer: (Symfony not allows to install with root user)

    $ docker exec -u dev -it php_web bash
Change directory to */var/www* where is the mapped *project* folder and please run the standard composer command to install all the necessary codes. Important: always use the word *project* as the directory parameter.

    $ cd /var/www
    $ composer create-project symfony/website-skeleton project
In your code editor you will see the */site* folder contains all the Symfony codes. This folder mapped to the */var/www/project* path.
