RocketMQ主要存储的文件：
1.Commitlog：消息存储文件，所有主题的消息都存储在这个文件中
2.ConsumeQueue：消息消费队列，消息到达Commitlog文件后，异步转发到消息消费队列，供消费者消费消息
3.IndexFile：消息索引文件，主要存储消息key与offset的对应关系
4.事务状态消息：存储每条消息的事务状态
5.定时消息服务：每一个延迟级别对应一个消息消费队列，存储延迟队列的消息拉取进度

消息存储实现类：org.apache.rocketmq.store.DefaultMessageStore