# Use an official Python runtime as a parent image
FROM ubuntu:latest

# Set the working directory
WORKDIR /app

# Update and install python3, pip3, and other necessary packages
RUN apt-get update && apt-get upgrade -y
RUN apt-get install -y python3 python3-pip

# Remove the EXTERNALLY-MANAGED file if present
RUN rm /usr/lib/python*/EXTERNALLY-MANAGED || true

# Install Flask using pip3
RUN pip3 install flask

# Install Flask-cors using pip3
RUN pip3 install flask-cors

# Copy the current directory contents into the container at /app
COPY ./api.py /app/

# Make port 5252 available to the world outside this container
EXPOSE 5252

# Run the application
CMD ["python3", "api.py"]
