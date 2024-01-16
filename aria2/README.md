

```
docker run -d \
  --name=aria2 \
  -e PUID=501 \
  -e PGID=20 \
  -e TZ=Asia/Shanghai \
  -e SECRET=fangmingdong \
  -e CACHE=512M \
  -e PORT=6800 \
  -e BTPORT=32516 \
  -e WEBUI=true \
  -e WEBUI_PORT=8080 \
  -e UT=true \
  -e RUT=true \
  -e FA=falloc \
  -e QUIET=true \
  -e SMD=true \
  -p 32516:32516 \
  -p 32516:32516/udp \
  -p 6800:6800 \
  -p 8080:8080 \
  -v $PWD/config:/config \
  -v /Volumes/mac/aria2:/downloads \
  --restart unless-stopped \
  superng6/aria2:webui-latest
```