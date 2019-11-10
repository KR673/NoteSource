---
tags: "tags"
---

[toc]

 
## 泛型
 
### 1. 定义

![](https://mynoteimg.oss-cn-beijing.aliyuncs.com/20191110012222.png)

> 泛型的本质是参数化类型,也就是说所操作的**数据类型被指定为一个参数**
 
泛型类型的确定是在类对象创建的时候确定的
 
### 2. 方法中的使用
 
在方法中的使用格式:
```java
权限修饰符 <无意义的泛型占位符> 返回值类型[可以使用自定义类型] 方法名(参数列表[可使用自定义泛型类型]) {
    //同样可以使用自定义泛型
    方法体
}
 
例如:
 
public static <E> void test(E a) {
    System.out.println(a);
}
```
> 占位符通常使用 E T K(key) V(value)
 
java是一个完全面对对象的语言, 在java中 , 8大数据类型也有与之对应的类对象,这个类对象称之为包装类
 
```java
Integer -> int
Byte -> byte
Long -> long
Short -> short
 
Double -> double
Float -> float
 
Boolean -> boolean
 
Character -> char
```
 
### 创建类对象
 
```java
//标准格式
ArrayList<String> list = new ArrayList<String>();
 
或: //为满足不同的版本和不同的编写工具
ArrayList list = new ArrayList<String>();
ArrayList<String> list = new ArrayList();
```
 
### 类内使用泛型
 
```java
class 类名<自定义泛型占位符> {
    //类内的普通成员变量和普通成员方法都可以使用和类名声明一致的泛型占位符
}
```
 
可以把尖括号中的 **自定义泛型占位符** 当作是一个 **变量类型** 来使用
 
**注意事项；**
 
1. 一个类声明了自定义的泛型，如果在创建当前类对象时，约束了泛型的具体类型，那么在类内的所有
非静态成员方法和非静态成员方法使用到泛型的位置，数据类型都会具体类型。如果在创建当前类对象时
没有约束数据类型，所有用到泛型的位置都是Object类型
 
2. 数组中如果数据类型为基本数据类型，那么当前数组是没有直接转换成对应包装类数组类型的能力。
因为，自动装箱和自动拆箱是针对单体数据的
 
1. 一个类声明的自定义泛型，不能在类内的静态方法中使用。【没有对象】
 
2. 类内的静态方法可以自己声明泛型。
 
5.使用不同的占位符保证阅读性
 
### 接口中使用泛型
 
```java
interface 接口名<自定义泛型的占位符> {
    //成员变量 缺省属性 public static final
    //成员方法 缺省属性 abstract
}
```
**注意:**
 
接口中的成员变量不能使用泛型.两方面的原因:
 
    final : 接口中的成员变量是使用final修饰的，定义时必须初始化，这里泛型的具体类型还没有被约束的条件下，无法进行对应数据类型的初始化
 
    static : 接口中的成员变量是使用static修饰的，而static修饰的成员变量是在类文件加载时已经存在于内存的【数据区】。而接口的泛型具体数据类型是随着类对象的创建为确定，时间不符。
 
#### 遵从自定义泛型接口的两种方式:
 
```java
第一种:
//没有确定泛型的具体类型,由调用者决定
class Test1<G> implements A<G> {
    @Override
    public void testA(G g){
 
    }
}
 
第二种:
//泛型的具体类型已经确定,比较常用
class Test2 implement A<String> {
    @Override
    public void testA(string g) {
 
    }
}
```
### 泛型的上下限
 
`<? extends T> `**上限**
表示该通配符所代表的类型是T类型的子类
 
`<? super T> `**下限**
表示该通配符所代表的类型是T类型的父类
 
**类型通配符**一般是使用` ? `代替具体的类型参数. 例如:
 
`List<?>` 在逻辑上是`List<String>, List<Integer>` 等所有`List<具体类型实参>`的父类
 
对集合中的数据的类型进行限制 // ? 好像是 ??
 
### Map
 
**键值对**
 
键 : 唯一不可重复
值 : 可以重复
 
一个键对一个值
 
声明格式:
 
```java
Map<K, V> map = new Hashmap<K, V>;
其中的K 和 V 表示数据类型
```
[java 泛型详解-绝对是对泛型方法讲解最详细的，没有之一](https://blog.csdn.net/s10461/article/details/53941091)
