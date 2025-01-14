---
title: How to use Seata to ensure consistency between Dubbo Microservices
keywords: [Dubbo,Seata,Consistency]
description: This article will introduce you how to use Seata to ensure consistency between Dubbo Microservices.
author: slievrly
date: 2019-03-07
---
# How to use Seata to ensure consistency between Dubbo Microservices
## Use case

A business logic for user purchasing commodities. The whole business logic is powered by 3 microservices:

- Storage service: deduct storage count on given commodity.
- Order service: create order according to purchase request.
- Account service: debit the balance of user's account.

### Architecture

![Architecture](/img/blog/seata/seata-1.png) 


### StorageService

```java
public interface StorageService {

    /**
     * deduct storage count
     */
    void deduct(String commodityCode, int count);
}
```

### OrderService

```java
public interface OrderService {

    /**
     * create order
     */
    Order create(String userId, String commodityCode, int orderCount);
}
```

### AccountService

```java
public interface AccountService {

    /**
     * debit balance of user's account
     */
    void debit(String userId, int money);
}
```

### Main business logic

```java
public class BusinessServiceImpl implements BusinessService {

    private StorageService storageService;

    private OrderService orderService;

    /**
     * purchase
     */
    public void purchase(String userId, String commodityCode, int orderCount) {

        storageService.deduct(commodityCode, orderCount);

        orderService.create(userId, commodityCode, orderCount);
    }
}
```

```java
public class StorageServiceImpl implements StorageService {

  private StorageDAO storageDAO;
  
    @Override
    public void deduct(String commodityCode, int count) {
        Storage storage = new Storage();
        storage.setCount(count);
        storage.setCommodityCode(commodityCode);
        storageDAO.update(storage);
    }
}
```

```java
public class OrderServiceImpl implements OrderService {

    private OrderDAO orderDAO;

    private AccountService accountService;

    public Order create(String userId, String commodityCode, int orderCount) {

        int orderMoney = calculate(commodityCode, orderCount);

        accountService.debit(userId, orderMoney);

        Order order = new Order();
        order.userId = userId;
        order.commodityCode = commodityCode;
        order.count = orderCount;
        order.money = orderMoney;

        return orderDAO.insert(order);
    }
}
```

## Distributed Transaction Solution with Seata

![undefined](/img/blog/seata/seata-2.png) 

We just need an annotation `@GlobalTransactional` on business method: 

```java

    @GlobalTransactional
    public void purchase(String userId, String commodityCode, int orderCount) {
        ......
    }
```

## Example powered by Dubbo + Seata

### Step 1: Setup database

- Requirement: MySQL with InnoDB engine.

**Note:** In fact, there should be 3 database for the 3 services in the example use case. However, we can just create one database and configure 3 data sources for simple. 

Modify Spring XML with the database URL/username/password you just created.

dubbo-account-service.xml
dubbo-order-service.xml
dubbo-storage-service.xml

```xml
    <property name="url" value="jdbc:mysql://x.x.x.x:3306/xxx" />
    <property name="username" value="xxx" />
    <property name="password" value="xxx" />
```
### Step 2: Create UNDO_LOG table for Seata

`UNDO_LOG` table is required by Seata AT mode.

```sql
CREATE TABLE `undo_log` (
  `id` bigint(20) NOT NULL AUTO_INCREMENT,
  `branch_id` bigint(20) NOT NULL,
  `xid` varchar(100) NOT NULL,
  `rollback_info` longblob NOT NULL,
  `log_status` int(11) NOT NULL,
  `log_created` datetime NOT NULL,
  `log_modified` datetime NOT NULL,
  `ext` varchar(100) DEFAULT NULL,
  PRIMARY KEY (`id`),
  KEY `idx_unionkey` (`xid`,`branch_id`)
) ENGINE=InnoDB AUTO_INCREMENT=159 DEFAULT CHARSET=utf8
```

### Step 3: Create tables for example business

```sql

DROP TABLE IF EXISTS `storage_tbl`;
CREATE TABLE `storage_tbl` (
  `id` int(11) NOT NULL AUTO_INCREMENT,
  `commodity_code` varchar(255) DEFAULT NULL,
  `count` int(11) DEFAULT 0,
  PRIMARY KEY (`id`),
  UNIQUE KEY (`commodity_code`)
) ENGINE=InnoDB DEFAULT CHARSET=utf8;


DROP TABLE IF EXISTS `order_tbl`;
CREATE TABLE `order_tbl` (
  `id` int(11) NOT NULL AUTO_INCREMENT,
  `user_id` varchar(255) DEFAULT NULL,
  `commodity_code` varchar(255) DEFAULT NULL,
  `count` int(11) DEFAULT 0,
  `money` int(11) DEFAULT 0,
  PRIMARY KEY (`id`)
) ENGINE=InnoDB DEFAULT CHARSET=utf8;


DROP TABLE IF EXISTS `account_tbl`;
CREATE TABLE `account_tbl` (
  `id` int(11) NOT NULL AUTO_INCREMENT,
  `user_id` varchar(255) DEFAULT NULL,
  `money` int(11) DEFAULT 0,
  PRIMARY KEY (`id`)
) ENGINE=InnoDB DEFAULT CHARSET=utf8;
```
### Step 4: Start Seata-Server

- Download server [package](https://github.com/seata/seata/releases), unzip it.
- Start Seata-Server

```shell
sh seata-server.sh $LISTEN_PORT $PATH_FOR_PERSISTENT_DATA

e.g.

sh seata-server.sh 8091 /home/admin/seata/data/
```

### Step 5: Run example

- Start AccountService ([DubboAccountServiceStarter](https://github.com/seata/seata-samples/blob/master/dubbo/src/main/java/com/seata/seata/samples/dubbo/starter/DubboAccountServiceStarter.java)).
- Start StorageService ([DubboStorageServiceStarter](https://github.com/seata/seata-samples/blob/master/dubbo/src/main/java/com/seata/seata/samples/dubbo/starter/DubboStorageServiceStarter.java)).
- Start OrderService ([DubboOrderServiceStarter](https://github.com/seata/seata-samples/blob/master/dubbo/src/main/java/com/seata/seata/samples/dubbo/starter/DubboOrderServiceStarter.java)).
- Run BusinessService for test ([DubboBusinessTester](https://github.com/seata/seata-samples/blob/master/dubbo/src/main/java/com/seata/seata/samples/dubbo/starter/DubboBusinessTester.java)).

### Related projects
* seata:          https://github.com/seata/seata/
* seata-samples : https://github.com/seata/seata-samples  
