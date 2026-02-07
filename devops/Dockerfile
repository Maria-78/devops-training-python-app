FROM python:3.6-slim

WORKDIR /app

COPY requirements.txt /app

# Install system dependencies for psycopg2 and other build essentials
RUN apt-get update && apt-get install -y gcc libpq-dev && rm -rf /var/lib/apt/lists/*

# Install Python dependencies
RUN pip install -r requirements.txt

COPY src /app/src
WORKDIR /app/src

CMD python app.py