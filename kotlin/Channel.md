# Channel基础概念
Channel本质上是一个阻塞队列的协程版本，提供了协程间的安全通信机制。
```kotlin
    //基本使用
    val channel = Channel<Int>()
    launch {
        for (x in 1..5){
            channel.send(x*x)
        }
        channel.close() //重要 发送完成后关闭channel
    }
    launch {
        for(y in channel){
            print(y)
        }
    }
```
# Channel类型详解
## Rendezvous Channel（默认）
- 容量为0，发送和接收必须同时发生
- 无缓冲，最严格的同步
  ```kotlin
    val channel = Channel<String>()
  ```
## Buffered Channel
- 指定缓冲区大小
- 发送方可以在缓冲区未满时立即返回
  ```kotlin
    val bufferedChannel = Channel<Int>(10)
    ```
##  Conflated Channel
- 缓冲区大小为1，但新值会覆盖旧值
- 只保留最新的值
  ```kotlin
    val conflatedChannel = Channel<Int>(Channel.CONFLATED)