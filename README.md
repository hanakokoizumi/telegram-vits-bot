# Vits Bot for Telegram

@hnkvitsbot 的源代码。

## 要求

1. 足够的算力
2. 能够公网访问的服务器。由于 Telegram Inline Bot 不支持直接上传音频文件，需要您使用任意的静态 HTTP 服务器（如 Nginx 等）设置一个 URL 解析到本目录的 temp 文件夹，以供 Telegram 服务器下载生成的音频文件。
3. 构建过程需要能够访问 Google Drive 的网络环境。构建脚本会从 Google Drive 下载各个人物的模型权重。
4. 既然是 Telegram Bot，显然需要一个能访问 `api.telegram.org` 的服务器。

## Docker 部署

1. 拉取项目文件

```shell
git clone https://github.com/hanakokoizumi/telegram-vits-bot --recursive
cd telegram-vits-bot
mv env.example .env
```

2. 修改 .env 中的环境变量，包括 Bot Token、HTTP 前缀等
3. 构建镜像并启动容器

```shell
docker compose up -d --build
```

## 致谢

本项目直接调用了 [Kanade-nya/PJSK-Vits-Uni](https://github.com/Kanade-nya/PJSK-Vits-Uni/) 进行语音合成。感谢 [Kira★](https://github.com/Kanade-nya) 对本项目的贡献。

感谢原始 [VITS](https://github.com/Kanade-nya) 项目。

感谢各人物模型权重的提供者。