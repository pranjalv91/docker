#------------------------------ Stage 1 ------------------------------------
# Use Python 3.9 as the builder image
FROM python:3.9 as builder

# Set the working directory to '/app' in the builder stage
WORKDIR /app

# Install build dependencies required packages for Python
RUN apt-get update && \
    apt-get install -y --no-install-recommends gcc default-libmysqlclient-dev pkg-config && \
    rm -rf /var/lib/apt/lists/*

# Copy the 'requirements.txt' file from the local directory to the '/app' directory in the builder stage
COPY requirements.txt .

# Install Python dependencies defined in 'requirements.txt' without caching
RUN pip install --no-cache-dir -r requirements.txt

#------------------------------ Stage 2 ------------------------------------
# Create a new stage with Python 3.9-slim as the base image
FROM python:3.9-slim

# Set the working directory to '/app' in the final image stage
WORKDIR /app

# Install build dependencies required the final image stage
RUN apt-get update && \
    apt-get install -y --no-install-recommends libmariadb3 && \
    rm -rf /var/lib/apt/lists/*

# Copy Python dependencies from the previous builder stage to the final image
COPY --from=builder /usr/local/lib/python3.9/site-packages /usr/local/lib/python3.9/site-packages

# Copy the local directory contents to the '/app' directory in the final image
COPY . .

# Specify the default command to run when the container starts
CMD ["python", "app.py"]