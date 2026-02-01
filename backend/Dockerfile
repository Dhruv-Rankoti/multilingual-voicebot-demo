FROM python:3.11-slim

WORKDIR /app

COPY requirements.txt .
RUN pip install --no-cache-dir -r requirements.txt

COPY . .

# App Runner needs to know which port to listen on
EXPOSE 8080

# Using gunicorn for production with Flask
CMD ["gunicorn", "--bind", "0.0.0.0:8080", "voice_server:app"]