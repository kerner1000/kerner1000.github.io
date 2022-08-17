---
title: Feign Exception Invalid HTTP method PATCH
excerpt: "Feign Exception: Invalid HTTP method: PATCH"
description: "Feign Exception: Invalid HTTP method: PATCH."
categories: [Development]
tags: [java, spring-boot, feign]
---

Tell Feign to use Apache's HTTP client:

```java
public class FeignConfiguration {

    @Bean
    Client apacheHttpClient(ApacheHttpClientConfigurationProperties properties) {
        CloseableHttpClient apacheClient = HttpClients.custom()
                .setMaxConnTotal(properties.getMaxConnectionsTotal())
                .setMaxConnPerRoute(properties.getMaxConnectionsPerRoute())
                .build();
        return new ApacheHttpClient(apacheClient);
    }
}
```

```xml
<dependency>
  <groupId>org.springframework.cloud</groupId>
  <artifactId>spring-cloud-starter-openfeign</artifactId>
  <exclusions>
    <exclusion>
      <groupId>io.github.openfeign</groupId>
      <artifactId>feign-core</artifactId>
    </exclusion>
  </exclusions>
</dependency>
<dependency>
  <groupId>io.github.openfeign</groupId>
  <artifactId>feign-core</artifactId>
</dependency>
<dependency>
  <groupId>io.github.openfeign</groupId>
  <artifactId>feign-httpclient</artifactId>
</dependency>
```

```json
apache:
  http:
    client:
      max-connections-per-route: 20
      max-connections-total: 200
```