# <译> Scala 类型的类型（二）

***

## 上一篇

[Scala 类型的类型（一）](http://yison.me/page/scala-types-of-types/part-1)

## 目录

- [6. 一个 ``object`` 的类型]()
- [7. Scala 中的型变]()
- [8. Refined Types (refinements)]()
- [9. Package Object]()
- [10. Type Alias]()

## 6. 一个 ``object`` 的类型

Scala 的 ``object`` 是通过 ``class`` 实现的（显然后者是 JVM 的基础构件）。然而你也会发现我们并不能像一个简单的类一样，轻松地获得一个 ``object`` 的类型……

我常常疑惑该如何传一个 ``object`` 给一个方法，对此我自己也非常惊讶。我的意思是指 ``obj: ExampleObj`` 是无效的，因为这种情况 ``ExampleObj`` 已经指向了实例，所以它有个 ``type`` 的成员，我们可以靠它解决问题。

下面的代码解释了大概的方法：
```scala
object ExampleObj

def takeAnObject(obj: ExampleObj.type) = {}

takeAnObject(ExampleObj)
```

## 7. Scala 中的型变

型变，通常可以解释成类型之间依靠彼此的「兼容性」，形成一种继承的关系。最常见的例子就是当你要处理「容器」或「函数」的时候，有时就必须要处理型变（极其的常见！）。

Scala 跟 Java 一个重大的差异，就是它的「容器类型」默认是不可变的！也就是说，如果你有一个定义为 ``Box[A]`` 的容器，然后在使用的时候将其中的类型参数 ``A`` 替换成 ``Fruit``，之后你就不能插入类型 ``Apple``（这也是一种 ``Fruit`` 类型）。

Scala 中的型变通过在「类型参数」前使用 ``+`` 和 ``-`` 符合来定义。

参见：[http://www.slideshare.net/dgalichet/demystifying-scala-type-system](http://www.slideshare.net/dgalichet/demystifying-scala-type-system)。







