# Polymorphism
1.  静态多态性（方法重载）
[什么是多态](assets/2023-04-24_172127.png)
```java
public class Calculation {
    public int add(int x, int y) {
        return x + y;
    }

    public double add(double x, double y) {
        return x + y;
    }
}

public class Main {
    public static void main(String[] args) {
        Calculation calc = new Calculation();
        int sum1 = calc.add(10, 20); // 调用第一个add方法
        double sum2 = calc.add(10.5, 20.5); // 调用第二个add方法
        System.out.println("Sum of integers: " + sum1);
        System.out.println("Sum of doubles: " + sum2);
    }
}
```
2. 动态多态性
```java
public class Animal {
    public void makeSound() {
        System.out.println("The animal makes a sound");
    }
}

public class Cat extends Animal {
    @Override
    public void makeSound() {
        System.out.println("Meow");
    }
}

public class Dog extends Animal {
    @Override
    public void makeSound() {
        System.out.println("Woof");
    }
}

public class Main {
    public static void main(String[] args) {
        Animal animal1 = new Cat(); // 创建一个Cat对象，使用Animal类型引用
        Animal animal2 = new Dog(); // 创建一个Dog对象，使用Animal类型引用
        animal1.makeSound(); // 调用Cat的makeSound方法
        animal2.makeSound(); // 调用Dog的makeSound方法
    }
}
```
# code-owners and code-users
abstrction

![](assets/Pasted%20image%2020230424201745.png)

# Coupling And Cohension

## Types of Coupling: 
• Content Coupling 
• Common Data Coupling 
• Control Coupling 
• Stamp Coupling 
• Data Coupling 
• Routine/Temporal Coupling 
• Interface

## logical Cohension
逻辑内聚性是指模块或组件内部元素在功能上相互关联的程度。换句话说，它是衡量模块或组件内部元素之间关系的好坏程度。如果模块内部的元素在逻辑上没有明显的关联或是关联度较弱，就称其具有低逻辑内聚性。通常情况下，低逻辑内聚性不是一个好的设计选择，因为它可能导致代码难以理解、维护和扩展。

举个例子来说明逻辑内聚性的概念。假设我们有一个计算器程序，它有以下几个功能：

-   加法
-   减法
-   乘法
-   除法
-   平方根
-   取反

如果我们将这些功能都放在同一个方法中实现，那么这个方法就具有很低的逻辑内聚性，因为这些功能并没有明显的关联。这样的实现方式可能导致代码难以理解、维护和扩展。

相反，如果我们将这些功能分别放在不同的方法中实现，那么这些方法就具有更高的逻辑内聚性。例如，我们可以创建一个叫做 Calculator 的类，其中包含 add()、subtract()、multiply()、divide()、squareRoot() 和 negate() 方法。这样，每个方法都只实现一个明确的功能，并且与其他方法之间没有复杂的相互依赖关系，使得代码更加清晰、易于理解和扩展。

因此，逻辑内聚性是一种重要的设计原则，有助于提高代码的质量和可维护性。

## Sequential/Procedural/Temporal Cohesion

解释并举例

这三个概念都属于模块或组件的内聚性的不同类型。

-   Sequential Cohesion（顺序内聚性）：模块内部的元素按照某种特定的顺序进行执行。这种内聚性最常见于过程式编程语言中，比如 C 和 Fortran。例如，一个计算税费的函数，需要先计算收入，再计算扣除项，最后计算税费，这些步骤必须按照顺序依次执行。
    
-   Procedural Cohesion（过程内聚性）：模块内部的元素按照某种特定的逻辑或目标组织在一起。这种内聚性最常见于过程式编程语言中，比如 C 和 Pascal。例如，一个处理学生信息的函数，可以包括获取学生信息、验证学生信息、保存学生信息等多个子过程，这些子过程之间没有必要按照特定的顺序执行。
    
-   Temporal Cohesion（时间内聚性）：模块内部的元素按照某种特定的时间段或事件组织在一起。这种内聚性通常与异步编程和事件驱动编程相关。例如，一个处理网络消息的模块，可能包括收到消息、解析消息、执行相关逻辑等多个事件处理函数，这些函数之间没有特定的顺序或逻辑关系。
    

需要注意的是，这些内聚性类型并不是相互独立的，同一个模块或组件可以同时具有多种内聚性类型。在实际的软件设计中，我们需要根据具体的需求和场景，选择合适的内聚性类型来组织代码，以提高代码的可读性、可维护性和可扩展性。

## Communication/Informational Cohesion 

Communication Cohesion（通信内聚性）和 Informational Cohesion（信息内聚性）都属于模块或组件的内聚性的不同类型。

-   Communication Cohesion：模块内部的元素之间通过某种共享的数据结构进行通信。这种内聚性通常与面向对象编程语言中的类或对象相关。例如，一个负责计算电费的类，可能包括获取电表读数、获取电费单价、计算电费等多个方法，这些方法之间通过共享的电费计算规则进行通信。
    
-   Informational Cohesion：模块内部的元素都与同一个抽象的概念或信息相关联。这种内聚性通常与面向对象编程语言中的类或对象相关。例如，一个负责处理学生信息的类，可能包括获取学生姓名、获取学生年龄、获取学生成绩等多个方法，这些方法之间都与同一个抽象的“学生信息”概念相关联。
    

需要注意的是，通信内聚性和信息内聚性是两种不同的内聚性类型。通信内聚性是通过共享的数据结构来实现元素之间的通信，而信息内聚性是通过抽象的概念或信息来实现元素之间的关联。在实际的软件设计中，我们需要根据具体的需求和场景，选择合适的内聚性类型来组织代码，以提高代码的可读性、可维护性和可扩展性。

## Functional Cohesion（功能内聚性） 

Functional Cohesion（功能内聚性）**是模块内部的元素都共同完成一个明确定义的任务，没有其他不必要的功能或操作。** 这种内聚性通常是面向过程编程语言中常见的，例如C语言和Fortran。

Functional Cohesion通常被认为是最好的内聚性类型，因为它使得模块内部的元素紧密相关，并且易于理解和维护。当模块内部的元素都与同一个任务相关联时，我们可以很容易地预测模块的行为，从而更容易地修改和扩展它。

举个例子，考虑一个负责计算平均数的函数。这个函数可能需要接收一个数组作为参数，并返回数组元素的平均值。这个函数内部只需要完成计算平均数的功能，没有其他不必要的操作。这就是一个典型的Functional Cohesion的例子。所有的函数元素都紧密相关，并且共同完成一个明确定义的任务，即计算平均数。

## Content Coupling（内容耦合）

是指一个模块在某种方式下直接访问了另一个模块的内部数据或操作，这种耦合方式是通常被认为是不好的，因为它会导致两个模块之间的高度依赖，限制了模块的独立性和可重用性。

Content Coupling违反了模块的封装原则，因为模块内部的细节暴露给了其他模块，使得其他模块必须了解模块内部的实现细节才能正确地使用它。这种依赖关系会导致代码的紧耦合和难以维护，因为任何一个模块的修改都可能影响到其他模块。

举个例子，考虑两个模块A和B，A模块包含了一些与数据库相关的操作，例如查询、插入和删除数据，而B模块需要获取A模块中查询的数据来进行一些操作。如果B模块直接访问A模块的数据库连接或查询语句，那么这种耦合方式就是Content Coupling。这样做会导致A和B模块高度依赖，限制了它们的独立性和可重用性。正确的做法是将数据库连接和查询语句封装在A模块中，通过公共的接口提供给B模块使用，从而降低两个模块之间的耦合度。

## Common Data Coupling（公共数据耦合）
是指多个模块**共享相同**的数据结构或变量。这种耦合方式通常被认为是不好的，因为它会导致各个模块之间高度依赖，使得修改一个模块的数据结构或变量可能会影响到其他模块的正确性。

Common Data Coupling 违反了模块之间的独立性原则，因为各个模块之间共享相同的数据结构或变量，使得模块的修改可能会影响到其他模块。这种依赖关系会导致代码的紧耦合和难以维护，因为任何一个模块的修改都可能影响到其他模块。

需要注意的是，如果共享的数据结构或变量是只读的，则 Common Data Coupling 可能是可以接受的。这是因为只读数据结构或变量不会影响其他模块的状态，不会影响程序的正确性。

举个例子，考虑一个包含多个模块的程序，这些模块共享同**一个全局变量**来表示当前时间。这种耦合方式就是Common Data Coupling。如果某个模块修改了这个全局变量的值，那么其他模块的逻辑可能会受到影响。正确的做法是将这个变量封装在一个类中，并通过类的接口来访问它，从而降低各个模块之间的耦合度。

## Control Coupling（控制耦合）
是指一个模块直接控制另一个模块的逻辑流程，通常是通过参数、标志或者函数调用来控制。**这种耦合方式不总是坏的，但需要谨慎使用。**

Control Coupling 违反了模块之间的独立性原则，因为它使得一个模块依赖于另一个模块的控制逻辑。这种依赖关系可能会导致代码的紧耦合和难以维护，因为任何一个模块的修改都可能影响到其他模块。

需要注意的是，有时候为了实现特定的功能，使用 Control Coupling 是有必要的。例如，一个模块可能需要控制另一个模块的行为，以确保正确的执行顺序或者避免竞态条件。

举个例子，考虑一个购物车系统，其中一个模块负责处理订单，另一个模块负责处理支付。当订单提交后，订单处理模块需要调用支付模块的函数来处理支付，以确保订单和支付的顺序正确。在这种情况下，使用 Control Coupling 是有必要的，但需要注意避免过度依赖和不必要的耦合。

## Stamp Coupling
是一种耦合类型，**表示两个或多个模块使用相同的数据结构**，但是这些数据结构不是从一个模块传递到另一个模块的参数。这种耦合类型通常被认为是一种较弱的耦合方式。
![](assets/截图_20230424210842.png)
他这个数据结构就直接用类来表示了
Stamp Coupling 违反了模块化原则，因为它在模块之间共享数据结构，导致模块之间的相互依赖。这种依赖关系可能会导致代码的紧耦合和难以维护，因为修改一个模块的数据结构可能会影响到其他模块。

举个例子，考虑一个简单的电子商务系统，其中一个模块负责管理用户数据，另一个模块负责处理订单。如果订单模块和用户数据模块使用相同的数据结构来表示用户信息，那么这两个模块就存在 Stamp Coupling。这可能会导致问题，因为任何一个模块的修改都可能影响到其他模块。

为避免这种耦合类型，可以将数据结构作为参数传递给模块，而不是直接共享数据结构。这种方法可以减少模块之间的依赖关系，并提高代码的可维护性和可扩展性

## Routine/Temporal Coupling（例行/时间耦合）
是一种耦合类型，表示两个或多个模块在特定时间内必须按特定顺序执行。这种耦合类型通常被认为是一种较强的耦合方式。

Routine/Temporal Coupling 的示例是，一个模块必须在另一个模块之后执行。例如，在一个订单处理系统中，一个模块负责验证用户的订单，而另一个模块负责处理付款。如果付款模块在订单验证模块之前运行，将会导致错误的付款或者订单验证失败。因此，这两个模块之间存在例行/时间耦合。

## Interface Coupling（接口耦合）

是一种松散的耦合类型，表示模块之间的通信仅通过它们共享的接口。这种耦合类型通常被认为是最佳形式的耦合方式。

Interface Coupling 的示例是，一个模块提供了一个API（应用程序编程接口），另一个模块使用该API来实现某些功能。这两个模块通过共享的接口进行通信，它们可以独立地开发和维护，因为它们互相不依赖。

Interface Coupling 使代码易于维护和扩展，因为更改一个模块不会影响其他模块，只要接口保持不变。它也使得代码更加灵活，因为不同的实现可以被用于实现相同的接口。因此，在设计软件时，应该尽可能地使用 Interface Coupling。

## Conclusion
P80-83 有例子 讲这些耦合
**高内聚 低耦合**

内聚性 是指模块内部的元素相互依存的程度，也就是模块内部各个元素间的关联度。高内聚的模块指的是模块内部各元素紧密联系，共同实现某一单一功能或一组相关的功能。相反，低内聚的模块指的是模块内部各元素联系松散，实现的功能分散或独立。

耦合性 是指模块间的相互依存程度，也就是模块之间的关联度。高耦合的模块指的是模块之间相互依赖性强，互相影响严重，一旦其中一个模块发生变化，其他模块也需要相应地修改。相反，低耦合的模块指的是模块之间相互独立，互相影响小，一个模块的变化不会影响其他模块。

例如，对于一个电子商务网站，购物车模块应该是高内聚的，因为它包含了所有关于购物车的逻辑和数据。而与购物车模块相连的模块应该是低耦合的，以便于未来的扩展和修改。这意味着购物车模块与其他模块之间的交互应该是通过定义清晰的接口实现的，这种耦合方式称为接口耦合（Interface Coupling），在此情境下是最佳的耦合方式。

## 难点
什么是 Common Data

# 修饰符 
![](assets/截图_20230424212611.png)

# Super Methods
```java
public class Parent {
    public void sayHello() {
        System.out.println("Hello from parent!");
    }
}

public class Child extends Parent {
    @Override
    public void sayHello() {
        super.sayHello(); // 调用父类的方法
        System.out.println("Hello from child!");
    }
}

public class Main {
    public static void main(String[] args) {
        Child child = new Child();
        child.sayHello(); // 输出: "Hello from parent!" 和 "Hello from child!"
    }
}

```

# 抽象类 接口类
一个子类只能继承一个父类
但是一个类可以实现多个接口

## 抽象类
```java
abstract class Shape {
   protected String color;
   
   public Shape(String color){
      this.color = color;
   }
   
   public abstract double getArea();
}

```
这个抽象类名为"Shape"，具有一个受保护的字符串变量"color"和一个抽象方法"getArea()"。由于"Shape"类是抽象的，它不能被直接实例化，而是必须由子类继承并实现"getArea()"方法。这个抽象类提供了一个通用的"color"属性和一个要求子类实现的"getArea()"方法，以便子类可以根据不同的形状（如圆形、矩形等）来具体实现该方法。这个抽象类为子类提供了一个通用的行为和属性，而不是作为实际的对象来使用的。

## 接口

Interfaces are abstract classes with 
• no data 
• all methods marked abstract
*接口是抽象类
*无数据•所有标记为abstract 的方法

```java
public interface Shape {
    double getArea();
    double getPerimeter();
}

```
这个接口定义了两个方法：`getArea()`和`getPerimeter()`。任何实现了`Shape`接口的类都必须实现这两个方法。通过这个接口，我们可以将所有的形状对象统一处理，例如计算它们的面积和周长。同时，我们可以创建不同的形状类来实现这个接口，例如矩形、圆形、三角形等，它们可以根据自己的特点来实现这两个方法，同时保证了对外统一的接口

# Final 关键字
Final can be applied elsewhere: 
• Final classes cannot be inherited from
• Final variables cannot be reassigned 
• It’s all about controlling use/relations between components 
• That is, controlling coupling/cohesion


---

# Unified Model Language
## 修饰符怎么画
![修饰符](assets/截图_20230425101458.png)

## Abstract Class
![](assets/截图_20230425101622.png)
抽象方法 斜体

## Association
![](assets/截图_20230425101915.png)
关联表示一个类与另一个类之间的关系，这种关系可以是单向的或双向的。在一个类中，**可以定义一个实例变量来引用另一个类的实例，这就是关联.**

比如这里的User的示例有一个 Account 的示例

## Inheritance
![](assets/截图_20230425102123.png)

## Aggregation
弱关联

![](assets/截图_20230425102209.png)

## Compositon
强关联

![](assets/截图_20230425102304.png)

## Class implement interface

![](assets/截图_20230425103601.png)













## Confusion
这个什么都没画的线是什么:
![这个什么都没画的线是什么](assets/截图_20230425103806.png)
# Sequence Diagram
![](assets/截图_20230425104126.png)
