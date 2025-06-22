# Use official Python image
FROM python:3.9-slim

# Set working directory
WORKDIR /app

# Copy requirements and install
COPY host/requirements.txt .
RUN pip install --no-cache-dir -r requirements.txt

# Copy app code
COPY . .

# Set environment variable for Flask
ENV FLASK_APP=hello_world.py

# Expose the Flask port
EXPOSE 5000

# Run the app
CMD ["flask", "run", "--host=0.0.0.0", "--port=5000"]
