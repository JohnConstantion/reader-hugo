---
title: "如何添加项目中的SpringDoc功能"
date: 2024-01-23T16:59:24+06:00
# post thumb
images:
  - "images/blog/code.jpg"
#author
author: "Crucio"
# description
description: "This is meta description"
# Taxonomies
categories: [ "学习","知识" ]
tags: [ "Java","Code","学习" ]
type: "regular" # available type (epic, trending, popular, or regular)
draft: false
---

SpringBoot 3.x版本如何集成swagger3 

## 在pom.xml中添加jar
```xml
 <!-- https://mvnrepository.com/artifact/org.springdoc/springdoc-openapi-ui -->
<dependency>
  <groupId>org.springdoc</groupId>
  <artifactId>springdoc-openapi-starter-webmvc-ui</artifactId>
  <version>2.3.0</version>
</dependency>
```

## 在项目中添加配置文件
```java
import io.swagger.v3.oas.models.OpenAPI;
import io.swagger.v3.oas.models.info.Info;
import org.springframework.context.annotation.Bean;
import org.springframework.context.annotation.Configuration;

@Configuration
public class SpringDocConfig {
    @Bean
    public OpenAPI openApi() {
        return new OpenAPI().info(new Info().title("TRAIN API").description("TRAIN 接口文档").version("1.0.0"));
    }
}
```

## 启动项目可以访问地址
[访问地址](http://localhost:8080/swagger-ui/index.html)
> 地址http://localhost:8080/swagger-ui/index.html 需要根据自己的项目的配置来修改对应的端口号和前缀地址（如有添加context-path时）

## 添加相应的注解
| 注解            |      描述       |    示例 |
|---------------|:-------------:|------:|
| @Tag          | 标记在接口类上，用来设置 Controller 的名称和描述 | @Tag(name = "测试接口", description = "定义测试接口") |
| @Parameter/@Parameters    |   用来设置请求参数的描述    |   @Parameter(name = "username", description = "参数username", example = "username") |
| @Operation |   对接口方法的描述，可以设置接口的名称    |    @Operation(summary = "get测试接口", description = "返回id") |
| @ApiResponse/@ApiResponses |   用来配置响应    |    @ApiResponse(responseCode = "403", description = "无权限") |
| @Schema |   标记在模型（model）类上或类的属性上，进行标注解释。    |    @Schema |

### 官方链接Link
[spring doc-openapi](https://springdoc.org/#springdoc-openapi-core-properties)
