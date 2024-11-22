
# Getting Started with two-tier-flask-app Project

## Github link to the project

<https://github.com/LondheShubham153/Springboot-BankApp>

## Clone the Project

- Navigate to the cloned project directory

```bash
   cd Springboot-BankApp
```

- Clone the 'Springboot-BankApp' project using the following command

```bash
   git clone https://github.com/LondheShubham153/Springboot-BankApp.git
```

## Build Docker Image

- Verify the presence of the Dockerfile. If it's present in the root directory, there is no need to copy it.

- Build the Docker image named 'bankapp-mini' using the following command

```bash
   docker build -t bankapp-mini .
```

- Login to docker hub and enter the personal access token when prompted

```bash
   docker login -u pranjalv91
   <Paste personal access token id to the cmd>
```

- Rename image to include appropriate tag name

```bash
   docker image tag bankapp-mini pranjalv91/springboot-bankapp:latest
```

- Push image to docker repository

```bash
   docker push pranjalv91/springboot-bankapp:latest
```

- Delete all images from the machine to free up space

```bash
   docker rmi -f $(docker images -aq)
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

- Create an inbound rule in security group(AWS EC2 machine) or Windows Firewall Manager for windows machine to allow inbound connections to port 8080

- Access the application on web browser using the below address format

```bash
   http://<public-ip>:8080
```

## Additional Information

For more information and usage guidelines, refer to the project's documentation and codebase.
