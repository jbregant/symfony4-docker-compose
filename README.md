"# symfony4-docker-compose" 

php7-nodejs8-nginx

put your Symfony application into symfony folder and do not forget to add symfony.localhost in your /etc/hosts file.

Make sure you adjust database_host in parameters.yml to the database container alias "db"

Then, run:

$ docker-compose up
You are done, you can visit your Symfony application on the following URL: http://symfony.localhost (and access Kibana on http://symfony.localhost:81)

Note : you can rebuild all Docker images by running:

$ docker-compose build

Read logs
You can access Nginx and Symfony application logs in the following directories on your host machine:

logs/nginx
logs/symfony
Use Kibana!
You can also use Kibana to visualize Nginx & Symfony logs by visiting http://symfony.localhost:81.

Use xdebug!
To use xdebug change the line "docker-host.localhost:127.0.0.1" in docker-compose.yml and replace 127.0.0.1 with your machine ip addres. If your IDE default port is not set to 5902 you should do that, too.
