# 使用redis-port进行迁移 {#concept_u3d_fj1_wdb .concept}

用户可以使用redis-port将自建 Redis 迁移至云数据库 Redis 版。

## 下载 redis-port { .section}

[redis-port地址](http://docs-aliyun.cn-hangzhou.oss.aliyun-inc.com/assets/attach/85829/cn_zh/1533199526614/redis-port%282%29)

## 使用示例 { .section}

```
./redis-port  sync  --from=src_host:src_port --password=src_password  --target=dst_host:dst_port   --auth=dst_password  [--filterkey="str1|str2|str3"] [--targetdb=DB] [--rewrite] [--bigkeysize=SIZE] [--logfile=REDISPORT.LOG]
```

**参数说明**

-   src\_host：自建 redis 域名（或者 IP）
-   src\_port：自建 redis 端口
-   src\_password：自建 redis 密码
-   dst\_host：云数据库 redis 域名
-   dst\_port：云数据库 redis 端口
-   dst\_password：云数据库 redis 密码
-   str1|str2|str3：过滤具有 str1 或 str2 或 str3 的 key
-   DB：将同步入云 redis 的 DB
-   rewrite：覆盖已经写入的 key
-   bigkeysize=SIZE：当写入的 value 大于 SIZE 时，走大 key 写入模式

## 根据 redis-port 日志查看数据同步状态 { .section}

![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/3157/15331999982803_zh-CN.png)

当出现`sync rdb done`时全量同步完成，进入增量同步的模式。

