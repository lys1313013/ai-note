

resttempalte
```java
@GetMapping("/testRestTemplate")  
public void testRestTemplate() {  
    String url = "http://58.22.61.222:49417/v1/chat-messages";  
  
    HttpHeaders headers = new HttpHeaders();  
    headers.add("Authorization", "Bearer app-E2RQ5bF632nuVFzgswFPnB6m");  
    headers.setContentType(MediaType.APPLICATION_JSON);  
  
    Map<String,Object> map = new HashMap<>();  
    map.put("inputs", new HashMap<>());  
    map.put("query", "30102");  
    map.put("response_mode", "streaming");  
    map.put("conversation_id", "");  
    map.put("user", "一体化系统用户ID");  
  
    HttpEntity requests = new HttpEntity<>(map, headers);  
  
    ResponseEntity<String> responseEntity = restTemplate.exchange(url, HttpMethod.POST, requests,  
            new ParameterizedTypeReference<String>() {  
            } );  
    log.info("结果:{}",responseEntity.getBody());  
}
```

