
# Week2 2

[3-Complexity_and_Challenges_in_Software-generated.pdf](assets/3-Complexity_and_Challenges_in_Software-generated-20230201090912-sct7st5.pdf) 2

主要讲了耦合什么是耦合,以及耦合的分类

有相关实验,来巩固耦合的知识Lab1

[维基百科,什么是耦合?](https://zh.wikipedia.org/wiki/%E8%80%A6%E5%90%88%E6%80%A7_(%E8%A8%88%E7%AE%97%E6%A9%9F%E7%A7%91%E5%AD%B8))

# The type of coupling

* Content Coupling 内容耦合
* Common Data Coupling  公共数据耦合
* Control Coupling 控制耦合
* Stamp Coupling 印记耦合
*  Data Coupling 数据耦合
*  Routine/Temporal Coupling 程序/时序耦合
* Interface Coupling 接口耦合

# Key concepts of coupling and cohesion

[耦合内聚](https://blog.csdn.net/kingscoming/article/details/78836229)

耦合与内聚的关键概念

内聚：每个模块尽可能独立完成自己的功能，不依赖于模块外部的代码。  
耦合：模块与模块之间接口的复杂程度，模块之间联系越复杂[耦合度](https://so.csdn.net/so/search?q=%E8%80%A6%E5%90%88%E5%BA%A6&spm=1001.2101.3001.7020)越高，牵一发而动全身

How components are built internally

How components are connected Both are about relationships between components/elements

‍

Internal details should not leak between components

 • If they do change becomes very difficult

内部细节不应该泄漏到组件之间，如果这样，变化变得非常困难。

这是一种软件开发设计原则，表示每个组件内部的细节应该保密，不能对其他组件造成影响。如果组件内部细节泄漏到其他组件，则任何对其内部细节的修改都可能导致整个系统中其他组件的不稳定。这样的设计可以提高软件的可维护性和可扩展性，使得变更变得更加困难。

‍

# The components in Java. What does it mean?

在Java中，组件的含义是指一组类和接口，它们共同实现了特定的功能。在Java编程中，开发者可以使用现有的组件或者自己开发组件，来完成一个应用程序的功能。组件之间应该通过接口来交互，这样有助于保证组件之间的内聚性。

# Abstaction

‍

# Stamp Coupling 印记耦合

Stamp coupling指的是一种软件结构中的耦合方式，即某一组件被其他组件复制或粘贴到另一个组件中，而不是通过直接调用或其他形式的抽象关系进行耦合。这种方式会导致代码冗余和难以维护，因为在修改其中一组件时需要同时修改所有复制的组件。

# Data coupling

数据耦合是指组件之间相互依赖的数据结构的关系。也就是说，组件A需要组件B中的某个数据结构才能正常工作。当组件B的数据结构发生变化时，组件A的工作也会受到影响。

# Control Coupling

Control Coupling 的中文名为控制耦合，这个概念指的是在一个模块的功能从另一个模块被改变。举个例子，一个函数的功能可能会因为另一个模块传入的参数而改变，

比如:

```java
void printValue(bool alsoPrintNewLine) 
{ 
	if(alsoPrintNewLine)
	{print("amother line")}
}
```

这种情况下，使用这个函数的模块需要知道另一个模块的控制参数，如果参数不多并且所有调用者都同意，那么没有问题；但如果参数多且需要修改，就可能对其他模块产生影响，从而增加代码维护的复杂度。

# Common Data coupling

Common Data Coupling是一种耦合方式，指的是在不同的组件之间共享数据，以实现通信和协作。当两个组件共享的数据是同一个数据结构时，就是Common Data Coupling。如果一个组件修改了这个共享数据结构，那么另一个组件也会受到影响。

**例如，在一个Java应用程序中，假设有两个类A和B。A类有一个公共变量X，B类也使用了这个公共变量X。在A类中，如果修改了变量X的值，那么B类中对X的值的引用也会发生变化。这就是Common Data Coupling的一个例子。**

# Content Coupling

内容耦合是指两个组件之间的耦合，当一个组件直接访问另一个组件的内部细节时。这意味着如果另一个组件的内部结构发生变化，则需要对依赖它的组件进行相应的修改。这可能导致复杂性增加，并且在维护代码时变得更加困难。因此，内容耦合应该尽可能地避免。

‍
