# 基础概念
- 什么是CoroutineScope

    CoroutineScope定义了协程的生命周期范围，确保协程的结构化并发。
    ```kotlin
        //创建CoroutineScope
        val scope = CoroutineScope(Dispatchers.Main+Job())
        //启动协程
        scope.launch{
            //协程体
        }

- 结构化并发核心思想
  - 父协程负责子协程的生命周期
  - 取消父协程会自动取消所有子协程
  - 子协程异常会传播到父协程
# 内置CoroutineScope
- GlobalScope(慎用)
  ```kotlin
    //应用级Scope,生命周期与应用相同
    Global.launch{
        //谨慎使用:可能造成内存泄漏
        
    }
- ViewModelScope ViewModel销毁时自动取消
- LifecycleScope 生命周期感知的协程
# 自定义CoroutineScope
- 基本创建方式
    ```kotlin
        private val customScope =CoroutineScope(Dispatchers.IO + SupervisorJob())
# 最佳实践
- Scope选择指南
  - UI组件：使用lifecycleScope或viewModelScope
  - 业务逻辑：创建自定义Scope
  - 全局任务：谨慎使用GlobalScope
