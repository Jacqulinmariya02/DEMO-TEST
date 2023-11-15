# Use an official Python runtime as a parent image
FROM python:3.8-slim

# Set the working directory to /app
WORKDIR /app

# Install Tkinter dependencies and Xvfb
RUN apt-get update && apt-get install -y \
    python3-tk \
    xvfb \
    && rm -rf /var/lib/apt/lists/*

# Copy the current directory contents into the container at /app
COPY . /app

# Install any needed packages specified in requirements.txt
RUN pip install --trusted-host pypi.python.org tk

# Set environment variable for virtual display
ENV DISPLAY=:99

# Start Xvfb and run app.py when the container launches
CMD Xvfb :99 -screen 0 1024x768x16 & python app.py
