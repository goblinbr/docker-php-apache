# Run php with apache at docker

## Create docker image
git clone https://github.com/goblinbr/docker-php-apache.git  
cd docker-php-apache  
docker build -t php .  

## Run the docker image 
docker run --name php -p 8010:8010 -v /your_site_dir/:/var/www/php -d php  

## Stop the docker image
docker stop php  

## By default, it will run at port 8010, to change to port 80:  
1) **Dockerfile**, change **EXPOSE 8010** to **EXPOSE 80**  
2) **apache-config.conf**, change **VirtualHost *:8010** to **VirtualHost *:80**  
3) **ports.conf**, change **Listen 8010** to **Listen 80**  
5) re-create docker image  
4) at the run cmd, change **-p 8010:8010** to **-p 80:80**  
