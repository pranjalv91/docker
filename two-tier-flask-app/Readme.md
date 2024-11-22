
# Getting Started with two-tier-flask-app Project

## Github link to the project

<https://github.com/LondheShubham153/two-tier-flask-app>

## Clone the Project

- Navigate to the cloned project directory

```bash
   cd two-tier-flask-app
```

- Clone the 'two-tier-flask-app' project using the following command

```bash
   git clone https://github.com/LondheShubham153/two-tier-flask-app.git
```

## Build Docker Image

- Verify the presence of the Dockerfile. If it's present in the root directory, there is no need to copy it.

- Build the Docker image named 'flaskapp' using the following command

```bash
   docker build -t flaskapp .
```

## Spin up Docker container using docker compose

- If docker-compose is not installed on your machine use the below command to install the same

```bash
   sudo apt-get install docker-compose-v2
```

- Start all the containers in detached mode using docker-compose

```bash
   docker-compose up -d
```

- Check whether all containers are up and running using below command

```bash
   docker ps -a
```

## Starting the application

- Create an inbound rule in security group(AWS EC2 machine) or Windows Firewall Manager for windows machine to allow inbound connections to port 5000

- Access the application on web browser using the below address format

```bash
   http://<public-ip>:5000
```

## Additional Information

For more information and usage guidelines, refer to the project's documentation and codebase.
