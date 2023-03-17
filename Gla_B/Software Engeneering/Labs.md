[图解7种耦合关系](https://yanhaijing.com/program/2016/09/01/about-coupling/)
# Lab0
# Q1
主要是讲数据耦合和印记耦合
##  1. 1 Data Coupling 数据耦合
When lots of parameters are sent between methods, data coupling occurs.
多个数据在多个方法之间传递

传递的参数数量大于等于三个就算是数据耦合.
```java
public class DataCoupling {

int numberA = 1;

int numberB = 2;

int numberC = 3;

boolean allNumbersSet = true;

Printer printer = new Printer();

Sum mySum = new Sum();

public void firstCaller() {

printer.print(numberA, numberB, numberC, allNumbersSet);

}
//出现了数据耦合 data coupling

public void secondCaller() {

mySum.sum(numberA, numberB);

}

public static void main(String[] args) {

DataCoupling myDataCoupling = new DataCoupling();

myDataCoupling.firstCaller();

myDataCoupling.secondCaller();

}

}
```

## 1.2 stamping coupling 标记耦合
![](assets/Pasted%20image%2020230223124937.png)
## 1.3 解决标记耦合
NumberAndBoolean这个类是为了之前去掉数据耦合而产生的
一次不传递四个数据只传递一个类

为了解决1.2的标记耦合,那就去掉Number这个类.改为把printer中的print函数分为两个小的函数,这样就可以了. 这样一次只传递两个变量,就不会出现数据耦合了,印记耦合也消失了.

## 1.4
数据耦合全部消失,且没有引入其他耦合.

## Conclusion
#数据耦合 Data Coupling
#标记耦合 Stamping Coupling
调用模块和被调用模块之间传<mark style="background: #FFB8EBA6;">递数据结构而不是简单数据</mark>，同时也称作特征耦合。

调用模块和被调用模块之间只传递<mark style="background: #FFB8EBA6;">简单的数据项参数</mark>。相当于高级语言中的值传递。

<mark style="background: #FFB8EBA6;">数据耦合 data coupling</mark>是指两个或多个模块之间的依赖关系，其中一个模块使用另一个模块的数据。当一个模块使用另一个模块的数据时，它就对该数据的格式、类型和值产生了依赖，从而导致它与另一个模块紧密耦合。

在软件开发中，数据耦合可能会导致以下问题：

-   降低代码的可重用性和可维护性，因为修改一个模块可能会导致其他模块也需要修改。
-   增加代码的复杂性，因为需要考虑多个模块之间的依赖关系。
-   增加代码的错误率，因为更多的依赖关系可能会导致错误的传递或不正确的使用数据。

为了减少数据耦合，可以使用软件设计原则和模式，例如抽象、封装和接口隔离等原则。这些原则可以帮助设计出低耦合的代码结构，从而提高代码的可维护性、可重用性和灵活性。

<mark style="background: #FF5582A6;">这里特指依赖的数据大于等于3个</mark>

<mark style="background: #FFB8EBA6;">戳印耦合（Stamp Coupling）</mark>，又称为格式耦合或外观耦合，是指一个模块依赖于另一个模块的接口，但只使用其中的一部分参数或数据，而不是使用整个接口。这种情况下，一个模块对另一个模块的接口的某些部分产生了不必要的依赖关系，从而导致代码紧密耦合，难以维护、扩展和重构。

举个例子，假设有两个模块 A 和 B。模块 A 调用了模块 B 的一个方法，这个方法包含了多个参数。但实际上，模块 A 只需要其中的一部分参数，而不需要使用所有的参数。这样，模块 A 就对模块 B 的接口的一部分产生了依赖，即产生了戳印耦合。

为了避免戳印耦合，可以使用更细粒度的接口来调用模块，只传递实际需要的参数。这可以使代码更加灵活和可维护，同时也可以减少对其他模块的依赖性。

---
---
# Lab1
# Q2
## 1 内容耦合
Content Couplingis (内容耦合) is observed <mark style="background: #FFB8EBA6;">when one moduleor class accesses and modifies the data of another moduleor class. </mark>This type of coupling can be reduced by having private instance variables and using getters and setters
内容耦合是最紧的耦合程度，一个模块直接访问另一模块的内容，则称这两个模块为内容耦合。

内容耦合是指如果一个模块与另一个模块的内部属性有关，不经调用直接使用另一个模块的程序代码或内部数据，那么这两个模块之间就存在内容耦合。这种耦合表明一个模块与另一个模块的内部数据或程序代码有关，当一个模块的程序代码被修改或内部数据出错,必然引起另一个模块出错。

## 2 数据耦合的替换
把 生日的 年 月 日改为了一个类
~~~java
//改之后
Person w1 = new Person("aaa", new dob(1, 2, 1991)); w1.setType(2);

Person w2 = new Person("bbb", new dob(3, 4, 1993)); w2.setType(2);

Person w3 = new Person("ccc", new dob(5, 6, 1995)); w3.setType(2);
// ------------------------
public class dob {

private int dob_d, dob_m, dob_y; // date of birth

public dob(int dob_day, int dob_month, int dob_year) {

dob_d = dob_day;

dob_m = dob_month;

dob_y = dob_year;

}

public int get_dob_day() {

return this.dob_d;

}

public int get_dob_month() {

return this.dob_m;

}

public int get_dob_year() {

return this.dob_y;

}

}
~~~

~~~java
Person w1 = new Person("aaa", 1, 2, 1991); w1.type = 2;

Person w2 = new Person("bbb", 3, 4, 1993); w2.type = 2;

Person w3 = new Person("ccc", 5, 6, 1995); w3.type = 2;

Person b1 = new Person("ddd", 7, 8, 1997); b1.type = 1;

b1.worker = new Person[10];

Person b2 = new Person("eee", 9,10, 1999); b2.type = 1;

b2.worker = new Person[10];
~~~

## 构造函数 拷贝构造函数

Java中的构造函数（Constructor）是一种特殊类型的方法，用于创建并初始化对象。构造函数在对象被创建时被调用，并且在对象创建时只能被调用一次。构造函数名称必须与类名相同，并且不返回任何值，因为它们的主要目的是初始化类的实例变量。

拷贝构造函数（Copy Constructor）是一种特殊类型的构造函数，用于创建一个新对象，并将现有对象的所有属性值复制到新对象中。拷贝构造函数通常用于创建一个新的对象，该对象与现有对象具有相同的属性值。在Java中，可以使用关键字`this`来引用当前对象，也可以使用关键字`super`来引用超类的构造函数。如果没有提供拷贝构造函数，则Java编译器将生成一个默认的拷贝构造函数，该构造函数将按值复制对象的属性值。
~~~java
//构造函数
public class Person {
    private String name;
    private int age;

    // 构造函数
    public Person(String name, int age) {
        this.name = name;
        this.age = age;
    }

    // getter 和 setter 方法
    public String getName() {
        return name;
    }

    public void setName(String name) {
        this.name = name;
    }

    public int getAge() {
        return age;
    }

    public void setAge(int age) {
        this.age = age;
    }
}

// 创建 Person 对象
Person person = new Person("Tom", 25);

~~~

~~~java
//拷贝构造函数
public class Student {
    private String name;
    private int age;

    // 拷贝构造函数
    public Student(Student other) {
        this.name = other.name;
        this.age = other.age;
    }

    // getter 和 setter 方法
    public String getName() {
        return name;
    }

    public void setName(String name) {
        this.name = name;
    }

    public int getAge() {
        return age;
    }

    public void setAge(int age) {
        this.age = age;
    }
}

// 创建 Student 对象
Student student1 = new Student("Tom", 25);
Student student2 = new Student(student1); // 使用拷贝构造函数创建一个新的 Student 对象

~~~
在上面的示例中，`Student`类包含一个拷贝构造函数，该构造函数带有一个`Student`对象作为参数，用于将另一个`Student`对象的属性值复制到新对象中。通过使用该拷贝构造函数，可以创建一个新的`Student`对象，该对象与现有`Student`对象具有相同的属性值。

## 3 Routing Coupling 例程耦合
例程耦合（Routine coupling）发生在多个方法需要一起调用以完成某些任务的情况下。例如，（如您在上一节课中看到的）将钱M从账户A转移到账户B需要执行以下步骤：

• 从账户A中取出M金额（例如，remove(M，A)）

• 将M金额添加到账户B中（例如，add(M，B)）

如果忘记调用其中一个方法，则会导致问题。解决这种例程耦合的一种方法是创建另一个方法（例如，transfer（M，A，B）），该方法首先调用方法remove（M，A），然后调用方法add（M，B）。


# Lab 2.1
## Control Coupling 控制耦合
Control coupling is a specialised form of coupling where one of the parameters to amethod is a control variable which decides what the method does.The disadvantage of control coupling is that the code-user has to know the different values the control variable cantake and what these variablesmean



## Class Date
自己写一个类 很简单