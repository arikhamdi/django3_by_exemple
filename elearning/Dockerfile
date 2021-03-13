FROM python:3.8-alpine

ENV PYTHONUNBUFFERED 1

RUN mkdir /app
WORKDIR /app

COPY requirements.txt .
RUN apk add --update --no-cache jpeg-dev
RUN apk add --update --no-cache --virtual .tmp-build-deps \
    gcc libc-dev linux-headers musl-dev zlib zlib-dev
RUN pip install -r requirements.txt
RUN apk del .tmp-build-deps

COPY . /app/