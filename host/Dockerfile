FROM python:3.9-slim

WORKDIR /app

COPY host/requirements.txt .
RUN pip install -r requirements.txt

COPY . .

# Add environment variable to define Flask entry point
ENV FLASK_APP=app.py

# Expose port (optional, but good practice)
EXPOSE 5000

# Run Flask app
CMD ["flask", "run", "--host=0.0.0.0", "--port=5000"]
