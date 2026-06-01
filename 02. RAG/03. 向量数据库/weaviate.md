```bash
docker pull semitechnologies/weaviate:latest
```


windows

```bash
docker run -d --name weaviate ^
    --restart=always ^
    -p 38080:8080 ^
    -p 50051:50051 ^
    -e "AUTHENTICATION_APIKEY_ENABLED=true" ^
    -e "AUTHENTICATION_APIKEY_ALLOWED_KEYS=test-secret-key,test2-secret-key" ^
    -e "AUTHENTICATION_APIKEY_USERS=test@2024.com,test2@2024.com" ^
    -e "AUTHORIZATION_ADMINLIST_ENABLED=true" ^
    -e "AUTHORIZATION_ADMINLIST_USERS=test@2024.com" ^
    -e "AUTHORIZATION_ADMINLIST_READONLY_USERS=test2@2024.com" ^
    -e WEAVIATE_HOSTNAME=0.0.0.0 ^
    semitechnologies/weaviate:latest
```
mac
```
docker run -d --name weaviate \
    --restart=always \
    -p 38080:8080 \
    -p 50051:50051 \
    -e "AUTHENTICATION_APIKEY_ENABLED=true" \
    -e "AUTHENTICATION_APIKEY_ALLOWED_KEYS=test-secret-key,test2-secret-key" \
    -e "AUTHENTICATION_APIKEY_USERS=test@2024.com,test2@2024.com" \
    -e "AUTHORIZATION_ADMINLIST_ENABLED=true" \
    -e "AUTHORIZATION_ADMINLIST_USERS=test@2024.com" \
    -e "AUTHORIZATION_ADMINLIST_READONLY_USERS=test2@2024.com" \
    -e WEAVIATE_HOSTNAME=0.0.0.0 \
    semitechnologies/weaviate:1.22.0
```

报错
```
java.lang.IllegalArgumentException: no graphql provider present, this is most likely because no schema is present. Import a schema first!
```




docker 启动


```
docker run -p 38080:8080 -p 50051:50051 cr.weaviate.io/semitechnologies/weaviate:1.30.0
```

api接口文档 [http://localhost:8080/v1/docs](http://localhost:8080/v1/docs)

# 参考资料
https://weaviate.io/developers/weaviate/installation/docker-compose