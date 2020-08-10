# OrangeHRM test application

OrangeHRM is an open-source PHP-based Human Resource Management application containerized by Bitname.
It's suitable for REST and UI testing.

OrangeHRM [Live Demo](https://opensource-demo.orangehrmlive.com)   
OrangeHRM [REST wiki](https://github.com/orangehrm/orangehrm/wiki/REST-API)  
OrangeHRM [REST API doc](https://api.orangehrm.com)

### Installation
Download and install [Docker](https://www.docker.com) for your OS. In terminal navigate to directory with *orangehrm.yml* and execute
`docker-compose -f orangehrm.yml up` and wait for images to be downloaded, containers started and application with database installed.
Access application through http://localhost:8080. Credentials for default OrangeHRM user - Admin/Bitnami.12345. 

As a database MySQL is used. It's appropriate to use any database client to access DB data. DB address - localhost:3306.
Check *orangehrm.yml* for connection credentials.  

Docker Compose cheat sheet:
* `docker-compose -f orangehrm.yml up` - initialize containers  
* `docker-compose -f orangehrm.yml down` - stop and remove containers  
* `docker-compose -f orangehrm.yml start` - start previously stopped containers  
* `docker-compose -f orangehrm.yml stop` - stop previously initialized or started containers  

After installation *volumes* directory will be created. This is a storage for specific data from within containers which remains persistent during container lifecycle.  
In case there is a need to perform data cleanup - delete this folder and reinitialize containers.  

Pay attention at API doc User Guide - it describes hot to authenticate REST calls to services. 

There is one uncommon thing - to use REST endpoints application link (http://localhost:8080/symfony/web/index.php) should be concatenated with endpoint, so it should
look like http://localhost:8080/symfony/web/index.php/api/v1/users. There is an advice to use Postman Environment feature and assign this to any short variable during testing.  

Happy testing