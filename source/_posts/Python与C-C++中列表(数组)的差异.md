title: Python与C/C++中列表(数组)的差异
author: 闰土
tags:
  - C
  - C++
  - Python
categories:
  - 杂码
date: 2023-03-18 22:31:00
---
做个整合吧（因为自己整的时候看着太离谱了..）  
<!--more-->
## **Python**
```python
# 传说中的Python!用了它之后感觉用哪种语言都是ntr
# 除了性能啊啊啊

# 创建
# 列表名 = [初始化元素]
List = []

# 初始化元素 元素类型无限制
List = [114514, "233", ["Another List"], True]

# 添加元素
# 列表名.append(元素)
List.append(233) # 注意一次只能添加一个

# 元素读取
# List[索引] # 支持负数索引
print(List[0])
```
## **C/C++**
请注意这里，C和C++称类似python的列表为数组。    
```c
#include <iostream>
// 这位更是速度的神

// 创建
// <数据类型> 数组名[元素个数] = {初始化元素};
int List[2];
// 需要注意的是 像这样的初始化会将其中的元素填充为对应数据类型的默认值
// 比如例子中的数组数据类型为int，则最终填充效果为{0, 0}。

// 初始化元素 类型需为定义类型
int List[2] = {114514, 233};

// 添加元素
// 事实上c并不能实现数组插入，只能用一种很硬核的方法
// 你可能在寻找：向量(vector)
int insertArray(int *a, int pos, int number){
    /*a ->          数组
    * pos ->      插入位置
    * number ->    插入数字 */
    int nN = sizeof(a) / sizeof(int);
    for(int i = nN - 1; i >= pos; i++){a[i + 1] = a[i];}
    a[pos] = number;
    return nN + 1;
}
// 当场手敲，有错误请指出x

// 元素读取 如上
std::cout << List[1];
```