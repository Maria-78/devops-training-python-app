FROM python:3.6-slim

WORKDIR /app

COPY requirements.txt /app

# Install system dependencies for psycopg2 and other build essentials
# Añadimos 'curl' a la lista de paquetes instalados
RUN apt-get update && apt-get install -y \
    gcc \
    libpq-dev \
    curl \
    && rm -rf /var/lib/apt/lists/*

# Install Python dependencies
RUN pip install -r requirements.txt

COPY src /app/src
WORKDIR /app/src
# Exponemos el puerto que Flask usa internamente
EXPOSE 5000
CMD ["python", "app.py"]