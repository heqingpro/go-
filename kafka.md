### kafka

#### 1、原理

- **topic**
  - 生产者push 到topic，消费者从topic 拉数据
- **Partition** （分区）
  - 一个topic 会对应多个分区，消费者从分区取数据
  - partition分布于不同的broker 中
  - 分区在各个broker中做备份
  - 数据写到磁盘来持久化，通过 顺序访问IO和缓存(等到一定的量或时间)才真正把数据写到磁盘上，来提高速度
- **broker**
  - 一台kafka 就是一个broker
  - kafka集群就是多个broker
- **consumer** 消费者
  - 消费者组

- **offset**
  - 表示消费者消费进度，偏移量

- **Zookeeper**
  - 探测broker和consumer的添加或移除
  - 负责维护所有partition的领导者/从属者关系（主分区和备份分区），如果主分区挂了，需要选举出备份分区作为主分区。
  - 维护topic、partition等元配置信息