FROM public.ecr.aws/docker/library/python:slim

WORKDIR /app

# Install PostgreSQL development libraries required for psycopg2
RUN apt-get update && \
    apt-get install -y libpq-dev && \
    rm -rf /var/lib/apt/lists/*

COPY requirements.txt .
RUN pip install --no-cache-dir -r requirements.txt
COPY . .

EXPOSE 5153

ENV PYTHONUNBUFFERED=1

CMD ["python", "app.py"]