FROM public.ecr.aws/docker/library/python:slim

WORKDIR /app

RUN yum -y update && \
    yum install -y postgresql-devel && \
    yum clean all

COPY requirements.txt .
RUN pip install --no-cache-dir -r requirements.txt
COPY . .

EXPOSE 5153

ENV PYTHONUNBUFFERED=1

CMD ["python", "app.py"]