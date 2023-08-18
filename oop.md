  

# Object Oriented Programming (OOP)

## OOP

OOP is a methodology or paradigm to design a program using classes and objects. Its simplifies the software development and mainrenance by providing some conpects below:  

## Class

Class is a **user-defined data type** which defines its **properties** and its functions. 

Class is the only **logical** representation of the data. 

For example, Human being is a class. The **body parts** of a human being are its **properties**, and the **actions** performed by the body parts are known as **functions**. 

The class does **not occupy any memory space**  `till the time an object is instantiated`.

  

## Object

 
Object is a **run-time entity**. 

It is an **instance** of the class. 

An object can represent a person, place or any other item. An object can operate on both data members and member functions.
 
**In short, Classes are blueprint and object are the actual product which is made using that blueprint**

If we take an example, In large factories, they spend millions of dollars to create a blueprint of a car, and that **blueprint** we can call a **class**, and using that blueprint, they create millions of cars, and these cars are called **objects**.

**Following is the example of class and object**

**Code:**

```java
class Car {
    String brand = "Tesla";
    int tires;
    String series;
}

public class ClassObject {

    public static void main(String[] args) {
        Car carObj1 = new Car(); // Object 1
        
        carObj1.series = "A";
        carObj1.tires = 4;
        
        System.out.println(carObj1.brand + " has " + carObj1.tires + " tires and is of " + carObj1.series +" series");
        
        Car carObj2 = new Car(); // Object 2

        carObj2.series = "X";
        carObj2.tires = 3;

        System.out.println(carObj2.brand + " has " + carObj2.tires + " tires and is of " + carObj2.series +" series");
    }
}
```

  

**Output:**

  

![](https://imgur.com/0396P8n.png)

  
  
  

This approach enhances code reusability and maintains a clear separation of concerns.

  
  

**Note**: When an object is created using a new keyword, then space is allocated for the variable in a **heap**, and the **starting address** is stored in the **stack memory**.

#### **Constructor**: 
A constructor is a special method that is invoked automatically at the time of object creation. It is generally used to initialise the data members of new objects.

● Constructors have the same name as classes or structures.

● Constructors don’t have a return type. (Not even void.)

● Constructors are only called once, at object creation.

There are three types of constructors.

### Non-Parameterized Constructor:

A constructor that has `no argument` is known as a non-parameterized constructor (or no-argument constructor).

It is invoked at the time of creating an object. If we don’t create one, then it is created by default by Java.

**Code:**
```java
class Me{

    Me(){
        System.out.println("My name is Abhishek Pathak");
    }
}

public class ClassObject {

    public static void main(String[] args) {

        Me me = new Me();
    }    
}
```

**output:**

![non parameterized constructor](https://imgur.com/2UqEUlD.png)

  

### Parameterized constructor

  

A constructor that has `parameters` is called a parameterized constructor.

  

It is used to provide different values to distinct objects.

  
  

**Code:**
```java

class Car {
    String brand = "Tesla";
    int tires;
    String series;

    Car(int tires, String series) {
        this.tires = tires;
        this.series = series;
    }
}

public class ClassObject {

    public static void main(String[] args) {

        Car carObj1 = new Car(1, "A"); // Object 1

        System.out.println(carObj1.brand + " has " + carObj1.tires + " tires and is of " + carObj1.series +" series");

        Car carObj2 = new Car(3, "X"); // Object 2

        System.out.println(carObj2.brand + " has " + carObj2.tires + " tires and is of " + carObj2.series +" series");
    }
}
```

**output:**

![](https://imgur.com/1PMYZwU.png)

  

#### **‘this’ keyword**: ‘this’ keyword in Java refers to the current instance of the class. In OOPS, it is used to:

1. pass the current object as a parameter to another method

2. refer to the current class instance variable


### Copy Constructor

  

A copy constructor is an overloaded constructor used to declare and initialise an object from another object.

  
  

**Code:**

```java
class Car {
    String brand = "Tesla";
    int tires;
    String series;

    Car(CarObj obj1) {
        this.tires = obj1.tires;
        this.series = obj1.series;
    }
}
```


  
  
  

**Java has a garbage collector that deallocates memory automatically.**
  

## Polymorphism

In simple words, poly means'**many**’ and morphism means **forms**.

This means a function can be *written in different forms*.

Polymorphism allows objects of different classes to be treated as instances of a common superclass.

Now, there are **two** types of polymorphism:

#### 1. Compile time polymorphism (static).

#### 2. Runtime Polymorphism (Dynamic)

Let’s deep-dive them one by one:
  

### Compile Time Polymorphism

The polymorphism that is implemented at compile time (the compiling stage) is known as compile-time polymorphism. example: **Method Overloading**

#### Method Overloading

Method overloading is a technique that **allows you to have more than one function with the same name but with different functionality**. 

The signature of the function is considered here.

#### What is function signature ?
  In Java, a method signature is composed of a name and the number, type, and order of its parameters. Return types and thrown exceptions are not considered to be part of the method signature, nor are the names of parameters; they are ignored by the compiler for checking method uniqueness.

Method overloading can be possible on the following basis:

1. The type of parameters passed to the function

2. The number of parameters passed to the function
  

**Code:**

```java
class Student {
    String name;
    int roll;

    public void display(String name) {
        System.out.println("Name: " + name);
    }

    public void display(String name, int roll) {
        System.out.println("Name: " + name + " roll: " + roll);
    }
}

public class Polymorphism {

    public static void main(String[] args) {
        Student std = new Student();
        std.display("Abhishek");
        std.display("Abhishek", 20);
    }
}
```

**Output:**

![poly](https://imgur.com/HqnXzTp.png)

### **Runtime Polymorphism**

Runtime polymorphism is also known as **dynamic polymorphism**.

**Function overriding** is an example of runtime polymorphism.

#### **Function overriding**

In a nutshell, function overriding is done when we override the function from the parent class, which means the child class has the same function as the parent class and the child class changes some fields.

This is called **dynamic** because objects are created in the head, which are dynamic. You will understand more when we do the inheritance.

**Code:**

Will do after `Inheritance`

Now, the next one on our list is THE GREAT `Inheritance`

## Inhertance

Inheritance is a process in which one object **acquires** all the properties and behaviours of its **parent** object automatically.

In such a way, you can reuse, extend, or modify the attributes and behaviours that are defined in other classes.
  
In Java, the class that inherits the members of another class is called the **derived class**, and the class whose members are inherited is called the **base class**.

The derived class is the specialised class for the base class.

We have different types of inheritance:

1. Single Inheritance

2. Hierarchical Inheritance

3. Multilevel Inheritance

Let's dive into them one by one:

### 1. Single Inheritance

  
 
> In Java, we achieve inheritance using the `extends` keyword.

**When one class inherits another class, it is known as single-level inheritance.**

```java
class Brand {

    int tires = 4;
    public void name() {
        System.out.println("This is class brand");
    }
}

class Tesla extends Brand {
    public void name(String name) {
        System.out.println("The brand is: "+ name + " with " + this.tires +" tires");
    }
}

public class Inheritance1 {

    public static void main(String[] args) {
        Tesla t = new Tesla();
        t.name("Tesla");
    }
}
```

Here, we can observe that the class Tesla **extends** Brand class and class Tesla make use of variable **tyres**.

 
Until now, you may have observed that both the function name in the parent class, i.e., **base class**, `name` is used in the child class, i.e., **derived class**. This is called **Run-Time Polyorphism**.

### Hierarchical inheritance:

Hierarchical inheritance is defined as the process of deriving more than one class from a base class.

```java
class Pencil {
    int size = 2;
}

class Apsara extends Pencil{
    Apsara(){
        System.out.println("This is Apsara with pencil length" + this.size);
    }
}

class Doms extends Pencil {
    Doms(){
        System.out.println("This is Doms with pencil length" + this.size);
    }
}
```

### Multilevel inheritance:

Multilevel inheritance is the process of deriving a class from another derived class.

```java
class Brand {

    int tires = 4;
}

class Manufacturer extends Brand{
    String mname = "Tesla";
}

class Tesla extends Manufacturer {
    public void name(String name) {
        System.out.println("The brand is: "+ name + " with " + this.tires +" tires and manu by " + this.mname );
    }
}

public class Inheritance1 {

    public static void main(String[] args) {
        Tesla t = new Tesla();
        t.name("Tesla");
    }
}
```
  

**output:**

![multi-level](https://imgur.com/7q04w6K.png)

### Hybrid inheritance

Hybrid inheritance is a combination of simple, multiple inheritance and hierarchical inheritance.

Now, we will move forward with **encapsulation**.



## Encapsulation


Encapsulation is the process of combining data and functions into a single unit called a class. In encapsulation, the data is not accessed directly; it is accessed through the functions present inside the class.


In simpler words, attributes of the class are kept **private** and **public**; **getter** and **setter** methods are provided to manipulate these attributes.


Encapsulation helps us achieve data hiding.


#### Data hiding:


Data hiding is a language feature to restrict access to members of an object, reducing the negative effect of dependencies. e.g., the "protected" and "private" features in Java


Before moving with encapsulation, we need to have some knowledge of access modifiers.


## Access Modifiers


Access modifiers are keywords that determine the visibility or accessibility of classes, methods, fields, and constructors within a programme.


They control which parts of the code can be accessed from different classes or packages.



1. Public
2. Protected
3. Default
4. Private


Let's do a deep dive into each of these.


### 1. Public


The public access modifier allows a class, method, field, or constructor to be accessible from anywhere in the programme, even from other classes and packages.

```java
public class Car {
    public String brand = "Tesla";
    public void startEngine() {
        System.out.println("Engine started.");
    }
}
```



### 2. Protected:

The protected access modifier allows a class, method, or field to be accessible within its **own package** and by **subclasses in other packages**.

```java
protected class Vehicle {
    protected String type = "Automobile";
    protected void honk() {
        System.out.println("Honk honk!");
    }
}
```

### 3. default (no modifier)

If **no access** modifier is specified, it's considered as the default access level. A class, method, or field with default access can be accessed only within its **own package**.

```java
class Animal {
    String name = "Unknown";
    void makeSound() {
        System.out.println("Some sound");
    }
}
```

### 4. Private

The private access modifier restricts the visibility of a **class member** to only **within the same class**. It's the most restrictive access level.

```java
class BankAccount {
    private double balance = 0.0;
    private void deductFees() {
        balance -= 10.0;
    }
}
```



This much is enough for the **access modifiers**, and we will head back to our **encapsulation**.


**So, encapsulation makes use of access modifiers to achieve data hiding.**


#### As mentioned above, encapsulation makes use of `getters` and `setters` to access the attributes.

You will understand more with the following example:


```java
class Bank {
    private double balance = 0.0;

    public Bank(double initial) {
        balance = initial;
    }

    public double getBalance() {
        return balance;
    }

    public void deposit(double amount) {
        if (amount > 0) {
            balance += amount;
            System.out.println("Deposited: " + amount);
        }
    }

    public void withdraw(double amount) {
        balance -= amount;
        System.out.println("Widrawl Done");
    }
}

public class Encapsulation {
    public static void main(String[] args) {
        Bank bank = new Bank(10);

        System.out.println("Initial Balance: " + bank.getBalance());
        bank.deposit(30);
        bank.withdraw(3);
        System.out.println("Balance after widrawl: " + bank.getBalance());
    }
}
```



This example shows the perfect encapsulation. The attribute `balance` is made private, so only the class methods can use and manipulate it.
Try playing around with it.

Now, next we have **Abstraction**


## Abstraction


> This time, I will be using a simple example, sure

Imagine driving a car.

You don't need to know every intricate detail of how the engine works; you just need to understand the basic functions such as accelerating, braking, and steering. 

Abstraction works similarly in software development.


It enables you to create simplified models of real-world objects, emphasising what's important while concealing the complexities.


Here, we try to achieve an **abstract view**.


> Wasn't this a simple one?


In simple terms, it is **hiding unnecessary** details and showing only the essential parts and functionalities to the user.

#### Data binding


Data binding is the process of binding the application UI and business logic. Any change made in the business logic will reflect directly on the application UI.



Abstraction is achieved in two ways:



1. Abstract class
2. Interfaces (Pure Abstraction)



Let's do a deep dive into each of them.


### 1. Abstract Class


In Java, abstraction can be achieved using the abstract class.

Following are the points that will give some glimmer:

- An abstract class must be declared with an abstract keyword.
- It can have abstract and non-abstract methods.
- It cannot be instantiated.
- It can have constructors and static methods as well.
- It can have final methods that will force the subclass not to change the body of the method.


```java
abstract class Shape {
    abstract void draw();
    Shape(){
        System.out.println("Creating new shape");
    }
}

class Circle extends Shape {
    void draw() {
        System.out.println("I'm drawing Circle here");
    }
}

class Square extends Shape {
    void draw() {
        System.out.println("I'm drawing Square here");
    }
}

```



Here, as you can see, we are using the `draw` method again and again in the derived classes.


### 2. Interfaces (Pure Abstraction)

This is another way to achieve abstraction.


Some of the specifications are:

- All the fields in interfaces are public, static, and final by default.

- All methods are public and abstract by default.

- A class that implements an interface must implement all the methods declared in the interface.



```java
interface Shape {
    double calculateArea();
    double calculatePerimeter();
}

class Circle implements Shape {
    double radius;

    public Circle(double radius) {
        this.radius = radius;
    }

    public double calculateArea() {
        return Math.PI * radius * radius;
    }

    public double calculatePerimeter() {
        return 2 * Math.PI * radius;
    }
}
```

**Interfaces support the functionality of multiple inheritance**

---  

**I will be adding more to it, based on the comments**

---


If the article helps you, leave a like, follow, or anything 🙂.  
You can follow me on [LinkedIn](https://www.linkedin.com/in/abhishekpathak32/), [GitHub](https://github.com/scorcism), [Dev.to](https://dev.to/scorcism) and [hashnode](https://scorcism.hashnode.dev/).

**Bye**
