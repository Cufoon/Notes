---
title: "C++ vector"
date: 2019-07-05T15:47:50+08:00
draft: false
tags: ["C++"]
---

## vector

#### 向量 相当于一个数组

在内存中分配一块连续的内存空间进行存储。支持不指定vector大小的存储。STL内部实现时，首先分配一个非常大的内存空间预备进行存储，即capacituy（）函数返回的大小，当超过此分配的空间时再整体重新放分配一块内存存储，这给人以vector可以不指定vector即一个连续内存的大小的感觉。通常此默认的内存分配能完成大部分情况下的存储。
**优点**：

- 不指定一块内存大小的数组的连续存储，即可以像数组一样操作，但可以对此数组进行动态操作。通常体现在push_back() pop_back()
- 随机访问方便，即支持[ ]操作符和vector.at()
- 节省空间。

**缺点**: 

- 在内部进行插入删除操作效率低。
- 只能在vector的最后进行push和pop，不能在vector的头进行push和pop。
- 当动态添加的数据超过vector默认分配的大小时要进行整体的重新分配、拷贝与释
  放 

### C++STL中vector容器的用法

**vector是C++标准模板库**

`#include <vector>`

vector属于std命名域的，因此需要通过命名限定，如下完成你的代码：

```c++
using std::vector;
vector<int> v;
```

或者连在一起，使用全名：

`std::vector<int> v;`

建议使用全局的命名域方式：

`using namespace std;`

vector的声明

| 示例        | 含义                                                        |
| :-------------------------- | :---------------------------------------------------------- |
| vector<ElemType> c;         | 创建一个空的vector                                          |
| vector<ElemType> c1(c2);    | 创建一个vector c1，并用c2去初始化c1                         |
| vector<ElemType> c(n) ;     | 创建一个含有n个ElemType类型数据的vector;                    |
| vector<ElemType> c(n,elem); | 创建一个含有n个ElemType类型数据的vector,并全部初始化为elem; |
| c.~vector<ElemType> ();     | 销毁所有数据,释放资源;                                      |

vector容器中常用的函数。(c为一个容器对象）

| 语法                   | 含义                                                         |
| ---------------------- | ------------------------------------------------------------ |
| c.push_back(elem);     | 在容器最后位置添加一个元素elem                               |
| c.pop_back();          | 删除容器最后位置处的元素                                     |
| c.at(index);           | 返回指定index位置处的元素                                    |
| c.begin();             | 返回指向容器最开始位置数据的指针                             |
| c.end();               | 返回指向容器最后一个数据单元的指针+1                         |
| c.front();             | 返回容器最开始单元数据的引用                                 |
| c.back();              | 返回容器最后一个数据的引用                                   |
| c.max_size();          | 返回容器的最大容量                                           |
| c.size();              | 返回当前容器中实际存放元素的个数                             |
| c.capacity();          | 同c.size()                                                   |
| c.resize();            | 重新设置vector的容量                                         |
| c.reserve();           | 同c.resize()                                                 |
| c.erase(p);            | 删除指针p指向位置的数据，返回下指向下一个数据位置的指针（迭代器） |
| c.erase(begin,end);    | 删除begin,end区间的数据，返回指向下一个数据位置的指针（迭代器） |
| c.clear();             | 清除所有数据                                                 |
| c.rbegin();            | 将vector反转后的开始指针返回(其实就是原来的end-1)            |
| c.rend();              | 将vector反转后的结束指针返回(其实就是原来的begin-1)          |
| c.empty();             | 判断容器是否为空，若为空返回true，否则返回false              |
| c1.swap(c2);           | 交换两个容器中的数据                                         |
| c.insert(p,elem);      | 在指针p指向的位置插入数据elem,返回指向elem位置的指针         |
| c.insert(p,n,elem);    | 在位置p插入n个elem数据，无返回值                             |
| c.insert(p,begin,end); | 在位置p插入在区间[begin,end)的数据，无返回值                 |

vector中的操作

- operator[] 如： c.[i]; 同at()函数的作用相同，即取容器中的数据。
  在上大致讲述了vector类中所含有的函数和操作，下面继续讨论如何使用vector容器；

1. 数据的输入和删除。push_back（）与pop_back（）
<left>![img](http://img.blog.163.com/photo/mILCTA6BMgOpdFJzIsdzyg==/5747719024432020726.jpg)

2. 元素的访问
<left>![img](http://img.blog.163.com/photo/3O_yi8sdiv40ND4gs2Rb0Q==/5747719024432020727.jpg)

3. 排序和查询
<left>![img](http://img.blog.163.com/photo/pjGEu-MvlXq-V4QWSCYRgA==/5747719024432020728.jpg)