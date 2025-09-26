FROM python:3.9-slim
WORKDIR /app

RUN apt-get update && apt-get install -y \
    netcat-openbsd libpq-dev gcc python3-dev \
 && rm -rf /var/lib/apt/lists/*

COPY requirements.txt .
RUN pip install --no-cache-dir -r requirements.txt

COPY . /app/
RUN sed -i 's/\r$//' /app/entrypoint.sh && chmod +x /app/entrypoint.sh

ENV PYTHONDONTWRITEBYTECODE=1 PYTHONUNBUFFERED=1
ENTRYPOINT ["/app/entrypoint.sh"]
