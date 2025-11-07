FROM python:3.12-slim

# Install system dependencies
RUN apt-get update && apt-get install -y python3-distutils python3-setuptools

# Set working directory
WORKDIR /app

# Copy requirements (if you have them)
COPY requirements.txt .

# Install dependencies
RUN pip install --no-cache-dir -r requirements.txt

# Copy application files
COPY . .

# Run migrations (during build or entrypoint)
RUN python manage.py migrate

# Run app
CMD ["python", "manage.py", "runserver", "0.0.0.0:8000"]
