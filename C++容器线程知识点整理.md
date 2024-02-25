## #include `<string>`
### 构造器
* `string();`          				      //创建一个空的字符串 例如: string str;
  `string(const char* s);`	               //使用字符串s初始化
  `string(const string& str);`               //使用一个string对象初始化另一个string对象
* `string(int n, char c);`                   //使用n个字符c初始化 
### 赋值
* `string& assign(const char *s);`           //把字符串s赋给当前的字符串
* `string& assign(const char *s, int n);`    //把字符串s的前n个字符赋给当前的字符串
* `string& assign(const string &s);`         //把字符串s赋给当前字符串
* `string& assign(int n, char c);`           //用n个字符c赋给当前字符串
### 拼接
* `string& operator+=(const char* str);`             //重载+=操作符
* `string& operator+=(const char c);`                //重载+=操作符
* `string& operator+=(const string& str);`           //重载+=操作符
* `string& append(const char *s); `                  //把字符串s连接到当前字符串结尾
* `string& append(const char *s, int n);`            //把字符串s的前n个字符连接到当前字符串结尾
* `string& append(const string &s);`                 //同operator+=(const string& str)
* `string& append(const string &s, int pos, int n);` //字符串s中从pos开始的n个字符连接到字符串结尾
### 查找和替换
* `int find(const string& str, int pos = 0) const;`        //查找str第一次出现位置,从pos开始查找
* `int find(const char* s, int pos = 0) const; `           //查找s第一次出现位置,从pos开始查找
* `int find(const char* s, int pos, int n) const; `        //从pos位置查找s的前n个字符第一次位置
* `int find(const char c, int pos = 0) const; `            //查找字符c第一次出现位置
* `int rfind(const string& str, int pos = npos) const;`    //查找str最后一次位置,从pos开始查找
* `int rfind(const char* s, int pos = npos) const;`        //查找s最后一次出现位置,从pos开始查找
* `int rfind(const char* s, int pos, int n) const;`        //从pos查找s的前n个字符最后一次位置
* `int rfind(const char c, int pos = 0) const;  `          //查找字符c最后一次出现位置
* `string& replace(int pos, int n, const string& str); `   //替换从pos开始n个字符为字符串str
* `string& replace(int pos, int n,const char* s); `        //替换从pos开始的n个字符为字符串s
### 比较
* `int compare(const string &s) const; `   //与字符串s比较
* `int compare(const char *s) const;`      //与字符串s比较
### 单个字符存取
* `char& operator[](int n); `       //通过[]方式取字符
* `char& at(int n);   `             //通过at方法获取字符
### 插入和删除
* `string& insert(int pos, const char* s);  `           //插入字符串
* `string& insert(int pos, const string& str); `        //插入字符串
* `string& insert(int pos, int n, char c);`             //在指定位置插入n个字符c
* `string& erase(int pos, int n = npos);`               //删除从Pos开始的n个字符 
### string子串
* `string substr(int pos = 0, int n = npos) const;`     //返回由pos开始的n个字符组成的字符串

## #include `<vector>`    // 类似于数组
### 构造器
* `vector<T> v; `               		     //采用模板实现类实现，默认构造函数
* `vector(v.begin(), v.end());   `       //将v[begin(), end())区间中的元素拷贝给本身。
* `vector(n, elem);`                     //构造函数将n个elem拷贝给本身。
* `vector(const vector &vec);`           //拷贝构造函数。
### 赋值
* `vector& operator=(const vector &vec);`  //重载等号操作符
* `assign(beg, end);`       //将[beg, end)区间中的数据拷贝赋值给本身。
* `assign(n, elem);`        //将n个elem拷贝赋值给本身。
### 容量和大小
* `empty(); `               //判断容器是否为空
* `capacity();`             //容器的容量
* `size();`                 //返回容器中元素的个数
* `resize(int num);`        //重新指定容器的长度为num，若容器变长，则以默认值填充新位置。如果容器变短，则末尾超出容器长度的元素被删除。
* `resize(int num, elem);`  //重新指定容器的长度为num，若容器变长，则以elem值填充新位置。如果容器变短，则末尾超出容器长度的元素被删除
### 插入和删除
* `push_back(ele);`                                 //尾部插入元素ele
* `pop_back();`                                     //删除最后一个元素
* `insert(const_iterator pos, ele);`                //迭代器指向位置pos插入元素ele
* `insert(const_iterator pos, int count,ele);`      //迭代器指向位置pos插入count个元素ele
* `erase(const_iterator pos);`                      //删除迭代器指向的元素
* `erase(const_iterator start, const_iterator end);`//删除迭代器从start到end之间的元素
* `clear();`                                        //删除容器中所有元素
### 数据存取
* `at(int idx); `       //返回索引idx所指的数据
* `operator[]; `        //返回索引idx所指的数据
* `front(); `           //返回容器中第一个数据元素
* `back();`             //返回容器中最后一个数据元素
### vector互换容器
* `swap(vec);`          // 将vec与本身的元素互换
### vector预留空间
* `reserve(int len);`   //容器预留len个元素长度，预留位置不初始化，元素不可访问。

## #include `<deque>`        //双端数组
### 构造器
* `deque<T>` deqT;                  //默认构造形式
* `deque(beg, end);`                //构造函数将[beg, end)区间中的元素拷贝给本身。
* `deque(n, elem);`                 //构造函数将n个elem拷贝给本身。
* `deque(const deque &deq);`        //拷贝构造函数
### 赋值
* `deque& operator=(const deque &deq); `         //重载等号操作符
* `assign(beg, end);`                            //将[beg, end)区间中的数据拷贝赋值给本身。
* `assign(n, elem);`                             //将n个elem拷贝赋值给本身。
### 大小操作
* `deque.empty();`                    //判断容器是否为空
* `deque.size();`                     //返回容器中元素的个数
* `deque.resize(num);`                //重新指定容器的长度为num,若容器变长，则以默认值填充新位置。如果容器变短，则末尾超出容器长度的元素被删除。
* `deque.resize(num, elem);`          //重新指定容器的长度为num,若容器变长，则以elem值填充新位置。如果容器变短，则末尾超出容器长度的元素被删除。
### 插入和删除
两端插入操作：
- `push_back(elem);`          //在容器尾部添加一个数据
- `push_front(elem);`         //在容器头部插入一个数据
- `pop_back();`               //删除容器最后一个数据
- `pop_front();`              //删除容器第一个数据
指定位置操作：
* `insert(pos,elem);`       //在pos位置插入一个elem元素的拷贝，返回新数据的位置。
* `insert(pos,n,elem);`     //在pos位置插入n个elem数据，无返回值。
* `insert(pos,beg,end);`    //在pos位置插入[beg,end)区间的数据，无返回值。
* `clear();`                //清空容器的所有数据
* `erase(beg,end);`         //删除[beg,end)区间的数据，返回下一个数据的位置。
* `erase(pos);`             //删除pos位置的数据，返回下一个数据的位置。
### 数据存取
- `at(int idx); `           //返回索引idx所指的数据
- `operator[]; `            //返回索引idx所指的数据
- `front(); `               //返回容器中第一个数据元素
- `back();`                 //返回容器中最后一个数据元素
### 排序
* `sort(iterator beg, iterator end)`  //对beg和end区间内元素进行排序 例：sort(d.begin(), d.end());

## #include `<stack>`     // 栈 先进后出

### 构造函数
* `stack<T> stk;`                       //stack采用模板类实现， stack对象的默认构造形式
* `stack(const stack &stk);`            //拷贝构造函数
### 赋值操作：
* `stack& operator=(const stack &stk);`        //重载等号操作符
### 数据存取：
* `push(elem);`          //向栈顶添加元素
* `pop();`               //从栈顶移除第一个元素
* `top(); `              //返回栈顶元素
### 大小操作：
* `empty();`             //判断堆栈是否为空
* `size(); `             //返回栈的大小

## #include `<queue>`     //队列   先进先出
### 构造函数：
- `queue<T> que;`                        //queue采用模板类实现，queue对象的默认构造形式
- `queue(const queue &que);`             //拷贝构造函数
### 赋值操作：
- `queue& operator=(const queue &que);`  //重载等号操作符
### 数据存取：
- `push(elem);`                          //往队尾添加元素
- `pop();`                               //从队头移除第一个元素
- `back();`                              //返回最后一个元素
- `front(); `                            //返回第一个元素
### 大小操作：
- `empty();`             //判断堆栈是否为空
- `size(); `              //返回栈的大小

## #include `<list>`           // 链表是一种物理存储单元上非连续的存储结构，数据元素的逻辑顺序是通过链表中的指针链接实现的
### 构造函数
* `list<T> lst;`                       //list采用采用模板类实现,对象的默认构造形式：
* `list(beg,end);`                     //构造函数将[beg, end)区间中的元素拷贝给本身。
* `list(n,elem);`                      //构造函数将n个elem拷贝给本身。
* `list(const list &lst);`             //拷贝构造函数。
### 赋值和交换
* `assign(beg, end);`                  //将[beg, end)区间中的数据拷贝赋值给本身。
* `assign(n, elem);`                   //将n个elem拷贝赋值给本身。
* `list& operator=(const list &lst);`  //重载等号操作符
* `swap(lst);`                         //将lst与本身的元素互换。
### 大小操作
* `size(); `                  //返回容器中元素的个数
* `empty(); `                 //判断容器是否为空
* `resize(num);`              //重新指定容器的长度为num，若容器变长，则以默认值填充新位置。如果容器变短，则末尾超出容器长度的元素被删除。
* `resize(num, elem); `       //重新指定容器的长度为num，若容器变长，则以elem值填充新位置。如果容器变短，则末尾超出容器长度的元素被删除。
### 插入和删除
* `push_back(elem);`          //在容器尾部加入一个元素
* `pop_back();`               //删除容器中最后一个元素
* `push_front(elem);`         //在容器开头插入一个元素
* `pop_front();`              //从容器开头移除第一个元素
* `insert(pos,elem);`         //在pos位置插elem元素的拷贝，返回新数据的位置。
* `insert(pos,n,elem);`       //在pos位置插入n个elem数据，无返回值。
* `insert(pos,beg,end);`      //在pos位置插入[beg,end)区间的数据，无返回值。
* `clear();`                  //移除容器的所有数据
* `erase(beg,end);`           //删除[beg,end)区间的数据，返回下一个数据的位置。
* `erase(pos);`               //删除pos位置的数据，返回下一个数据的位置。
* `remove(elem);`             //删除容器中所有与elem值匹配的元素。
### 数据存取
* `front();`        //返回第一个元素。
* `back();`         //返回最后一个元素。
### 反转和排序
* `reverse();`      //反转链表
* `sort(排序规则);`  //链表排序 

  ```c++
  例如：
  bool myCompare(int val1 , int val2)
  {
  return val1 > val2;
  }
  list<int> L;
  L.sort(myCompare); //指定规则，从大到小
  ```

  

## #include `<set>`     //set/multiset属于关联式容器，底层结构是用`二叉树`实现，所有元素都会在`插入时自动被排序`
**set和multiset区别**：
* set不允许容器中有重复的元素
* multiset允许容器中有重复的元素
### 构造器
* `set<T> st;`                      //默认构造函数：
* `set(const set &st);`             //拷贝构造函数
### 赋值
* `set& operator=(const set &st);`  //重载等号操作符
### 大小和交换
* `size();`                         //返回容器中元素的数目
* `empty();`                        //判断容器是否为空
* `swap(st);`                       //交换两个集合容器
### 插入和删除
* `insert(elem);`                   //在容器中插入元素。
* `clear();`                        //清除所有元素
* `erase(pos);`                     //删除pos迭代器所指的元素，返回下一个元素的迭代器。
* `erase(beg, end);`                //删除区间[beg,end)的所有元素 ，返回下一个元素的迭代器。
* `erase(elem);`                    //删除容器中值为elem的元素。
### 查找和统计
* `find(key);`     //查找key是否存在,若存在，返回该键的元素的迭代器；若不存在，返回set.end();
* `count(key);`    //统计key的元素个数 （对于set，结果为0或者1）
例：set<int>::iterator pos = s1.find(30);
### pair对组创建     //成对出现的数据，利用对组可以返回两个数据
* `pair<type, type> p ( value1, value2 );`
* `pair<type, type> p = make_pair( value1, value2 );`
	例：
	pair<string, int> p(string("Tom"), 20);
	cout << "姓名： " <<  p.first << " 年龄： " << p.second << endl;
### 排序     // set容器默认排序规则为从小到大，利用`仿函数`，可以改变排序规则
```c++
例：
class MyCompare 
{
public:
	bool operator()(int v1, int v2) {
		return v1 > v2;
	}
};
set<int,MyCompare> s2;    // `对于自定义数据类型，set必须指定排序规则才可以插入数据`
```



## #include `<map>`    //map/multimap属于关联式容器，底层结构是用`二叉树`实现，所有元素都会根据元素的键值自动排序
map和multimap区别：
- map不允许容器中有重复key值元素
- multimap允许容器中有重复key值元素

### 构造
* `map<T1, T2> mp;`                 //map默认构造函数: 
* `map(const map &mp);`             //拷贝构造函数
### 赋值
* `map& operator=(const map &mp);`  //重载等号操作符
### 大小和交换
- `size();`          //返回容器中元素的数目
- `empty();`         //判断容器是否为空
- `swap(st);`        //交换两个集合容器
### 插入和删除
- `insert(elem);`    //在容器中插入元素。
- `clear();`         //清除所有元素
- `erase(pos);`      //删除pos迭代器所指的元素，返回下一个元素的迭代器。
- `erase(beg, end);` //删除区间[beg,end)的所有元素 ，返回下一个元素的迭代器。
- `erase(key);`      //删除容器中值为key的元素。

	```C++
	例：
	//插入
	map<int, int> m;
	//第一种插入方式
	m.insert(pair<int, int>(1, 10));
	//第二种插入方式
	m.insert(make_pair(2, 20));
	//第三种插入方式
	m.insert(map<int, int>::value_type(3, 30));
	//第四种插入方式
	m[4] = 40; 
	```
### 查找和统计
- `find(key);`     //查找key是否存在,若存在，返回该键的元素的迭代器；若不存在，返回map.end();
- `count(key);`    //统计key的元素个数 对于map，结果为0或者1
### 排序   // map容器默认排序规则为 按照key值进行 从小到大排序，`利用仿函数，可以改变排序规则`
```C++
例：
class MyCompare {
public:
	bool operator()(int v1, int v2) {
		return v1 > v2;
	}
};
```

map<int, int, MyCompare> m;   // 对于自定义数据类型，map必须要指定排序规则

* 算法主要是由头文件`<algorithm>` `<functional>` `<numeric>`组成。
* `<algorithm>`是所有STL头文件中最大的一个，范围涉及到比较、 交换、查找、遍历操作、复制、修改等等
* `<numeric>`体积很小，只包括几个在序列上面进行简单数学运算的模板函数
* `<functional>`定义了一些模板类,用以声明函数对象。
### 遍历算法  for_each
* `for_each(iterator beg, iterator end, _func);  `
  // 遍历算法 遍历容器元素
  // beg 开始迭代器
  // end 结束迭代器
  // _func 函数或者函数对象

  ```C++
  例：
  //普通函数
	void print01(int val) 
  {
  cout << val << " ";
  }
  //函数对象
  class print02 
	{
	 public:
	void operator()(int val) 
	{
  	cout << val << " ";
  }
  };
  for_each(v.begin(), v.end(), print01);
  cout << endl;
  for_each(v.begin(), v.end(), print02());
  cout << endl;
  ```
### 排序算法 sort()
- `sort(iterator beg, iterator end, _Pred);  `
  // 按值查找元素，找到返回指定位置迭代器，找不到返回结束迭代器位置
  //  beg    开始迭代器
  //  end    结束迭代器
  // _Pred  谓词   //  不填的情况下，sort默认从小到大排序

	```C++
	例：
	//从大到小排序
	sort(v.begin(), v.end(), greater<int>());   // greater<int>()为内建函数对象
	```

## #include `<memory>`   //所有的智能指针类（包括std::unique_ptr）均包含于此头文件中。
### unique_ptr
初始化
//初始化方式1
std::unique_ptr<int> sp1(new int(123));
//初始化方式2
std::unique_ptr<int> sp2;
sp2.reset(new int(123));
//初始化方式3 `推荐`
std::unique_ptr<int> sp3 = std::make_unique<int>(123);

### shared_ptr
**说明**：std::shared_ptr持有的资源可以在多个std::shared_ptr之间共享，每多一个std::shared_ptr对资源的引用，资源引用计数将增加1，每一个指向该资源的std::shared_ptr对象析构时，资源引用计数减1，最后一个std::shared_ptr对象析构时，发现资源计数为0，将释放其持有的资源。多个线程之间，递增和减少资源的引用计数是安全的。（注意：这不意味着多个线程同时操作std::shared_ptr引用的对象是安全的）。std::shared_ptr提供了一个use_count()方法来获取当前持有资源的引用计数。
**初始化**
//初始化方式1
std::shared_ptr<int> sp1(new int(123));
//初始化方式2
std::shared_ptr<int> sp2;
sp2.reset(new int(123));
//初始化方式3
std::shared_ptr<int> sp3;
sp3 = std::make_shared<int>(123);

### weak_ptr
**说明**：std::weak_ptr是一个不控制资源生命周期的智能指针，是对对象的一种弱引用，只是提供了对其管理的资源的一个访问手段，引入它的目的为协助std::shared_ptr工作。std::weak_ptr可以从一个std::shared_ptr或另一个std::weak_ptr对象构造，std::shared_ptr可以直接赋值给std::weak_ptr ，也可以通过std::weak_ptr的lock()函数来获得std::shared_ptr。它的构造和析构不会引起引用计数的增加或减少。std::weak_ptr可用来解决std::shared_ptr相互引用时的死锁问题，即两个std::shared_ptr相互引用，那么这两个指针的引用计数永远不可能下降为0， 资源永远不会释放。
**使用场景**
std::weak_ptr的正确使用场景是那些资源如果可用就使用，如果不可用则不使用的场景，它不参与资源的生命周期管理。
std::weak_ptr的应用场景，经典的例子是订阅者模式或者观察者模式中。这里以订阅者为例来说明，消息发布器只有在某个订阅者存在的情况下才会向其发布消息，而不能管理订阅者的生命周期。
**expired()和lock()方法**
std::weak_ptr不管理对象的生命周期，那么其引用的对象可能在某个时刻被销毁了，如何得知呢？std::weak_ptr提供了一个expired()方法来做这一项检测，返回true，说明其引用的资源已经不存在了；返回false，说明该资源仍然存在，这个时候可以使用std::weak_ptr 的lock()方法得到一个std::shared_ptr对象然后继续操作资源。

```c++
例如
//tmpConn_是一个std::weak_ptr<TcpConnection>对象
//tmpConn_引用的TcpConnection已经销毁，直接返回
if (tmpConn_.expired())
    return;

std::shared_ptr<TcpConnection> conn = tmpConn_.lock();
if (conn)
{
    //对conn进行操作，省略...
}
```

## #include `<thread>`   // C++11新标准引入了一个新的类std::thread

### 创建新线程
用法：

```C++
void threadproc1()
{
    while (true)
    {
        printf("I am New Thread 1!\n");
    }
}
//创建线程t1
std::thread t1(threadproc1);
```

### 获取线程id
std::thread t(worker_thread_func);
//获取线程t的ID
std::thread::id worker_thread_id = t.get_id();
//获取主线程的线程ID 可以用`this_thread`
std::thread::id main_thread_id = std::this_thread::get_id();

### 等待线程结束
例：
std::thread t(FileThreadFunc);
if (t.joinable())
  t.join();   // `join()函数可以使子线程打断主线程提前运行，但是对于多个子线程的join()，它们之间不是严格按照调用函数的前后顺序来执行的`

## std::mutex系列

**#include `<mutex>`          // 对应mutex**
**#include `<shared_mutex>`   // 对应shared_mutex**

说明：
C++ 11/14/17 中提供了如下 mutex 系列类型：
互斥量	              版本	           作用
`mutex`	            C++11	         最基本的互斥量
timed_mutex	        C++11	         有超时机制的互斥量
recursive_mutex	    C++11	         可重入的互斥量
recursive_timed_mutex  C++11	         结合 timed_mutex 和 recursive_mutex 特点的互斥量
shared_timed_mutex	 C++14	         具有超时机制的可共享互斥量
`shared_mutex`	     C++17	         共享的互斥量
std::shared_mutex 底层实现主要原理是操作系统提供的读写锁，也就是说，在存在多个线程对共享资源读、少许线程对共享资源写的情况下，std::shared_mutex 比 std::mutex 效率更高。

### 互斥量管理

**说明**
 互斥量管理	   版本	 作用
`lock_guard`	C++11	基于作用域的互斥量管理
`unique_lock`   C++11	更加灵活的互斥量管理
`shared_lock`   C++14	共享互斥量的管理
`scope_lock`	C++17	多互斥量避免死锁的管理

```c++
例
void func()
{
	std::lock_guard<std::mutex> guard(mymutex);
  std::shared_lock<std::shared_mutex> lock(mutex);
	//在这里放被保护的资源操作
}
```

## #include <condition_variable>   // std::condition_variable

**说明**

C++ 11 提供了 std::condition_variable 这个类代表条件变量，与 Linux 系统原生的条件变量一样，同时提供了等待条件变量满足的 wait 系列方法（wait、wait_for、wait_until 方法），发送条件信号使用 notify 方法（notify_one 和 notify_all 方法），`当然使用 std::condition_variable 对象时需要绑定一个 std::unique_lock 或 std::lock_guard 对象。`

```c++
例如
std::unique_lock<std::mutex> guard(mymutex);
std::condition_variable   mycv;
mycv.wait(guard);
mycv.notify_one();
```

## `thread_local` 关键字   // C++11 对应的头文件为 #include `<thread>`

**说明**

对于线程变量，每个线程都会有该变量的一个拷贝，并行不悖，互不干扰，该局部变量一直都在，直到线程退出为止。
系统的线程局部存储区域内存空间并不大，所以尽量不要利用这个空间存储大的数据块，如果不得不使用大的数据块，可以将大的数据块存储在堆内存中，再将该堆内存的地址指针存储在线程局部存储区域。

```c++
例如
thread_local int g_mydata = 1;
```

















  
