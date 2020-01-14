---
title: Java8实战-行为参数化
tags: java
categories:
  - Java
date: 2019-12-20 00:48:27
---
[toc]

## 1. 行为参数化

一言以蔽之, 就是将行为传传递给一个方法, 从而实现代码整体逻辑的复用, 使代码更加的简洁,灵活
> 有点类似于匿名内部类, 但比他更加的简洁, 易读

## 2. 实现

1. 需要一个函数式接口
2. 用Lambda表示的行为
3. 由这个接口作为一个参数 

将这个接口作为一个方法的参数时, 就可以传递由lambda表示的具体行为

### 2.1 函数式接口

就是只定义了**一个抽象方法**的接口(*就算有许多的默认方法, 只要中定义了一个抽象方法, 就仍是函数式接口*)
> 因为之后**相当于使用lambda表达式实现了这个方法**, 是不可以指定要实现哪个方法的, 如果一个接口中包含多个抽象方法就无法确定实现的是哪一个

对于函数式接口, 可以在接口上使用`@FunctionalInterface`注解, 目的是告诉编译器这是一个函数式接口, 如果此时接口中有多个抽象方法编译器就会报错

```java
// 函数式接口
@FunctionalInterface // 可不加
public interface FunctionInterface<T> {
    void test(T a);
}

// 调用
public static void main(String[] args) {
  //使用lambda实现接口FunctionInterface的test方法
  FunctionInterface functionInterface = a -> System.out.println(a);
  functionInterpret.test("aa");
}

```
`-> aa`

### 2.2 Lambda表达式

一种可以简洁的传递匿名函数的方式, 包含了 参数列表, 函数主体, 返回类型
主要语法为 : **(参数) -> 主体** 或 **(参数) -> {主体}**

![](https://mynoteimg.oss-cn-beijing.aliyuncs.com/20191220011408.png)