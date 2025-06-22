FROM python:3.9-slim

# Prevents Python from writing pyc files to disk
ENV PYTHONDONTWRITEBYTECODE=1
# Ensures output is logged directly
ENV PYTHONUNBUFFERED=1

# Set working directory
WORKDIR /app

# Install dependencies early for caching
COPY host/requirements.txt .

# Install system dependencies
RUN apt-get update && apt-get install -y --no-install-recommends \
    build-essential gcc && \
    pip install --upgrade pip && \
    pip install -r requirements.txt && \
    apt-get remove -y build-essential gcc && \
    apt-get autoremove -y && \
    rm -rf /var/lib/apt/lists/*

# Copy project files
COPY . .

# Set Flask environment variables
ENV FLASK_APP=hello_world.py
ENV FLASK_RUN_HOST=0.0.0.0
ENV FLASK_RUN_PORT=5000

# Expose Flask port
EXPOSE 5000

# Default command
CMD ["flask", "run"]
