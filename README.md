# OneBot-Impl-Docker

将 OneBot 实现放入 Docker 中。

## [Walle-K](https://github.com/onebot-walle/walle-k)

Kook 的实现。

直接运行 Walle-K。

```sh
docker run --detach \
  --volume=./walle-k-data:/data \
  --restart=always \
  --name=walle-k \
  ghcr.io/he0119/walle-k
```

## [Walle-Q](https://github.com/onebot-walle/walle-q)

QQ 的实现。

直接运行 Walle-Q。

```sh
docker run --detach \
  --volume=./walle-k-data:/data \
  --restart=always \
  --name=walle-q \
  ghcr.io/he0119/walle-q
```

## [Teydacore](https://github.com/teyda/teydacore)

Telegram 的实现。

直接运行 Teydacore。

```sh
docker run --detach \
  --env TELEGRAM_TOKEN=token \
  --env ONEBOT_WSR_URL=url \
  --env ONEBOT_WSR_ACCESS_TOKEN=access_token \
  --restart=always \
  --name=teydacore \
  ghcr.io/he0119/teydacore
```
