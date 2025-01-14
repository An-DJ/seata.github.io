---
title: 版本升级指南
keywords: [Seata]
description: Seata upgrade.
---

# 版本升级指南

********

<h3>1. 升级到 seata 1.1.0 有哪些兼容性事项是需要注意的？</h3>
<details>
  <summary><mark>注意事项</mark></summary>

1. 需要注意配置项的兼容性，1.1.0 版本对于配置项的风格进行了统一。
若程序中依赖的是 seata-all，对应于 *.conf 文件，conf文件中配置项的命名风格统一为 点号+驼峰式组合，[1.1.0 配置项说明](https://seata.io/zh-cn/docs/user/configurations.html)， [1.1.0 配置参考](https://github.com/seata/seata/tree/1.1.0/script/client/conf); 
若程序中依赖的是seata-spring-boot-starter，对应于 *.properties 或 *.yml。propertie、 yml文件命名风格统一为 点号+中划线组合 
[1.1.0 配置参考](https://github.com/seata/seata/tree/1.1.0/script/client/spring) 需要特别注意的是1.0.0 版本配置项 seata.service
.vgroup-mapping=default 1.1.0 更改为: seata.service.vgroup-mapping
.my_test_tx_group=default,其中my_test_tx_group代表程序所使用的事务分组； 1.0.0 版本配置项seata.service.grouplist=127.0.0.1:8091， 1.1.0 
更改为：seata.service.grouplist.default=127.0.0.1:8091 其中 default 代表 seata注册服务名。

2. seata-all 默认不开启数据源自动代理。原 seata-all中 conf 文件配置项
client.support.spring.datasource.autoproxy 配置项失效，由注解 @EnableAutoDataSourceProxy 
注解代替，注解参数可选择使用jdk代理或者cglib代理，当使用HikariDataSource 时推荐使用 cglib 代理模式。
seata-spring-boot-starter 默认开启数据源代理，对应数据源自动代理配置项与1.0.0 版本保持不变。

3. 使用spring cloud框架时需要使用[Spring Cloud Alibaba](https://github.com/alibaba/spring-cloud-alibaba)来进行seata 
事务上下文的传递，与Spring Cloud Alibaba 版本集成依赖关系，参考 [版本说明](https://github.com/alibaba/spring-cloud-alibaba/wiki/%E7%89%88%E6%9C%AC%E8%AF%B4%E6%98%8E)     
spring-cloud-alibaba-seata 在 2.2.0.RELEASE 版本前 依赖的是seata-all 若继续使用低版本的 spring-cloud-alibaba-seata 可以使用高版本的 seata-all 取代内置的 seata-all 版本；   
从spring-cloud-alibaba-seata 在 2.2.0.RELEASE 开始后（含）内部开始依赖seata-spring-boot-starter,2.2.0.RELEASE 内部集成 seata-spring-boot-starter 1.0.0 可以升级为 seata-spring-boot-starter 1.1.0，seata-spring-boot-starter 集成了seata-all，seata-spring-boot-starter 包装了对于properties或yml 配置的autoconfig 功能，在spring-cloud-alibaba-seata 2.2.0.RELEASE 前 
autoconfig 功能由其本身支持，在其后去掉 spring-cloud-alibaba-seata 中关于 seata 本身的autoconfig 由seata-spring-boot-starter 支持，因此低版本spring-cloud-alibaba-seata 只能配合 seata-all使用，高版本spring-cloud-alibaba-seata 只能配合seata-spring-boot-starter 使用，以2.2.0.RELEASE为分界点。

4. TC端采用 db 存储模式时 branch_table 中增加 gmt_create，gmt_modified 字段的精度，用于精确确认回滚的顺序，
[各数据库脚本参考](https://github.com/seata/seata/tree/1.1.0/script/server/db)

</details>
