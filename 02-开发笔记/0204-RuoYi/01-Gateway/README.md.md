
## 包概览

```
com.ruoyi.gateway
|- config            // 网关配置
|- filter            // 过滤器
|- handler           // 处理器
|- service           // Service
```

## config

- <span style="color:red">Swagger文档聚合Provider（不应该放在config包里吧）</span>
- 路由配置
- ~~验证码文本生成器~~
- 网关限流配置
- 验证码配置
- properties包
	- XSS跨站脚本
	- 白名单
	- 验证码
  

## filter

- 跨站脚本过滤器
- 验证码过滤器
- 黑名单过滤器
- 鉴权过滤器
- 处理流不能重复读取问题

### 跨站脚本过滤器

实现接口

- `org.springframework.cloud.gateway.filter.GlobalFilter`
- `org.springframework.core.Ordered`
### 验证码过滤器

继承`org.springframework.cloud.gateway.filter.factory.AbstractGatewayFilterFactory`类。

### 黑名单过滤器

继承`org.springframework.cloud.gateway.filter.factory.AbstractGatewayFilterFactory`类。

### 鉴权过滤器

实现接口

- `org.springframework.cloud.gateway.filter.GlobalFilter`
- `org.springframework.core.Ordered`

功能

- 请求头中是否有token
- token是否过期
- 根据userKey判断登录是否过期，userKey从token中获取
- 从token获取userId和username，然后判断是否为空
- 向request中添加请求头（userKey、userId、username）

### 处理流不能重复读取问题

继承`org.springframework.cloud.gateway.filter.factory.AbstractGatewayFilterFactory`类。


## handler

- 网关统一异常处理
- 限流异常处理
- Swagger
- 验证码

### 网关统一异常处理

实现`org.springframework.boot.web.reactive.error.ErrorWebExceptionHandler`接口。

### 限流异常处理

实现`org.springframework.web.server.WebExceptionHandler`接口。

### Swagger

> 这是一个Controller。放在这个包下，不合适吧。

### 验证码

实现`org.springframework.web.reactive.function.server.HandlerFunction`接口。

## service

- 验证码

### 验证码

功能清单：

- 生成验证码
- 校验验证码

---

- [x] 处理跨域
- [x] 初步鉴权
- [ ] 记录请求日志、响应日志