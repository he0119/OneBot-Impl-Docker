# syntax=docker/dockerfile:1

FROM python:3.10-slim

WORKDIR /app

ENV TZ Asia/Shanghai
ENV PYTHONPATH=/app

RUN apt-get update \
    && apt-get install -y --no-install-recommends git \
    && apt-get purge -y --auto-remove \
    && rm -rf /var/lib/apt/lists/*

COPY ./requirements.txt ./bot.py /app/

RUN pip install --no-cache-dir -r requirements.txt

COPY . /app/

CMD ["python", "bot.py"]
