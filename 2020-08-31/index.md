### 上周遗留问题

1. `handler` 中开启事务,由于`postgress` 的原因,在并发高时,会导致锁表.
2. 项目的错误处理不够用户化,开发模式也不要返回错误页面而是通过日志记录

----

### 今日解决问题:

1. 通过查询使用`navicate`查询`postgress`数据库中所有活动的连接. 查找出活动类型,及`pid`
```sql
    select pid, state, usename, query, query_start 
    from pg_stat_activity 
    where pid in (
    select pid from pg_locks l 
    join pg_class t on l.relation = t.oid 
    and t.relkind = 'r' 
    
    );
```
2. 关闭锁住的连接
```sql
SELECT pg_cancel_backend('pid');
```

3. 对于事务出错未完成提交或者回滚而一直处于阻塞的状态,通过1查出相关的操作信息,手动进行事务的提交或回滚.
4. 针对`buffalo`框架,只在一个`handle`中使用事务操作,避免多个`handle`同时开启事务,而又由于某个`handle`出现错误导致事务无法正常进行回滚或提交
5. 修改逻辑,取消使用事务.分解操作.操作逻辑优化

----

重构了配置创建及编辑的操作处理,规范代码.优化逻辑