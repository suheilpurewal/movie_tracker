# Use a Python base image directly for ease of dependency management
FROM python:3.11-slim

# Set environment variables
ENV LANG C.UTF-8

# Set working directory
WORKDIR /app

# Copy all application files into the container
COPY . .

# Install required Python packages
RUN pip install --no-cache-dir -r requirements.txt

# Copy the startup script and ensure it has execute permissions
COPY run.sh /run.sh
RUN chmod +x /run.sh

# Expose the application port
EXPOSE 5001

# Run the application
CMD [ "/run.sh" ]