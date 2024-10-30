# Base image for Home Assistant add-ons
ARG BUILD_FROM
FROM $BUILD_FROM

# Set environment
ENV LANG C.UTF-8

# Set working directory
WORKDIR /app

# Install system dependencies for building Python packages
RUN apk add --no-cache python3 py3-pip gcc musl-dev libffi-dev openssl-dev \
    && python3 -m ensurepip \
    && pip3 install --upgrade pip

# Copy application files into the container
COPY . .

# Install Python packages from requirements.txt, capturing any potential issues
RUN pip install --no-cache-dir -r requirements.txt || { \
    echo "Error installing Python packages. Showing pip and apk logs for debugging:"; \
    pip3 --version; apk --version; exit 1; \
}

# Copy the startup script and grant execute permissions
COPY run.sh /run.sh
RUN chmod +x /run.sh

# Expose the port Flask will run on
EXPOSE 5001

# Command to run the application
CMD [ "/run.sh" ]