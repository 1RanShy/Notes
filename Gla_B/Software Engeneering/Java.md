# Java子类可以使用父类的构造器
当一个子类继承一个父类时，它可以使用父类的构造函数来初始化继承的成员变量。

在Java中，子类可以通过调用super关键字来显式调用父类的构造函数。使用super关键字时，子类必须在构造函数的第一行调用父类的构造函数。如果子类没有显式地调用父类的构造函数，则编译器会自动调用父类的默认构造函数。

下面是一个简单的示例，展示了如何使用super关键字在子类中调用父类的构造函数：

~~~java
public class Animal {
    private String name;
    private int age;

    public Animal(String name, int age) {
        this.name = name;
        this.age = age;
    }

    public String getName() {
        return name;
    }

    public int getAge() {
        return age;
    }
}

public class Dog extends Animal {
    private String breed;

    public Dog(String name, int age, String breed) {
        super(name, age);
        this.breed = breed;
    }

    public String getBreed() {
        return breed;
    }
}

public class Main {
    public static void main(String[] args) {
        Dog dog = new Dog("Fido", 3, "Labrador");
        System.out.println("Name: " + dog.getName());
        System.out.println("Age: " + dog.getAge());
        System.out.println("Breed: " + dog.getBreed());
    }
}
~~~

在上面的示例中，我们定义了一个Animal类和一个Dog类。Dog类继承自Animal类，并添加了一个名为breed的属性。我们在Dog类的构造函数中使用super关键字来调用父类Animal的构造函数，以初始化name和age属性。我们创建一个Dog对象，并输出它的属性。注意，我们只需要在Dog类中定义breed属性的getter方法，因为name和age属性继承自Animal类。