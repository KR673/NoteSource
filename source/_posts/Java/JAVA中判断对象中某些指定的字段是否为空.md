---
title: JAVA中判断对象中某些指定的字段是否为空
tags: java
categories:
  - Java
date: 2019-11-26 23:47:01
---

[toc]

> 可以使用 自定义注解 + 反射来实现, 这样可以为不同的字段添加不同的注解以分类判断

## 1. 自定义注解

```java
/**
 * 字段、枚举的常量
 */
@Target(ElementType.FIELD)

/**
 * 注解会在class字节码文件中存在，在运行时可以通过反射获取到
 */
@Retention(RetentionPolicy.RUNTIME)
public @interface TypeOne {
}
```

## 2. 测试对象

```java
@Data
public class ParamTest {

    @TypeOne
    private String name = "testName";

    @TypeOne
    private Integer age;
}
```

## 3. 判断方法

```java
public static boolean fieldIncludeNull(Object trueParam, Class<? extends Annotation> anno) throws Exception {

    Field[] declaredFields = trueParam.getClass().getDeclaredFields();
    for (Field fields : declaredFields) {
        fields.setAccessible(true);

        // 判断字段是否有对应注解
        if(fields.getAnnotation(anno) != null) {
            // 判断字段值是否为null
            if(Objects.equals(fields.get(trueParam), null)) {
                return true;
            }
        }
    }
    return false;
}
```

## 调用

```java
Boolean result = fieldIncludeNull(paramTest,TypeOne.class);
```
`result => true`

> 返回true, 说明加上这个注解的字段存在null值