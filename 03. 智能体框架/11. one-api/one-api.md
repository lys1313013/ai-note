# one-api


部署
```bash
docker run --name one-api -d --restart always -p 3000:3000 -e TZ=Asia/Shanghai -v /home/ubuntu/data/one-api:/data justsong/one-api
```



mac:
docker run --platform linux/amd64 --name one-api -d --restart always -p 3001:3000 -e TZ=Asia/Shanghai  justsong/one-api

docker run --platform linux/amd64 --name one-api -d --restart always -p 3001:3000 -e TZ=Asia/Shanghai -e LOG_LEVEL=debug justsong/one-api


默认账号密码
root
123456