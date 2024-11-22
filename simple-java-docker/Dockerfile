#Repo Link: https://github.com/LondheShubham153/simple-java-docker

# Use the 'openjdk:17-java-alpine' base image as the starting point
FROM openjdk:17-alpine

# Set the working directory inside the container to /app
WORKDIR /app

# Copy the Main.java file from the host machine to the /app directory inside the container
COPY src/Main.java /app/Main.java

# Compile the Main.java file using the javac compiler inside the container
RUN javac Main.java

# Specify the default command to run when the container starts - execute the compiled Main class using the java command
CMD ["java", "Main"]