[03 Dart的数据类型详解 int double String bool List Maps-2021更新\_哔哩哔哩\_bilibili](https://www.bilibili.com/video/BV1S4411E7LY?p=3&spm_id_from=pageDriver&vd_source=2f6e531d9d833ca7fdcd8c5bb99bd1bb)
[Dart中类的默认构造函数和命名构造函数](https://www.itying.com/dart/dart25.html)
[List 数组的常用方法](https://blog.csdn.net/qq_42351033/article/details/107924344)

# 01
[安装Dart SDK](https://dart.dev/get-dart)
CMD中 `dart --version` 可以检测Dart SDK是否成功安装

配置VSCODE
___
1. 安装 Dart 插件
2. 安装 code Runner 插件


# 03 数据类型

String
___
$```$三个单引号可以写多行字符.

字符串拼接: Print(Str1 + Str2) 或者Print($Str + $Str)

var
___
推断数据类型

List 集合类型
___
```dart
// 方式一
var l1 = ["Jack",20,True];
// 集合是可以不同数据类型的

//方式二 指定数据类型
var l2 = <int>[12,30];

//方式三
var l3 = [];
l3.add(14);
l3.add("jack")
l3.length


```
map
___
```dart
//1

var person = {
"name" : "Jack",
"age" : 20,
"work" : ["1","2"]
};

print(person[name]);


//2
var p = new Map();

p["name"] = "Jack";
p["age"] = 22;
p["work"] = ["程序员","外卖员"];
print(p);

p.addAll({
"height": 160 //Map里就只有addAll 没有add
})
```

is
___
`print(A is int) //输出 true / false`


set
___
也是数组,主要功能是去重.
例如:
```dart

var x = new Set[1,2,3,4,1,1]
print(x); //输出[1,2,3,4]
```

# 06 List Map常用英雄
```dart
//函数是可以没有名字的
(){
	print("Hello");//这也是一个合法函数
	//但是只能用在方法的方法中
}

```


```dart
List myList = [1,2,3,4];

//
var newList = myList.map((value){
	return value*2;
})
//这里返回的newList 是这样的(1,2,3,4),不是一个List.所以需要用var来定义,然后转换成List
print(newList.toList()); 
```

遍历数组方法
___
```dart
for(var item in myList){
	print(item);
}

myList.forEach((value){print("$value")})

```


# 07 函数参数

```dart
//可选参数
void Person(String name,[int age , String sex ]){

}
//age sex这两个可选参数在调用函数的时候可以不赋值.也是对的


//默认参数
void Person(String name,[int age = 20, String sex = "male"]){


}
//如果在调用这个函数的时候没有给age和sex赋值,那么age和sex的值就会是默认值


//命名参数
void Person(String name,{int age, String sex = "male"}){

}

Peson("Jack",age : 20);
//在传递参数的时候必须要带上变量名
```


# 09 类

构造函数与命名构造函数
___
```dart
class Person{
int age;

Person(this.age);
Person.set(int age){
	this.age = age;
}

Person p2=new Person.set(20);   //命名构造函数

```
私有 公有
___
不像Java和C++. Dart语言没有private与public等修饰符.

但是如果你想将Dart语言中的变量修饰为 Private,
你只需要在变量名之前加入`_`即可
```dart
var _name = "Jack";

//_name 是私有变量
```


# 10 静态非静态方法
静态方法
___
```dart
//访问静态变量不需要this, 不管是不是静态成员函数
class Person{
	static int age = 0
	
	static void printName(){
		print(name); //访问静态变量不需要this.name
	} 
	
	void printName2(){
		print(name); //访问静态变量不需要this.name, 不管是不是静态成员函数
	} 
}

```

继承
___
构造函数是不能继承的.
[Extends](assets/Pasted%20image%2020230623144343.png)

```dart

class Rect{
  int height;
  int width;
  Rect():height=2,width=10{      //Dart类中的初始化列表
    print("${this.height}---${this.width}");
  }
  getArea(){
    return this.height*this.width;
  } 
}

void main(){
  Rect r=new Rect();
  print(r.getArea()); 
   
}
```

![](assets/截图_20230623145020.png)

