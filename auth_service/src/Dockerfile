FROM python:3.10.13-alpine3.17 

WORKDIR /home/app

RUN apk add curl

ENV PYTHONDONTWRITEBYTECODE 1
ENV PYTHONUNBUFFERED 1

COPY requirements.txt requirements.txt

RUN pip install --no-cache-dir --upgrade -r requirements.txt

COPY . .

ARG COMMAND
ENV COMMAND_VAR=${COMMAND}

RUN chmod 777 docker-entrypoint.sh

ENTRYPOINT ./docker-entrypoint.sh $COMMAND_VAR