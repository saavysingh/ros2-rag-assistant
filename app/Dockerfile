# Use an official Python runtime as a parent image
FROM python:3.9-slim

# Install system dependencies
RUN apt-get update && apt-get install -y \
    build-essential \
    && rm -rf /var/lib/apt/lists/*

# Set the working directory in the container
WORKDIR /app

# Copy requirements file into the container
COPY requirements.txt .

# Install Python dependencies
RUN pip install --no-cache-dir -r requirements.txt

# Copy the current directory contents into the container at /app
COPY . /app

# Expose ports
EXPOSE 8888 8000
EXPOSE 7860
EXPOSE 8237

# Define environment variable
ENV PYTHONUNBUFFERED=1

# Command to run your app
CMD ["bash", "-c", "jupyter notebook --ip=0.0.0.0 --port=8888 --allow-root --no-browser"]
