# Dart
## 1.基础语法
### 集合
- 样例
  - 有序集合
    ```dart
      List<String> names = ['Alice','Bob','Charlie']
  - 无序唯一集合
    ```dart
      Set<int> names = {'Alice','Bob','Charlie'}
  - map键值对集合
    ```dart
      Map<String,String> namesUser = {'Alice':'boy','Bob':'girl'}
- 🎯 集合的高阶函数
    - 转换操作
        ```dart
            List<int> numbers = [1, 2, 3, 4, 5];
            //map转换
            var new_numbers = numbers.map((x) => x*2).toList();
            //where过滤
            var new_numbers = numbers.where((x) => x%2 == 0).toList();
            //expand展开
            var new_numbers = numbers.expand((x) => [x,x*10]).toList();
    - 聚合操作
        ```dart
            List<int> numbers = [1, 2, 3, 4, 5];
            //redice累积计算
            var sum = numbers.reduce((value,element)=>value+element);
            //fold带初始值的累积
            var sum = numbers.fold(1,(value,element)=>value*element);
            //any、all条件查询
            var result = (numbers.any((x)=>x>3)); //返回true
            var result = (numbers.all((x)=>x>3)); //返回false
    - 排序和查找
        ```dart
            List<String> names = ['Charlie', 'Alice', 'Bob'];
            // 排序
            names.sort();
            print(names); // [Alice, Bob, Charlie]
            //自定义排序
            names.sort((a,b)=>a.length.compareTo(b.length)); //按照长度排序
            print(names); // [Bob, Alice, Charlie]
            //查找第一个满足条件的元素
            var firstLongName = names.firstWhere((name)=>name.length>4);


