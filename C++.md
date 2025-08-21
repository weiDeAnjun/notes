# C++库

//动态数组vector

```c++
#include <vector>
//动态数组vector

	//初始化方式
int num = 10;//元素数

vector<int> nums;				// 初始化一个 int 型的空数组 nums
vector<int> arrOne(num);		//根据个数，默认初始值0
vector<int> arrTwo(num, 1);		//根据个数和默认值
vector<int> arrThree{1,2,3};	//根据值
//嵌套，n*n*n个值
vector<vector<vector<bool>>> arrFour(num, vector<vector<bool>>(num, vector<bool>(num, true)));






	//vector常用操作
.empty()	//判空
.size()		//返回大小
.push_back()//尾插
.pop_back() //尾删
.back()		//返回尾元素值
.insert()	//指定索引插入
.erase()	//删除指定索引元素值
.swap()		//交换指定索引元素值


```



//双链表

```c++
//双链表list
#include <list>
	//初始化方式	同vector

	
    //list常用操作
.back()			//返回尾元素值
.front()		//返回头元素值
.advance(旧位置，新位置)		//移动到指定索引
    
    
.empty()	//判空
.size()		//返回大小
.push_back()	//尾插
.push_front()	//头插
.pop_back()		//尾删
.pop_front()	//头删


    
```





//队列

```c++

#include <queue>

	//queue初始化方式	好像只能初始化空队列
	
	//queue相关操作
	c++中对queue的定义是尾插头删
    
.push()	//尾插
.pop()	//头删
.front()	//获取对头
.back()		//获取队尾
        
        
.empty()	//判空
.size()	//返回大小



```





//栈

```c++
#include <stack>

	//stack初始化方式	好像只能初始化空队列


	//stack操作
.pop	//删除栈顶
.top	//获取栈顶






```





//散列表

```c++
// unordered_map

	//初始化散列表
unordered_map<键类型, 键值类型> hashmap;
	
	//unordered_map操作方法
empty、size这些所有容器类的基础方法不写了
.contains()		//指定键是否存在
.first			//键名
.second			//键值

	//c++散列表遍历
for(const auto &pair : 散列表名){
	
    cout << pair.first << pair.second << endl;
}

```



//散列集合

常用于去重

散列表体现了散列思想

c++中散列集合我没直观感受到它体现了散列思想

它是个存储不重复元素的集合

```c++
// unordered_set	存储不重复元素










```













































