FROM python:3.9

WORKDIR /app

COPY requirements.txt /app/

RUN pip install -r requirements.txt

COPY .env /app

COPY . /app

ENTRYPOINT ["/app/entrypoint.sh"]

