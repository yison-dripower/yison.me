# Scala 类型的类型

***

## 原文

[http://ktoso.github.io/scala-types-of-types/](http://ktoso.github.io/scala-types-of-types/)

## 翻译

### 1. Scala 类型的不同类型

2013 年在几场 「JavaOne 大会」之后，掀起了一些关于 「Scala 类型」方面的热议，这篇博文也应运而生。  

在这些讨论声中，我发现不同的人在学习 Scala 的过程中，经常重复提出相同的问题。虽然我们并不能穷举所有跟 Scala 类型打交道的妙招，但我依然决定总结自己已有的经验，分享下在 Scala 中为什么我们需要这些类型。

### 2. 写作进度

尽管我写这篇文章已经有段时间了，但始终还有很多内容未完成。比如说「高阶类型」部分需要重新梳理，「Self Type」还得补充更多细节，等等等等。详情参见「计划清单」。

此外，如果你看到某个部分被打上了 ❌ ，则表示该部分需要修改或者是未完成。

### 3. Type Ascription

Scala 有「类型推断」，这意味着我们可以在源码中省略一些「类型声明」。在不显式声明类型的前提下，我们只要书写 val 或 def 就够了。

这种显式表明类型的行为，被称为「Type Ascription」（有时候，也被叫做「Type Annotation」，但这个名字容易造成混淆，在 Scala 中并不采纳使用）。

```scala
trait Thing
def getThing = new Thing { }

// without Type Ascription, the type is infered to be `Thing`
val infered = getThing

// with Type Ascription
val thing: Thing = getThing
```

在此类情况下，我们可以不使用「Type Ascription」。当然你也可以针对每个公有的方法显示声明返回类型（这是非常好的习惯），这可以让代码可读性更好。

你可以根据以下的提示问题，来决定是否使用「Type Ascription」：

Q: 如果它是一个变量？
```
A: 必须使用。
```

Q: 如果它是一个公有方法的返回值？
```
A: 为了更好的代码可读性及控制输出类型，需要使用。
```

Q: 如果它是一个递归或重载的方法？
```
A: 必须使用。
```

Q: 当你需要返回一个比隐式推断结果更通用的接口？
```
A: 除非你愿意暴露实现细节，否则必须使用。
```

除上述情况之外，则可以不必显式声明类型。

补充提示：使用「Type Ascriptions」可以加快编译的速度，同时能看到一个方法的返回类型，通常也都是一件好事。

好了，我们现在明白了「Type Ascriptions」大概是怎么一回事。讲完这个之后，我们继续接下来的话题，类型随之也会变得越来越有趣。

### 4. 通用类型系统 — Any, AnyRef, AnyVal




