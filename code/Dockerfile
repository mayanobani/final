FROM python:3.11-slim

# Python settings
ENV PYTHONDONTWRITEBYTECODE=1
ENV PYTHONUNBUFFERED=1

# Application directory
WORKDIR /app

# Install Python dependencies
COPY requirements.txt .

RUN pip install --no-cache-dir -r requirements.txt \
    && pip install --no-cache-dir gunicorn

# Copy the entire application
COPY . .

# Application port
EXPOSE 5000

# Start Flask with Gunicorn
CMD ["gunicorn", "--bind", "0.0.0.0:5000", "app:app"]
