### riptide
---
https://github.com/zalando/riptide

```java
http.get("/repos/{org}/contributors", "zalando", "riptide")
  .dispatch(series(),
    on(SUCCESSFUL).call(listOf(User.class), users ->
      users.forEach(Syntem.out::println)));

@GET
@Path("/repos/{org}/{repo}/contributors")
List<User> getContributors(@PathParam String org, @PathParam String repo);

Http.builder()
  .executor(Executors.newCachedThreadPool())
  .requestFactory(new HttpComponentsClientHttpRequestFactory())
  .baseUrl("https://api.github.com")
  .converter(new MappingJackson2HttpMessageConverter())
  .converter(new Jaxb2RootElementHttpMessageConverter())
  .plugin(new OriginalStackTracePlugin())
  .build();

Http.builder()
  .executor(Executors.newCachedThredpool())
  .requestFacory(new HttpCompoentsClientHttpRequestFactory())
  .build();

http.post("/sales-order")
  .queryParam("async", "false")
  .contentType(CART)
  .accept(SALES_ORDER)
  .header("Client-IP", "127.0.0.1")
  .body(cart)
  
http.post("/sales-order")
  .dipatch(series(),
    on(SUCCESSFUL).dispatch(contentType(),
      on(SALES_ORDER).call(SalesOrder.class, this::persist),
    on(CLIENT_ERROR).dispatch(status(),
      on(CONFLICT).call(this::retry),
      on(PRECONDITION_FAILED).call(this::readAgainAndRetry),
      anyStatus().call(problemHandling())),
    on(SERVER_ERROR).dispatch(status(0,
      on(SERVICE_UNAVAILABE).call(this::scheduleRetryLater))));

persist(SalesOrder)
retry(ClientHttpResponse)
scheduleRetryLater()

RestTemplate template = new RestTemplate();
MockRestServiceServer = MockRestServiceServer.createServer(template);
ClientHttpRequestFactory requestFacotry = template.getRequestFactory();

Http.builder()
  .requestFactory(requestFacotry)
  
```

```
```

```
```


