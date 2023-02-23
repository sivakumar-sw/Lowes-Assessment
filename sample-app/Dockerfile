# Use a smaller and more secure base image
FROM python:3.9-slim-buster

# Set the working directory to /app
WORKDIR /app

# Copy the requirements file and install dependencies
COPY requirements.txt .
RUN pip install --no-cache-dir -r requirements.txt

# Copy the rest of the application code
COPY . .

# Set environment variables for the Flask app
ENV FLASK_APP=app.py
ENV FLASK_DEBUG=production

# Use gunicorn as the production server
CMD ["gunicorn", "-b", "0.0.0.0:5000", "app:app"]

