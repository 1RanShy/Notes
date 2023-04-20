---
title: Week3
date: 2023-02-01T17:15:26Z
lastmod: 2023-02-04T23:35:35Z
---

# Week3

[4-Advanced_OOP_for_Software_Engineering-generated.pdf](assets/4-Advanced_OOP_for_Software_Engineering-generated-20230201172052-3gkxnxp.pdf)

‍

还是耦合与内聚

# Coupling And Cohesion

Within components: Cohesion • Between components: Coupling\

# 抽象类

* 抽象类：必须从类继承，然后才能构造。
* 抽象方法：必须由子类实现。

抽象类：必须从类继承，然后才能构造。这是什么意思

抽象类是一种特殊的类，它不能被直接实例化，必须由另一个类继承后才能被使用。当一个类继承抽象类后，它必须实现抽象类中所有的抽象方法，然后才能被构造。**这是因为抽象类可以包含抽象方法，它们是需要子类实现的。**

因此，如果您想使用抽象类，则必须从它继承一个子类，实现抽象方法后，才能构造该子类的实例。

# 接口 interface

Interfaces are abstract classes with • no data • all methods marked abstract • They define the API a child class must implement

接口是抽象类，具有以下特征：

* 没有数据
* 所有方法都标记为抽象

它们定义了一个子类必须实现的 API。

简单来说，接口是一种特殊的抽象类，不包含数据，所有方法都是抽象方法，它们定义了子类必须实现的 API。

# Final关键字

Final can be applied elsewhere: • Final classes cannot be inherited from • Final variables cannot be reassigned • It’s all about controlling use/relations between components • That is, controlling coupling/cohesion

"final" 可以应用在其他地方：

* final 类不能被继承
* final 变量不能被重新赋值
* 这一切都是关于控制组件之间的使用/关系
* 也就是说，控制耦合/紧密度。

简单来说，"final"可以用来限制类不能被继承和变量不能被重新赋值，旨在控制组件之间的关系和使用，以此来控制耦合和紧密度。

Objects are Communication Cohesive • Methods that operate on the same data • Language features for Cohesion/Coupling control • Visibility modifiers: public, private, protected • Inheritance: create cohesive “trees” of functionality • Abstract classes/interfaces: Coupling to API only • Specific implementations kept abstract • Polymorphism: Disallows coupling to concrete implementations • Finality: Control when overriding is allowed

对象是通信紧密的

* 操作同一数据的方法
* 用于控制紧密度/耦合的语言特性
* 可见性修饰符：public、private、protected
* 继承：创建功能的紧密的“树”
* 抽象类/接口：仅耦合到API
* 具体实现保持抽象
* 多态：禁止与具体实现的耦合
* 定型：控制何时允许重写。

简单来说，对象是通信紧密的，操作同一数据的方法，语言特性可以用来控制紧密度和耦合，例如可见性修饰符、继承、抽象类/接口、多态、定型。

# 什么是多态 Polymorphism

多态指的是在程序运行期间，同一个方法可以根据不同的对象类型调用不同的实现。

```java
public interface Animal {
    public void makeSound();
}

public class Dog implements Animal {
    @Override
    public void makeSound() {
        System.out.println("Woof");
    }
}

public class Cat implements Animal {
    @Override
    public void makeSound() {
        System.out.println("Meow");
    }
}

public class TestPolymorphism {
    public static void main(String[] args) {
        Animal myAnimal = new Dog();
        myAnimal.makeSound(); // Output: Woof
        myAnimal = new Cat();
        myAnimal.makeSound(); // Output: Meow
    }
}

```

在这个例子中，`Animal`​是一个接口，其中定义了一个方法`makeSound()`​。`Dog`​和`Cat`​类都实现了`Animal`​接口，因此必须实现其中的所有方法。在`main`​方法中，我们创建了一个`Animal`​类型的变量`myAnimal`​，分别将其分配给`Dog`​和`Cat`​对象，调用`makeSound()`​方法时会调用不同的实现，从而实现了多态。

‍

‍

# Common Data

What is “common data” in Java code? How do we identify it A: Common data occurs whenever multiple components (usually functions in OOP) access shared data. For example: methods in a class can share the data members of that class; so this is common data coupling. The main difference to other forms of data coupling is that this data is not passed via parameters. There’s an example on the next side to explain

"共同数据"在Java代码中是什么？我们如何识别它？ A：当多个组件（通常是OOP中的函数）访问共享数据时，会出现共同数据。**例如：类中的方法可以共享该类的数据成员；**因此这是共同数据耦合。与其他形式的数据耦合的主要区别在于该数据不是通过参数传递的。下一页有一个例子解释。

```java
public class User { // Common since both toString // and addYears have access to modify 
private String name = ""; 
public int age = 1;
public String toString() 
{ return name + " " + age; }
// i is *not common* since only addYears has access. 
public String addYears(int i) { age = age + i; }
}
public static void main(String args[]) 
{ User u = new User(); // Also common data since it directly accesses data within u // Getters/Setters turn common data coupling into interface coupling. u.age = 5;
}
```

我的理解就是类定义,可以用 object.variables 可以直接访问的变量就叫common ddata

# 不懂

What is the difference between Place p = new School() and School p = new School()

  
A: The important bit is to think of the type of p, in School p = new School() we remember p is a School meaning it can do anything defined in either Place or School. For Place p = new School() we ignore the fact we know the concrete version of the  
place, and instead treat p as a (abstract) Place only. This means we can only call things defined on Place. This avoids context coupling, since we no longer know the exact implementation details (the School) only general interface details (the Place). It also means we can transparently change it later, e.g. make it Place p = new Hospital()  
without changing any other code below it (so we have reduced coupling!)

‍
