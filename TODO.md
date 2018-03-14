# 参考实现
https://stackoverflow.com/questions/9274777/mongodb-as-a-queue-service

待执行的任务存储到mongodb中
后台任务通过原子操作接口findAndModify设置processing标志，防止消息被二次处理
执行完毕之后删除（设置done标志）对应的任务记录
可在任务上设置failed标志，统计任务执行的失败次数

大量可选的消息队列解决方案
https://stackoverflow.com/questions/731233/activemq-or-rabbitmq-or-zeromq-or/5350026#5350026

mongodb中的原子操作与事务处理
https://docs.mongodb.com/manual/core/write-operations-atomicity/


# 功能点
删除Message Visibility Window特性以适应端口扫描，指纹扫描时间长的特性