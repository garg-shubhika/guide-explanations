# The base image to use for your container.
FROM python:3.9-slim

# This sets the working directory inside the container to /app.
WORKDIR /app

# This command copies the app.py file from your local machine to the /app directory inside the container 
COPY app.py .

# CMD tells Docker to run python app.py, which will execute the app.py Python script.
CMD ["python", "app.py"]
