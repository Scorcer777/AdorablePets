FROM python:3.9

RUN apt update && apt upgrade -y && apt install  -y libpq-dev gcc netcat-traditional

WORKDIR /app

COPY requirements.txt .

RUN pip install -U pip && pip install -r requirements.txt --no-cache-dir

COPY . .

# CMD ["gunicorn", "--bind", "0.0.0.0:9000", "kittygram_backend.wsgi"]
RUN chmod +x starter.sh
ENTRYPOINT ["/app/starter.sh"]