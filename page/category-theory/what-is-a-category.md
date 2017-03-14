# 范畴 - 组合的本质

***

## Part 1.1

- [Category: The Essence of Composition](https://bartoszmilewski.com/2014/11/04/category-the-essence-of-composition/)
- [Category Theory 1.2: What is a category?](https://www.youtube.com/watch?v=p54Hd7AmVFU&index=2&list=PLbgaMIhjbmEnaH_LTkxLI7FMa2HsnawM_)

## 什么是范畴？

在 Milewski 看来，「范畴」是一个很简单的概念，但是如果要准确地解释清它是什么，似乎也不是一件容易的事。

### 简单理解：  
```
「一类对象」及「该类对象之间的箭头」构成了一个范畴。
```

- 范畴跟集合、关系都不是一个层面的概念，前者可以包含后两者；
- 范畴论中对象可以看成原子性的点，忽略内部细节，重点关注对象之间的箭头，即「态射」；
- 态射与态射之间是可组合的，如下图 A → C = A → B + B → C

![pig arrow](http://yison.me/assets/img/2017-03/pig-arrow.jpg)

（注意！此图并非一个完整的范畴，因为它没有单位态射，详见下文。）

### 精确定义：
```
一个完整的范畴包含：  

1. 一个由对象所构成的类；
2. 对象与对象之间的态射；
3. 对任三个对象，它们之间的态射复合需满足「结合律」；
4. 对任一对象，都存在「单位态射」。
```

有点迷？下面逐一解释。

## 类

类是造成「范畴」不容易被准确理解的原因之一。


- 组成范畴的一类对象并不一定就是「集合」。
- 「类」是为了解决「集合论」缺陷而创造的概念，参见「[罗素悖论](https://www.zhihu.com/question/28422649)」。
- 为了便于理解，一般情况下，可以近似认为「一个范畴包含一个集合」。


## 态射复合



## 复合的性质

在任何范畴中，复合必须满足两个非常重要的性质。

### 结合律

### 单位态射