## Contents

- [this指针](#this指针)
- [c++多态通过虚函数实现](#c++多态通过虚函数实现)
- [容器](#容器)
- [数据类型](#数据类型)

## this指针
类中this指针，指向类本身；成员函数的形参与成员变量名字相同时使用this。

this只能在成员函数内使用，且是const的。
> this->name = name 	// name是成员函数形参；this->name是类的成员变量。

## c++多态通过虚函数实现

纯虚函数：在基类中只定义不实现；在派生类中实现。包含纯虚函数的类不能定义对象

引入纯虚函数原因：
1. 更方便的使用多态
2. 很多情况下，基类中生成对象并不合理
包含纯虚函数的类称为抽象类。

## 容器
序列容器：元素在容器中的位置同元素的值无关（vector/list/deque）

排序容器：元素在容器中默认由小到大排列（set/multiset/map/multimap）

哈希容器：c++11引入的，元素的位置由哈希函数确定

正向迭代器：执行++操作，迭代器会指向容器的下一个元素
1. 容器类名::iterator 迭代器名 正向迭代器（可修改指向的元素）
2. 容器类名::const_iterator 迭代器名 常量正向迭代器（不可修改指向的元素）

反向迭代器：执行++操作，迭代器会指向容器的上一个元素
1. 容器类名::reverse_iterator 迭代器名 反向向迭代器（可修改指向的元素）
2. 容器类名::const_reverse_iterator 迭代器名 常量反向向迭代器（不可修改指向的元素）

vector容器特点
1. 初始化时自动分配一段连续的内存存储数据（自定义/default）
2. 存储数据超过内存大小，重新分配内存（非常耗时）
> 重新分配空间时的操作：<br>
> 1. vector会申请一块更大的内存块
> 2. 将原来的数据拷贝到新的内存块中
> 3. 销毁掉原内存块中的对象（调用对象的析构函数）
> 4. 将原来的内存空间释放掉

list容器特点
1. 双向量表
2. 序列容器

map和unordered_map
1. 相同点：两者都存储key-value对。
2. 不同点：unorder_map内部无序，通过key的hash-value判断值是否一样；而map内部元素从小到大，按红黑树排序。
3. 结论：如果需要内部元素按key大小自动排序用map，否则用unordered_map。
4. 基本用法：unorder_map<int, int> name, 查找时间复杂度为O(1);map<int, int> name。

stack容器
1. 线性表，插入和删除只在栈顶进行。

## 数据类型

string类
1. string str：声明一个名为str的string类变量。
2. string类主要用于处理字符串，有点类似与数组的结构，str[2]表示索引为2的字符。
3. 使用c_str()方法，可转换为const char*，注意const声明：const char* ptr = str.c_str();
```cpp
string s1 = "hello";
string s2 = "world";
s1 += s2; // output "hello world"
s1.append(s2); // output "hello world"
s[1];   // output 'e'
s1 += "world"; // output "hello world"
s1 += 'c';  // output "helloc"
```

new关键字
```cpp
// 32/64位系统中，所有类型的指针都是4/8字节大小。

class new_function{
public:
    new_function(){
        cout << "CLASS new_function() construction" << endl;
    }

    ~new_function(){
        cout << "CLASS new_function() deconstruction" << endl;
    }
};

int* arr = new int[5];                      // new int[5] 只分配了空间
cout << sizeof(*(arr+1)) << endl;           // output: 4
new_function *NEW = new new_function();     // new new_function()不仅为对象NEW分配了空间，还调用了构造函数
                                            // new A() 这样方式的功能如下:
                                            //      在堆上分配空间
                                            //      在分配的空间上调用对象的构造函数
                                            //      （这也是 new 和 malloc的主要区别，是否调用构造函数）
delete []arr;
delete NEW;                                 //  调用析构函数，然后删除对象空间
```