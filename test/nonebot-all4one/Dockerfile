# syntax=docker/dockerfile:1

FROM python:3.10 as requirements_stage

WORKDIR /tmp

RUN python -m pip install --user pipx

COPY ./pyproject.toml /tmp/

RUN python -m pipx run --no-cache poetry export -f requirements.txt --output requirements.txt --without-hashes

RUN python -m pipx run --no-cache nb-cli generate -f bot.py


FROM python:3.10-slim

WORKDIR /app

ENV TZ Asia/Shanghai
ENV PYTHONPATH=/app

RUN apt-get update \
    && apt-get install -y --no-install-recommends git \
    && apt-get purge -y --auto-remove \
    && rm -rf /var/lib/apt/lists/*

COPY --from=requirements_stage /tmp/requirements.txt /tmp/bot.py /app/

RUN pip install --no-cache-dir -r requirements.txt

COPY . /app/

CMD ["python", "bot.py"]
