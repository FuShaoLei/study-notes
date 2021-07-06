# Kotlin速成

kotlin中没有分号

kotlin中在后边进行类型的声明

## 函数

```kotlin
/**
 * main函数，同java一样，程序的入口
 * Unit表示返回值为空
 */
fun main():Unit{
    println("Hello Kotlin!")
}
// 带参数的函数
fun test(x:Int):Int{
    return x*2
}
```

## 变量

- var声明可变引用
- val声明不可变引用（相当于Java中加上final的变量）

```kotlin
// 可写成 var age = 18，系统会自动识别
var age: Int = 18
val NAME = "JulyPost"
// 创建对象直接如此，不需要new关键字了
var person = Person()
```

object修饰，所有的函数和成员属性都回变成静态的