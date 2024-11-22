#Repo Link: https://github.com/deparkes/simple-django-app

# Use the Python 3.9 base image for the Docker container
FROM python:3.9

# Set the working directory inside the container to '/app'
WORKDIR /app

# Copy the local files from the host machine to the '/app' directory in the container
COPY . /app

# Install Python dependencies specified in the 'requirements.txt' file
RUN pip install -r requirements.txt

# Run the Django database migration script to apply any pending migrations
RUN python cool_counters/migrate.py migrate

# Expose port 8000 to make the Django application accessible outside the container
EXPOSE 8000

# Specify the command to run when the container starts:
# Start the Django development server to run the application on '0.0.0.0:8000'
CMD ["python", "cool_counters/migrate.py", "runserver", "0.0.0.0:8000"]