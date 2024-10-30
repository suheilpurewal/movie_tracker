# Base image for Home Assistant add-ons
ARG BUILD_FROM
FROM $BUILD_FROM

# Set environment
ENV LANG C.UTF-8

# Set working directory
WORKDIR /app

# Copy all files into the container
COPY . .

# Install required packages
RUN pip install -r requirements.txt

# Copy the startup script and grant execute permissions
COPY run.sh /run.sh
RUN chmod +x /run.sh

# Expose the port Flask will run on
EXPOSE 5001

# Command to run the application
CMD [ "/run.sh" ]
