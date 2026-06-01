# Spring AI

![image-20241116194812867](Spring AI.assets/image-20241116194812867.png)









下载ollama

https://ollama.com/



ollama run llama3





依赖

```xml
<dependency>
    <groupId>org.springframework.ai</groupId>
    <artifactId>spring-ai-ollama-spring-boot-starter</artifactId>
</dependency>
```





检索增强生成RAG Retrieval Augmented Generation

![image-20241116214059090](Spring AI.assets/image-20241116214059090.png)



AnythingLLM





webui







```
docker run -d -p 3000:8080 --gpus=all -v ollama:/root/.ollama -v open-webui:/app/backend/data --name open-webui --restart always ghcr.io/open-webui/open-webui:ollama
```



```
docker run -d -p 3000:8080 --gpus=all --name open-webui --restart always ghcr.io/open-webui/open-webui:ollama
```







![image-20241116222908612](Spring AI.assets/image-20241116222908612.png)





one API

![image-20241116223201851](Spring AI.assets/image-20241116223201851.png)

![image-20241116223220383](Spring AI.assets/image-20241116223220383.png)





![image-20241116223613408](Spring AI.assets/image-20241116223613408.png)
