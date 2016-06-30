# Run php with apache at docker

## Create docker image
git clone https://github.com/goblinbr/docker-php-apache.git  
cd docker-php-apache  
docker build -t php .  

## Run the docker image 
docker run --name php -p 8010:8010 --rm -v /your_site_dir/:/var/www/php php &  

## Stop the docker image
docker stop php  

## By default, it will run at port 8010, to change to port 80:  
1) at Dockerfile, change "EXPOSE 8010" to "EXPOSE 80"  
2) at apache-config.conf, change "<VirtualHost *:8010>" to "<VirtualHost *:80>"  
3) at ports.conf, change "Listen 8010" to "Listen 80"  
4) at the run cmd, change "-p 8010:8010" to "-p 80:80"
5) re-create docker image
