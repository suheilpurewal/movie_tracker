# Base image
FROM python:3.11-slim

# Set working directory
WORKDIR /app

# Copy all files into the container
COPY . .

# Install required packages
RUN pip install -r requirements.txt

# Expose the port Flask will run on
EXPOSE 5001

# Command to run your application
CMD ["python", "app.py"]