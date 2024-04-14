# frp

手动创建目录, 将四个toml配置文件拷贝到目录中, 准备挂载
```bash
mkdir /usr/local/src/frp
```

## Usage

```bash
docker pull luode0320/frp-server:latest
docker pull luode0320/frp-client:latest
```

start frps

```bash
docker run -d \
    --restart always \
    --network host \
    -v "/usr/local/src/frp:/etc/frp" \
    --name frp-server \
    luode0320/frp-server:latest
```

start frpc

```bash
docker run -d \
    --restart always \
    --network host \
    -v "/usr/local/src/frp:/etc/frp" \
    --name frp-client \
    luode0320/frp-client:latest
```
