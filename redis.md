## 1.基本数据结构
String：字符串   List：列表   Set:无序集合   ZSet：有序集合   Hash：散列

## 2.常用配置选项
指定是否使用守护进程：daemonize no
日志级别：loglevel verbose  //Redis总共支持四个级别：debug、verbose、notice、warning，默认为verbose
日志文件：logfile stdout  //默认是标准输出
本地数据库文件名：dbfilename dump.rdb
本地数据库文件目录：dir ./
设置连接密码：requirepass password  //默认无密码
本机作为slave自动同步master的数据：slaveof <masterip> <masterport>
本机作为slave连接master的密码：masterauth <master-password>

## 3.基本命令
字符串：set key value / get key / del key / exists key / expire key seconds
列表：lpush key value.. / lrange key start stop
Hash：hmset key field value.. /hget key field
无序集合：sadd key member..  / smembers key
有序集合：zadd key score member.. / zrangbyscore key min  max

## 4.进阶命令
--字符串--
设置并返回key更新前的值：getset key value
同时返回多个key的值：mget key..
同时设置多个key的值：mset key value ..
如果key不存在则设置：setnx key value
增加值为数字的key的值：incrby key no 或 incrbyfloat key no  // no = 1 时可简写为  incr key
减少值为数字的key的值：decrby key no // no = 1 时可简写为  decr key
追件或设置值为字符串的key：append key value  //不存在则设置

--Hash--
删除key中的field：hdel key field
查询全部字段和值：hgetall key
设置或更新字段值：hset key field value
检查key中是否存在field：hexists key field

--List--
删除列表中的指定元素：lrem key count value
count > 0 从头向尾搜索，删除count个value
count = 0 删除全部value
count < 0 从尾向头搜索，删除绝对count个value

--Set--
差集：sdiff key1 key2.. //(key1-key2)-...
交集：sinter key1 key2.. //key1 ∩ key2 ∩ ..
并集：sunion key1 key2..
删除成员：srem key member..

--ZSet--
返回指定分数区间的成员数：zcount key min max //包含min和max
返回排名：zrank key member
返回分数值：zscore key member


5.基本数据结构总数
列表：llen key
Hash：hlen key
set：scard key
zset：zcard key




