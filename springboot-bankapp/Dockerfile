#------------ Stage 1 ------------------

# Use Maven with OpenJDK 17 as the base image for the builder stage
FROM maven:3.8.3-openjdk-17 as builder

# Add labels to the image to filter out if we have multiple application running
LABEL app=bankapp

# Set the working directory to /app in the container
WORKDIR /app

# Copy the source code to the /app directory in the builder stage
COPY . /app

# Build the application using Maven, skipping tests
RUN mvn clean install -DSkipTests=true

#------------ Stage 2 ------------------

# Use Maven with a slim image as the base image for the final stage
FROM openjdk:17-alpine

# Set the working directory to /app in the container
WORKDIR /app

# Copy the built JAR file from the builder stage to the /app/target directory in the final stage
COPY --from=builder /app/target/*.jar /app/target/bankapp.jar

# Expose port 8080 to allow external connections
EXPOSE 8080

# Define the entrypoint command to run the Java application with the JAR file
ENTRYPOINT ["java", "-jar", "bankapp.jar"]
