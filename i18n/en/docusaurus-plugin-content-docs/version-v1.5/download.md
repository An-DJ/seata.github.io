---
title: Downloads
keywords: [Seata, Downloads, Version]
description: This article will introduce you how to understand the details of each version and upgrade matters needing attention.
---


# Downloads

# Seata

> GitHub: https://github.com/seata/seata
>
> Release Notes: https://github.com/seata/seata/releases

### 1.5.2 (2022-07-12)

[source](https://github.com/seata/seata/archive/v1.5.2.zip) |
[binary](https://github.com/seata/seata/releases/download/v1.5.2/seata-server-1.5.2.zip)

<details>
  <summary><mark>Release notes</mark></summary>


### Seata 1.5.2

Seata 1.5.2 Released.

Seata is an easy-to-use, high-performance, open source distributed transaction solution.

The version is updated as follows:

### feature：
- [[#4661](https://github.com/seata/seata/pull/4713)] support xid load balance
- [[#4676](https://github.com/seata/seata/pull/4676)] support server to expose Nacos services by mounting SLB
- [[#4642](https://github.com/seata/seata/pull/4642)] support batch message parallel processing
- [[#4567](https://github.com/seata/seata/pull/4567)] support where method condition(find_in_set)


### bugfix：
- [[#4515](https://github.com/seata/seata/pull/4515)] fix the error of SeataTCCFenceAutoConfiguration when database unused
- [[#4661](https://github.com/seata/seata/pull/4661)] fix sql exception with PostgreSQL in module console
- [[#4667](https://github.com/seata/seata/pull/4682)] fix the exception in RedisTransactionStoreManager for update map During iteration
- [[#4678](https://github.com/seata/seata/pull/4678)] fix the error of key transport.enableRmClientBatchSendRequest cache penetration if not configure
- [[#4701](https://github.com/seata/seata/pull/4701)] fix missing command line args
- [[#4607](https://github.com/seata/seata/pull/4607)] fix bug on skipping lock check
- [[#4696](https://github.com/seata/seata/pull/4696)] fix oracle database insert value
- [[#4726](https://github.com/seata/seata/pull/4726)] fix batch message send may return NullPointException
- [[#4729](https://github.com/seata/seata/pull/4729)] fix set AspectTransactional.rollbackForClassName with wrong value
- [[#4653](https://github.com/seata/seata/pull/4653)] fix the sql exception when pk is non-numeric in INSERT_ON_DUPLICATE SQL

### optimize：
- [[#4650](https://github.com/seata/seata/pull/4650)] fix some security vulnerabilities
- [[#4670](https://github.com/seata/seata/pull/4670)] optimize the thread pool size of branchResultMessageExecutor
- [[#4662](https://github.com/seata/seata/pull/4662)] optimize rollback transaction metrics
- [[#4693](https://github.com/seata/seata/pull/4693)] optimize the console navigation bar
- [[#4700](https://github.com/seata/seata/pull/4700)] fix maven-compiler-plugin and maven-resources-plugin execute failed
- [[#4711](https://github.com/seata/seata/pull/4711)] separate lib dependencies for deployments
- [[#4720](https://github.com/seata/seata/pull/4720)] optimize pom description
- [[#4728](https://github.com/seata/seata/pull/4728)] upgrade logback dependency to 1.2.9
- [[#4745](https://github.com/seata/seata/pull/4745)] support mysql8 in release package
- [[#4626](https://github.com/seata/seata/pull/4626)] Replace `flatten-maven-plugin` with `easyj-maven-plugin` to fix the conflict between `shade` and `flatten`
- [[#4629](https://github.com/seata/seata/pull/4629)] check relation of before status and after status when updating global session
- [[#4662](https://github.com/seata/seata/pull/4662)] make EnhancedServiceLoader more readable

### test:

- [[#4544](https://github.com/seata/seata/pull/4544)] optimize jackson dependencies in TransactionContextFilterTest
- [[#4731](https://github.com/seata/seata/pull/4731)] fix UT failed in AsyncWorkerTest and LockManagerTest

Thanks to these contributors for their code commits. Please report an unintended omission.

<!-- Please make sure your Github ID is in the list below -->
- [slievrly](https://github.com/slievrly)
- [pengten](https://github.com/pengten)
- [YSF-A](https://github.com/YSF-A)
- [tuwenlin](https://github.com/tuwenlin)
- [Ifdevil](https://github.com/Ifdevil)
- [wingchi-leung](https://github.com/wingchi-leung)
- [liurong](https://github.com/robynron)
- [opelok-z](https://github.com/opelok-z)
- [funky-eyes](https://github.com/funky-eyes)
- [2129zxl](https://github.com/2129zxl)
- [Smery-lxm](https://github.com/Smery-lxm)
- [doubleDimple](https://github.com/doubleDimple)
- [wangliang181230](https://github.com/wangliang181230)
- [Bughue](https://github.com/Bughue)
- [AYue-94](https://github.com/AYue-94)
- [lingxiao-wu](https://github.com/lingxiao-wu)
- [caohdgege](https://github.com/caohdgege)

Also, we receive many valuable issues, questions and advices from our community. Thanks for you all.

#### Link

- **Seata:** https://github.com/seata/seata
- **Seata-Samples:** https://github.com/seata/seata-samples
- **Release:** https://github.com/seata/seata/releases
- **WebSite:** https://seata.io

</details>

### 1.5.1 (2021-05-17)

[source](https://github.com/seata/seata/archive/v1.5.1.zip) |
[binary](https://github.com/seata/seata/releases/download/v1.5.1/seata-server-1.5.1.zip)

<details>
  <summary><mark>Release notes</mark></summary>

### feature：
- [[#4115](https://github.com/seata/seata/pull/4115) ] support console management
- [[#3472](https://github.com/seata/seata/pull/3472) ] add redisLocker's lua mode
- [[#3575](https://github.com/seata/seata/pull/3575) ] support the mixed use of different storages of locks and sessions
- [[#3374](https://github.com/seata/seata/pull/3374) ] add a Executor for INSERT ON DUPLICATE KEY UPDATE
- [[#3642](https://github.com/seata/seata/pull/3642) ] provide an api to share tcc phase-1's params to phase-2
- [[#3064](https://github.com/seata/seata/pull/3064) ] support configuring the order of the TM and TCC interceptor
- [[#2852](https://github.com/seata/seata/pull/2852) ] support configuring scan target for GlobalTransactionScanner
- [[#3683](https://github.com/seata/seata/pull/3683) ] support redis distributed lock to prevent multi TC competition
- [[#3545](https://github.com/seata/seata/pull/3545) ] TCC mode support idempotent and anti hanging
- [[#3009](https://github.com/seata/seata/pull/3009) ] support server start with springboot and config with application.yaml
- [[#3652](https://github.com/seata/seata/pull/3652) ] support APM with SkyWalking
- [[#3823](https://github.com/seata/seata/pull/3823) ] TCC mode supports customized parameters list of the method in phase two
- [[#3642](https://github.com/seata/seata/pull/3642) ] TCC mode's try method supports passing `BusinessActionContext` implicitly
- [[#3856](https://github.com/seata/seata/pull/3856) ] support edas-hsf RPC framework
- [[#3880](https://github.com/seata/seata/pull/3880) ] contributing md support chinese.
- [[#2568](https://github.com/seata/seata/pull/2568) ] support GlobalTransactionInterceptor expression
- [[#3886](https://github.com/seata/seata/pull/3886) ] support the registry center network preferences
- [[#3869](https://github.com/seata/seata/pull/3869) ] support get configuration from environment
- [[#3906](https://github.com/seata/seata/pull/3906) ] support SPI unload
- [[#3668](https://github.com/seata/seata/pull/3668) ] support kotlin coroutine
- [[#3968](https://github.com/seata/seata/pull/3968) ] support brpc-java RPC framework
- [[#4134](https://github.com/seata/seata/pull/4134) ] init the console basic code
- [[#4268](https://github.com/seata/seata/pull/4268) ] query global session in the file mode
- [[#4281](https://github.com/seata/seata/pull/4281) ] query global session and global lock in the redis mode
- [[#4293](https://github.com/seata/seata/pull/4293) ] get global lock in the file mode
- [[#4335](https://github.com/seata/seata/pull/4335) ] Realize configuration center upload configuration interactive script (nacos,etcd3)
- [[#4360](https://github.com/seata/seata/pull/4360) ] Realize configuration center upload configuration interactive script (apollo,consul,zk)
- [[#4320](https://github.com/seata/seata/pull/4320) ] realize the interface of console: get global session and global lock in the db mode
- [[#4435](https://github.com/seata/seata/pull/4435) ] console front-end page implementation
- [[#4480](https://github.com/seata/seata/pull/4480) ] implementation of DefaultAuthSigner
- [[#3870](https://github.com/seata/seata/pull/3870) ] make seata-bom be the real Bill-Of-Material
- [[#3487](https://github.com/seata/seata/pull/3487) ] add db realization for distribute lock
- [[#3889](https://github.com/seata/seata/pull/3889) ] registry add heartbeat
- [[#3951](https://github.com/seata/seata/pull/3951) ] support zstd compressor
- [[#2838](https://github.com/seata/seata/pull/2838) ] Saga support auto configuration in the spring boot project

### bugfix：
- [[#3497](https://github.com/seata/seata/pull/3497) ] fix tcc phase two response timeout exception
- [[#3686](https://github.com/seata/seata/pull/3686) ] fix NPE and wrong cluster name of Apollo
- [[#3702](https://github.com/seata/seata/pull/3702) ] fix some comments
- [[#3716](https://github.com/seata/seata/pull/3716) ] fix the problem in the findTargetClass method
- [[#3717](https://github.com/seata/seata/pull/3717) ] fix typo of interval
- [[#3773](https://github.com/seata/seata/pull/3773) ] fix consul not found tc cluster
- [[#3695](https://github.com/seata/seata/pull/3695) ] fix mariadb unable to create XA connection
- [[#3783](https://github.com/seata/seata/pull/3783) ] fix the problem that store mode does not take effect
- [[#3740](https://github.com/seata/seata/pull/3740) ] fix that `LocalThread` is not cleared when the `Saga` transaction ends
- [[#3792](https://github.com/seata/seata/pull/3792) ] fix the Server can't find redis-host property
- [[#3828](https://github.com/seata/seata/pull/3828) ] fix StringUtils StackOverflowError
- [[#3817](https://github.com/seata/seata/pull/3817) ] fix TC SkyWalking topo calling node not gather
- [[#3803](https://github.com/seata/seata/pull/3803) ] fix ReflectionUtil throw unexpected exception
- [[#3879](https://github.com/seata/seata/pull/3879) ] fix postgresql multi schema throw not found channel exception
- [[#3881](https://github.com/seata/seata/pull/3881) ] fix getConfig with different default value return the first
- [[#3897](https://github.com/seata/seata/pull/3897) ] fix LocalDataTime type in FastjsonUndoLogParser can't be rollback
- [[#3901](https://github.com/seata/seata/pull/3901) ] fix seataio/seata-server servlet-api conflict
- [[#3931](https://github.com/seata/seata/pull/3931) ] fix the wrong path and filename when dump the jvm memory for analysis
- [[#3978](https://github.com/seata/seata/pull/3978) ] fix NPE cause by future timeout
- [[#4266](https://github.com/seata/seata/pull/4266) ] fix register branch and release lock failed when the size of rows that modified is greater than 1000 in oracle
- [[#3949](https://github.com/seata/seata/pull/3949) ] fix the problem that `nacos-config.py` will not skip blank options. fix bug that split options may cause content loss
- [[#3988](https://github.com/seata/seata/pull/3988) ] fix the problem that nacos not found user when password has special characters
- [[#3998](https://github.com/seata/seata/pull/3998) ] fix the NPE of jedis multi.exec
- [[#4011](https://github.com/seata/seata/pull/4011) ] fix can not get properties of distributed-lock-table in springboot
- [[#4025](https://github.com/seata/seata/pull/4025) ] fix potential database resource leak
- [[#4023](https://github.com/seata/seata/pull/4023) ] fix the problem that the xid is not cleared in some scenes of dubbo
- [[#4039](https://github.com/seata/seata/pull/4039) ] fix RM did not clear XID after the local transaction threw an exception
- [[#4032](https://github.com/seata/seata/pull/4032) ] fix ApplicationContext already closed problem when Seata server using ShutdownHook to destroy
- [[#4074](https://github.com/seata/seata/pull/4074) ] fix prevents XA mode resource suspension
- [[#4107](https://github.com/seata/seata/pull/4107) ] fix deadlock problems during project construction
- [[#4158](https://github.com/seata/seata/pull/4158) ] fix the logback can't load the `RPC_PORT`
- [[#4162](https://github.com/seata/seata/pull/4162) ] fix correct built-in properties for redis registry
- [[#4165](https://github.com/seata/seata/pull/4165) ] fix `StringUtils.toString(obj)` throw `ClassCastException` when the obj is primitive data array
- [[#4169](https://github.com/seata/seata/pull/4169) ] fix xa mode originalConnection has been closed, cause PhaseTwo fail to execute
- [[#4177](https://github.com/seata/seata/pull/4177) ] fix the problem of accidentally releasing the global lock
- [[#4174](https://github.com/seata/seata/pull/4174) ] fix delete undo log connection already closed
- [[#4189](https://github.com/seata/seata/pull/4189) ] fix the `kafka-appender.xml` and `logstash-appender.xml`
- [[#4213](https://github.com/seata/seata/pull/4213) ] fix code for "sessionMode" not execute problem
- [[#4220](https://github.com/seata/seata/pull/4220) ] fix some problems with `zstd` compressor and add the version of the `kotlin-maven-plugin`
- [[#4222](https://github.com/seata/seata/pull/4222) ] fix could not rollback when insert field list is empty
- [[#4253](https://github.com/seata/seata/pull/4253) ] update executor store the actually modified columns but not only the columns in set condition
- [[#4276](https://github.com/seata/seata/pull/4276) ] fix seata-test module UT not work
- [[#4278](https://github.com/seata/seata/pull/4278) ] fix the problem that mysql's Blob/Clob/NClob data type cannot be deserialized
- [[#4302](https://github.com/seata/seata/pull/4302) ] fix the problem that other ORMs may not be able to obtain the auto-incrementing primary key value
- [[#4233](https://github.com/seata/seata/pull/4233) ] fix data remanence problems in lock and branch under specific circumstances.
- [[#4308](https://github.com/seata/seata/pull/4308) ] fix the TableMetaCache parsing problem with the same table under multiple Postgresql schemas
- [[#4326](https://github.com/seata/seata/pull/4326) ] fix inability to build Executor when using mariadb driver
- [[#4355](https://github.com/seata/seata/pull/4355) ] fix mysql-loadbalance resource id error
- [[#4310](https://github.com/seata/seata/pull/4310) ] fix the problem that failed to obtain the self increment ID of MySQL database through "select last_insert_id"
- [[#4331](https://github.com/seata/seata/pull/4331) ] fix dirty write check exception that may occur when using ONLY_CARE_UPDATE_COLUMNS configuration
- [[#4228](https://github.com/seata/seata/pull/4228) ] fix resource suspension in xa mode caused by choose other ip as channel alternative
- [[#4408](https://github.com/seata/seata/pull/4408) ] fix the invalid environment variable in container env
- [[#4441](https://github.com/seata/seata/pull/4441) ] fix the problem that pipelined resources are not closed in redis mode and add branchSession judge branchSessions is not null
- [[#4438](https://github.com/seata/seata/pull/4438) ] fix the problem that GlobalSession could not be deleted normally in the case of delayed deletion in the file mode of the develop branch
- [[#4432](https://github.com/seata/seata/pull/4432) ] fix the inability to get some remote configurations
- [[#4452](https://github.com/seata/seata/pull/4452) ] fix the change log of 'service.disableGlobalTransaction' config
- [[#4449](https://github.com/seata/seata/pull/4449) ] fix redis mode page npe and optimize get globalSession on average
- [[#4459](https://github.com/seata/seata/pull/4459) ] fix the failure to obtain before image and after image on oracle and pgsql of the develop branch
- [[#4471](https://github.com/seata/seata/pull/4471) ] in branch 'develop', fix the error when service.vgroupMapping change
- [[#4474](https://github.com/seata/seata/pull/4474) ] fix Mysql multi-bit Bit type field rollback error
- [[#4492](https://github.com/seata/seata/pull/4492) ] fix the failure to update cluster list dynamically when use eureka of the develop branch
- [[#4535](https://github.com/seata/seata/pull/4535) ] fix FileSessionManagerTest fail
- [[#4561](https://github.com/seata/seata/pull/4561) ] fix allSessions/findGlobalSessions may return null and cause npe
- [[#4505](https://github.com/seata/seata/pull/4505) ] fix fastjson serialization of time data types
- [[#4579](https://github.com/seata/seata/pull/4579) ] fix prepareUndoLogAll of MySQLInsertOrUpdateExecutor
- [[#4005](https://github.com/seata/seata/pull/4005) ] fix PK constraint name isn't the same as the unique index name which is belong to PK
- [[#4062](https://github.com/seata/seata/pull/4062) ] fix saga complex parameter deserialization problem
- [[#4199](https://github.com/seata/seata/pull/4199) ] fix rpc tm request timeout
- [[#4352](https://github.com/seata/seata/pull/4352) ] fix some problem of the sql parser
- [[#4487](https://github.com/seata/seata/pull/4487) ] fix remove Pagination hideOnlyOnePage attribute
- [[#4449](https://github.com/seata/seata/pull/4449) ] fix optimize redis limit and fix redis page bug
- [[#4608](https://github.com/seata/seata/pull/4608) ] fix test case
- [[#3110](https://github.com/seata/seata/pull/3110) ] fix the problem of unit test


### optimize：
- [[#4163](https://github.com/seata/seata/pull/4163) ] improve CONTRIBUTING docs
- [[#3678](https://github.com/seata/seata/pull/3678) ] supplement missing configuration and new version documents
- [[#3654](https://github.com/seata/seata/pull/3654) ] fix typo,applicationContex -> applicationContext
- [[#3615](https://github.com/seata/seata/pull/3615) ] asynchronous deletion after the transaction is committed
- [[#3687](https://github.com/seata/seata/pull/3687) ] fix the case that could not retry acquire global lock
- [[#3689](https://github.com/seata/seata/pull/3689) ] modify the attribute prefix in the file file.properties
- [[#3528](https://github.com/seata/seata/pull/3528) ] optimize the memory footprint of redis mode
- [[#3700](https://github.com/seata/seata/pull/3700) ] optimize the speed of buildLockKey
- [[#3588](https://github.com/seata/seata/pull/3588) ] optimize the logic of datasource auto proxy
- [[#3626](https://github.com/seata/seata/pull/3626) ] remove repeat change status
- [[#3722](https://github.com/seata/seata/pull/3722) ] add the basic code of distributed lock
- [[#3713](https://github.com/seata/seata/pull/3713) ] unified the default value of enableClientBatchSendRequest
- [[#3120](https://github.com/seata/seata/pull/3120) ] optimize `Configuration` and add unit tests
- [[#3735](https://github.com/seata/seata/pull/3735) ] do not load `LoadBalance` if not necessary
- [[#3770](https://github.com/seata/seata/pull/3770) ] close the `Closeable` and optimize some code
- [[#3627](https://github.com/seata/seata/pull/3627) ] use TreeMap instead of the LinkedHashMap in TableMeta to compatible high level MySQL
- [[#3760](https://github.com/seata/seata/pull/3760) ] opt the logback's config of `seata-server`
- [[#3765](https://github.com/seata/seata/pull/3765) ] Transfer the operation of adding configuration class from 'AutoConfiguration' to 'EnvironmentPostProcessor'
- [[#3730](https://github.com/seata/seata/pull/3730) ] Refactoring the code of TCC mode
- [[#3820](https://github.com/seata/seata/pull/3820) ] add column `action_name` to the `tcc_fence_log`
- [[#3738](https://github.com/seata/seata/pull/3738) ] `JacksonUndoLogParser` supports to parsing `LocalDateTime`
- [[#3794](https://github.com/seata/seata/pull/3794) ] optimize the packaging of `seata-server`
- [[#3795](https://github.com/seata/seata/pull/3795) ] optimize zk registry lookup performance
- [[#3840](https://github.com/seata/seata/pull/3840) ] optimiza `apm-skwalking` operation method to generate rules
- [[#3834](https://github.com/seata/seata/pull/3834) ] optimize `seata-distribution` add `apm-seata-skywalking`
- [[#3847](https://github.com/seata/seata/pull/3847) ] optimize ConcurrentHashMap.newKeySet replace ConcurrentSet
- [[#3311](https://github.com/seata/seata/pull/3311) ] supports reading all configurations from a single Consul key
- [[#3849](https://github.com/seata/seata/pull/3849) ] optimize string concat
- [[#3890](https://github.com/seata/seata/pull/3890) ] optimize only the inserted fields are checked
- [[#3895](https://github.com/seata/seata/pull/3895) ] optimize decode exception
- [[#3898](https://github.com/seata/seata/pull/3898) ] add jib-maven-plugin
- [[#3904](https://github.com/seata/seata/pull/3904) ] ehance metrics and fix seata-server UT not work
- [[#3212](https://github.com/seata/seata/pull/3212) ] optimize recognize sql in limit and order by
- [[#3905](https://github.com/seata/seata/pull/3905) ] optimize nacos-config.sh to support ash
- [[#3935](https://github.com/seata/seata/pull/3935) ] optimize Send redis command at one time using pipeline
- [[#3916](https://github.com/seata/seata/pull/3916) ] optimize determine whether the server in the register is alive
- [[#3918](https://github.com/seata/seata/pull/3918) ] cache reflection results of the fields and methods
- [[#3898](https://github.com/seata/seata/pull/3898) ] add jib-maven-plugin
- [[#3907](https://github.com/seata/seata/pull/3907) ] optimize set server port
- [[#3912](https://github.com/seata/seata/pull/3912) ] support config JVM param in env
- [[#3939](https://github.com/seata/seata/pull/3939) ] use map instead of if else judge for more change in the future
- [[#3955](https://github.com/seata/seata/pull/3955) ] add a start banner for seata
- [[#3954](https://github.com/seata/seata/pull/3954) ] replace @Deprecated getOwnernName to getOwnerName in druid
- [[#3981](https://github.com/seata/seata/pull/3981) ] optimize service port priority
- [[#4013](https://github.com/seata/seata/pull/4013) ] optimize channel alive check
- [[#3982](https://github.com/seata/seata/pull/3982) ] optimize readme doc and upgrade some dependencies
- [[#3949](https://github.com/seata/seata/pull/3949) ] `nacos-config.py` support default parameters and optional input parameters
- [[#3991](https://github.com/seata/seata/pull/3991) ] disable listening in the FileConfiguration center in Springboot
- [[#3994](https://github.com/seata/seata/pull/3994) ] Optimize the mechanism of periodically deleting tasks in the `tcc_fence_log` table
- [[#3327](https://github.com/seata/seata/pull/3327) ] supports reading all configurations from a single Etcd3 key
- [[#4001](https://github.com/seata/seata/pull/4001) ] support to read YML configuration from Nacos, Zookeeper, Consul, Etcd3
- [[#4017](https://github.com/seata/seata/pull/4017) ] optimize file configuration
- [[#4018](https://github.com/seata/seata/pull/4018) ] optimize Apollo configuration
- [[#4021](https://github.com/seata/seata/pull/4021) ] optimize Nacos、Consul、Zookeeper、Etcd3 configuration
- [[#4034](https://github.com/seata/seata/pull/4034) ] optimize Nacos, Consul, Zookeeper and Etcd3 configuration Junit test Class
- [[#4055](https://github.com/seata/seata/pull/4055) ] optimize NetUtil#getLocalAddress0
- [[#4086](https://github.com/seata/seata/pull/4086) ] optimize lazily load branch transactions and task scheduling
- [[#4056](https://github.com/seata/seata/pull/4056) ] optimize the DurationUtil
- [[#4103](https://github.com/seata/seata/pull/4103) ] optimize AbstractLockManager#collectRowLocks logic
- [[#3733](https://github.com/seata/seata/pull/3733) ] optimize acquire lock logic
- [[#4144](https://github.com/seata/seata/pull/4144) ] support default configuration of tx-service-group
- [[#4157](https://github.com/seata/seata/pull/4157) ] optimize client batch sending.
- [[#4191](https://github.com/seata/seata/pull/4191) ] support rpc timeout can be customized.
- [[#4216](https://github.com/seata/seata/pull/4216) ] no more attempt to clean undolog for none AT mode
- [[#4176](https://github.com/seata/seata/pull/4176) ] use expire key instead hash when using redis as registry center.
- [[#4196](https://github.com/seata/seata/pull/4196) ] tc batch response to client.
- [[#4212](https://github.com/seata/seata/pull/4212) ] optimize the interface of the console
- [[#4237](https://github.com/seata/seata/pull/4237) ] skip check lock when all the before image is empty
- [[#4251](https://github.com/seata/seata/pull/4251) ] optimize partial code handling
- [[#4262](https://github.com/seata/seata/pull/4262) ] optimize tcc module code handling
- [[#4235](https://github.com/seata/seata/pull/4235) ] optimize instance saved in eureka
- [[#4277](https://github.com/seata/seata/pull/4277) ] optimize acquire lock return fail-fast code in redis-pipeline mode.
- [[#4284](https://github.com/seata/seata/pull/4284) ] support authentication of MSE-Nacos with ak/sk
- [[#4299](https://github.com/seata/seata/pull/4299) ] optimize exceptions to make them friendly
- [[#4300](https://github.com/seata/seata/pull/4300) ] optimize let DefaultCoordinator invoke NettyRemotingServer's close method,no longer closed by ServerRunner
- [[#4270](https://github.com/seata/seata/pull/4270) ] improve the performance of global commit and global rollback, asynchronous branch transaction cleanup
- [[#4307](https://github.com/seata/seata/pull/4307) ] when in TCC mode there is no need to delete global locks
- [[#4303](https://github.com/seata/seata/pull/4303) ] `tcc_fence_log` table hanging log records are deleted asynchronously
- [[#4328](https://github.com/seata/seata/pull/4328) ] upload configuration script support comments
- [[#4305](https://github.com/seata/seata/pull/4305) ] optimize acquire global lock fail error log print on tc
- [[#4336](https://github.com/seata/seata/pull/4336) ] add SQL exception prompt not supported by AT mode
- [[#4359](https://github.com/seata/seata/pull/4359) ] support configuration metadata read from environment variables
- [[#4247](https://github.com/seata/seata/pull/4247) ] add tests for `java17` and `springboot` in the `github/actions`
- [[#4353](https://github.com/seata/seata/pull/4353) ] Slimming down for the `seata-all.jar`
- [[#4393](https://github.com/seata/seata/pull/4393) ] skip reload for redis & db mode
- [[#4400](https://github.com/seata/seata/pull/4400) ] asynchronous tasks handle global transactions in parallel
- [[#4391](https://github.com/seata/seata/pull/4391) ] commit/rollback retry timeout event
- [[#4409](https://github.com/seata/seata/pull/4409) ] add copyright header to test classes
- [[#4282](https://github.com/seata/seata/pull/4282) ] optimize build UndoItem logic
- [[#4407](https://github.com/seata/seata/pull/4407) ] file mode does not require lazy processing of sessions
- [[#4436](https://github.com/seata/seata/pull/4436) ] optimize global session query in file mode
- [[#4431](https://github.com/seata/seata/pull/4431) ] limit the number of queries in Redis storage mode
- [[#4465](https://github.com/seata/seata/pull/4465) ] optimize client version transfer in tc batch response to client mode.
- [[#4469](https://github.com/seata/seata/pull/4469) ] optimize the way to get configuration in DB mode of console
- [[#4478](https://github.com/seata/seata/pull/4478) ] optimize Nacos config and naming properties
- [[#4522](https://github.com/seata/seata/pull/4522) ] optimize GC parameters in JVM
- [[#4517](https://github.com/seata/seata/pull/4517) ] enhance fail/timeout status metric and log level
- [[#4451](https://github.com/seata/seata/pull/4451) ] filesessionmanager changed to singleton and optimized task thread pool processing
- [[#4551](https://github.com/seata/seata/pull/4551) ] optimize metrics rt statistics
- [[#4574](https://github.com/seata/seata/pull/4574) ] support accessKey/secretKey auto configuration
- [[#4583](https://github.com/seata/seata/pull/4583) ] use HmacSHA256 instead of HmacSHA1 for ram signature
- [[#4591](https://github.com/seata/seata/pull/4591) ] optimize the default value of the switch
- [[#3780](https://github.com/seata/seata/pull/3780) ] optimize upgrade the Druid version
- [[#3797](https://github.com/seata/seata/pull/3797) ] optimize support instance `BusinessActionContext` outside the TCC try method
- [[#3909](https://github.com/seata/seata/pull/3909) ] optimize `collectRowLocks` method
- [[#3763](https://github.com/seata/seata/pull/3763) ] optimize github actions
- [[#4345](https://github.com/seata/seata/pull/4345) ] optimize fix the path of the package
- [[#4346](https://github.com/seata/seata/pull/4346) ] optimize the log of the server and remove lombok
- [[#4348](https://github.com/seata/seata/pull/4348) ] optimize Unified management the versions of maven-plugin
- [[#4354](https://github.com/seata/seata/pull/4354) ] optimize the tests of `SAGA`
- [[#4227](https://github.com/seata/seata/pull/4227) ] optimize the versions of the dependencies
- [[#4403](https://github.com/seata/seata/pull/4403) ] optimize disable `SAGA` tests
- [[#4453](https://github.com/seata/seata/pull/4453) ] optimize upgrade eureka-clients and xstream dependencies
- [[#4481](https://github.com/seata/seata/pull/4481) ] optimize nacos config and naming properties
- [[#4477](https://github.com/seata/seata/pull/4477) ] optimize debug log and fix typo
- [[#4484](https://github.com/seata/seata/pull/4484) ]optimize  the log of TM/RM register
- [[#3874](https://github.com/seata/seata/pull/4484) ] optimize Add logo of registered enterprise,and Change image source to Alicdn
- [[#4458](https://github.com/seata/seata/pull/4458) ] optimize fix the README.md of metrices module
- [[#4482](https://github.com/seata/seata/pull/4482) ] optimize remove duplicated word

Thanks to these contributors for their code commits. Please report an unintended omission.
- [slievrly](https://github.com/slievrly)
- [wangliang181230](https://github.com/wangliang181230)
- [funky-eyes](https://github.com/funky-eyes)
- [lvekee](https://github.com/lvekee)
- [caohdgege](https://github.com/caohdgege)
- [lightClouds917](https://github.com/lightClouds917)
- [objcoding](https://github.com/objcoding)
- [siyu](https://github.com/Pinocchio2018)
- [GoodBoyCoder](https://github.com/GoodBoyCoder)
- [pengten](https://github.com/pengten)
- [Bughue](https://github.com/Bughue)
- [doubleDimple](https://github.com/doubleDimple)
- [zhaoyuguang](https://github.com/zhaoyuguang)
- [liuqiufeng](https://github.com/liuqiufeng)
- [jsbxyyx](https://github.com/jsbxyyx)
- [lcmvs](https://github.com/lcmvs)
- [onlinechild](https://github.com/onlinechild)
- [xjlgod](https://github.com/xjlgod)
- [h-zhi](https://github.com/h-zhi)
- [tanzzj](https://github.com/tanzzj)
- [miaoxueyu](https://github.com/miaoxueyu)
- [selfishlover](https://github.com/selfishlover)
- [tuwenlin](https://github.com/tuwenlin)
- [dmego](https://github.com/dmego)
- [xiaochangbai](https://github.com/xiaochangbai)
- [Rubbernecker](https://github.com/Rubbernecker)
- [ruanun](https://github.com/ruanun)
- [huan415](https://github.com/huan415)
- [drgnchan](https://github.com/drgnchan)
- [cmonkey](https://github.com/cmonkey)
- [13414850431](https://github.com/13414850431)
- [ls9527](https://github.com/ls9527)
- [xingfudeshi](https://github.com/xingfudeshi)
- [spilledyear](https://github.com/spilledyear)
- [kaka2code](https://github.com/kaka2code)
- [iqinning](https://github.com/iqinning)
- [yujianfei1986](https://github.com/yujianfei1986)
- [elrond-g](https://github.com/elrond-g)
- [jameslcj](https://github.com/jameslcj)
- [zhouchuhang](https://github.com/zch0214)
- [xujj](https://github.com/XBNGit)
- [mengxzh](https://github.com/mengxzh)
- [portman](https://github.com/iportman)
- [anselleeyy](https://github.com/anselleeyy)
- [wangyuewen](https://github.com/2858917634)
- [imherewait](https://github.com/imherewait)
- [wfnuser](https://github.com/wfnuser)
- [zhixing](https://github.com/chenlei3641)

Also, we receive many valuable issues, questions and advices from our community. Thanks for you all.
</details>
