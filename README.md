## Prerequisites 
- Docker 
- Docker compose 
- Copy `.env.example` to `.env` and edit the `.env` file.
- Place your application files with a *public/* directory inside the *app/* directory. 
  Your web app will be served from the app/public/ directory. 

## Running 
- **First run:** Run `docker-compose up -d --build`.

  You can follow the logs by running `docker-compose logs -f php`.
- **Subsequent runs:** Run `docker-compose up -d`
- Navigate to *http://localhost:<APP_PORT>* where <APP_PORT> is the PORT value set in the *.env* file.


## Working With The Application 


### Container and Service Administration 
- To log into any container, run: 
  `docker exec -it <APP_NAME>_<SERVICE_NAME> bash` . 
- To view the logs of any service, maybe for troubleshooting purposes, run: 
  `docker-compose logs -f <SERVICE_NAME>`.

Here, 
- *<APP_NAME>* is the name of the containers as specified inside the `.env` file.
- *<SERVICE_NAME>* is the name of the service. The following services are available: 
    - **php**
    - **nginx**
    - **mysql**
    - **rabbitmq**
  
For example, assuming the <APP_NAME> is **sample_app**, 
- to log into the **php** container service, run: `docker exec -it sample_app_php bash`.
- to view the logs of the **nginx** service, run: `docker-compose logs -f nginx`.
