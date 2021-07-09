# docker-cakephp2.0-nvhieu

1. Build docker file -> docker-compose build 
2. Run image -> docker-compose up 
3. Import SQL to docker mysql image : 
          First find the docker container:

          docker ps
          This will list out a bunch of container ids. Find the one relating to mysql.

          CONTAINER ID        IMAGE                   ...
          [YourContainerId]        mysql:5.7.29            ...CONTAINER ID        IMAGE                   
          Now copy the sql file using docker cp into our container

          docker cp your.sql [YourContainerId]:/your.sql
          Once complete, we need to login to our container and import to our mysql database.

          docker exec -it [YourContainerId] bin/bash
          Once we're logged in, we can now login to mysql.

          mysql -u root -p 
          To see your databases, run show databases;

          Select the database you're going to be importing to:

          use your-database-name
          Now import by running:

          source your.sql
