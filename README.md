# springCloud 的注册中心为Consul,

## 入门步骤

+ 导入相关的依赖
```xml
   <!--consul 客户端-->
        <dependency>
            <groupId>org.springframework.cloud</groupId>
            <artifactId>spring-cloud-starter-consul-discovery</artifactId>
            <version>2.2.1.RELEASE</version>
        </dependency>
```

+ 本地的必须要安装consul软件，并且启动

+ 配置yml文件

```yaml
  server:
  port: 8005

spring:
  cloud:
    consul:
      host: localhost
      port: 8500  # 这是默认地址
      discovery:
        service-name: ${spring.application.name}   # 服务名称
        prefer-ip-address: true    # 是否注册ip

  application:
    name: consul-demo
```
+ 最后访问consul的监控中心，查看服务是否注册成功
    + 地址是: localhost:8500



