FROM alpine:latest

COPY ./walle-q /usr/bin/walle-q
RUN chmod +x /usr/bin/walle-q

WORKDIR /data

ENTRYPOINT ["/usr/bin/walle-q"]
