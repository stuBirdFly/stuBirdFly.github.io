---
title: c++花括号
date: 2022-06-06 18:42:45
categories:
- c++
---

​	今天看代码的时候，发现有些地方的if判断删除了，但是花括号没有删除，不知道会不会影响到里面代码的执行，如：

```c++
class Dog
{
public:
    Dog();
    ~Dog();
};

Dog::Dog()
{
    cout<<"生成一条狗"<<endl;
}

Dog::~Dog()
{
    cout<<"毁灭一条狗"<<endl;
}

int main(int argc, char *args[])
{
    cout<<"hello world"<<endl;
    // if(a==b)
    {
    	Dog d; 
	}
    cout<<"hello run last"<<endl;
}
  
```

运行结果如下：

![image-20220606185543769](https://s2.loli.net/2022/06/06/iMdg6eamBAtH43C.png)

再去掉花括号：

```c++
class Dog
{
public:
    Dog();
    ~Dog();
};

Dog::Dog()
{
    cout<<"生成一条狗"<<endl;
}

Dog::~Dog()
{
    cout<<"毁灭一条狗"<<endl;
}

int main(int argc, char *args[])
{
    cout<<"hello world"<<endl;
    // if(a==b)
    
    Dog d; 
	
    cout<<"hello run last"<<endl;
}
```

运行结果如下：

![image-20220606185649437](https://s2.loli.net/2022/06/06/JEX2ROs3zHWnuwM.png)

## 结论

​	花括号内的代码是一定会执行的，但是在括号内创建的对象，会在执行完括号内的代码后进行析构。
