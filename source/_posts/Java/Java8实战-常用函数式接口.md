---
title: Java8实战-常用函数式接口
date: 2019-12-20 01:16:23
tags: java
---

[toc]

![](https://mynoteimg.oss-cn-beijing.aliyuncs.com/20191220011454.png)
![](https://mynoteimg.oss-cn-beijing.aliyuncs.com/20191220011514.png)

## 1. Predicate(谓语)

`java.util.function.Predicate<T>`接口定义了一个名叫test的抽象方法，它**接受泛型T对象**，并**返回一个boolean**, 适合于需要根据多种不同的判断条件获取不同值的情况

```java
public static <T> void judgeString(String param,Predicate<T> judge){
    if(judge.test(param)){
        System.out.print(param)
    }
}
// "aa"
judgeString("aa", t -> Ojbects.equals(t , "aa"))
```

## 2. Consumer

`java.util.function.Consumer<T>`定义了一个名叫accept的抽象方法，它接受泛型T的对象，没有返回（void),如果需要访问类型T的对象，并对其执行某些操作，就可以使用这个接口

## 3. Function

`java.util.function.Function<T, R>`接口定义了一个叫作apply的方法，它接受一个 泛型T的对象，并返回一个泛型R的对象. 。如果你需要定义一个Lambda，将输入对象的信息映射到输出，就可以使用这个接口

```java
Class Uses{
    private Strng name;
    private Integer age;
}

public static <T, R> List<R> getList(List<T> param, Function<T, R> f){
        return param.stream()
                .map(f)
                .collect(Collectors.toList());
}

// 获取list中Uses对应的名字属性, 并转为一个新的列表
List<Users> param;
getList(param, Param::getName())

```