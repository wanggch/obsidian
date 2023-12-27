
- [详解SptingBoot参数校验机制，使用校验不再混乱](https://zzzzbw.cn/article/27)
- [SpringBoot整合任务调度框架Quartz及持久化配置](https://www.cnblogs.com/summerday152/p/14193968.html
- [在 Spring Boot 中实现定时备份 MySQL 数据库](https://springdoc.cn/spring-boot-mysql-backup/)
- [Drools | drools动态增加、修改、删除规则](https://www.cnblogs.com/huan1993/p/16319931.html)
- [JasperReports | JasperReports with Spring Boot](https://github.com/blueswen/jasperreports-with-spring-boot/blob/main/README.md)


## toString()

```java
// import org.apache.commons.lang3.builder.ToStringBuilder;

@Override
public String toString() {
	return ToStringBuilder.reflectionToString(this);
}
```

Spring Boot 中如果不显式地使用`@ComponentScan`指明对象扫描的包，那么默认只扫描当前启动类所在的包里的类。

