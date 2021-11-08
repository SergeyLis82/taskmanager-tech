FROM python:3.9.7-slim

WORKDIR /usr/src/app

# set environment variables
ENV PYTHONDONTWRITEBYTECODE 1
ENV PYTHONUNBUFFERED 1

RUN apt -y update && apt -y install python3-dev default-libmysqlclient-dev build-essential

COPY ./requirements.txt .
RUN pip install --upgrade pip && \
pip install --requirement requirements.txt

COPY ./entrypoint.sh .
RUN chmod +x entrypoint.sh
ENTRYPOINT [ "/usr/src/app/entrypoint.sh" ]
