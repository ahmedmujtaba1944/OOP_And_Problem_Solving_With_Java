# OOP_And_Problem_Solving_With_Java


# OOP Concepts

Basic concepts
- oop ?
- class
- object
- encapsulation
- inheritance and its types
- polymorphism
- overloading
- overriding
- abstrction
- class or interface
- constuctors and its types
- access modifier, setter and getter
- final,finally, static, this keyword


### Object-Oriented Programming (OOP)
- OOP is a programming paradigm that structures code around the concept of "objects," which can encapsulate(contian) data ( variable) and behavior ( methods). In OOP, programs are designed by modeling real-world entities as object and defining their interactions.
- This paradigm is based on four key principles:
    1. Encapsulation
    2. Inheritance
    3. Polymorphism
    4. Abstraction

### Encapsulation:
-  Bundling of data (attributes) and the methods (functions) that operate on the  data into a single unit, called a class. This restricts access to some of the object's components  and prevents the accidental modification of data.
 example 
- Class: BankAccount. 
- Data (Encapsulated): Account balance, account holder name
- Methods: Deposit, withdraw.
- Encapsulation ensures that the account balance can only be modified through defined methods, preventing unauthorized access


### Inheritance: 
- A mechanism that allows a class to inherit properties and behaviors from another  class. It promotes code reuse and establishes a hierarchy of classes.

example
- Base Class: Person
-  Properties: Name, Age, Address, Phone 
- Behaviors: UpdateAddress(new_address), Contact()
- Derived Class: Student 
- Inherits from Person and adds properties like marks, subject, GetGrade(), Enrol(subjects), Study() production. 
- Inheritance models the relationship between general entities (Person) and more specific entities (Student).

### Polymorphism:
- It means Many form. a property having many form. in simple words we can define polymorphism as the ability of a same message to be displayed in more than one form. 
- when the same entity(functionl or object) behave differently in diffently scenarios it is knwo as polymorphism.
--- Two types of polymorphism ---

*compile time* (function overloading, operator overloading).
- Function Overloading occurs when a two or more functions can have same name but different parameters.
*run time* (function overriding  )

- Function Overriding occurs when a drive class has a definition of one or more member of a base class.

### Abstraction 
- Data hiding is the process of protection members of a class from uninteded changes whereas, abstraction is hiding the implementation details and showing only important/ useful parts to the user.
- In simple terms, it is hiding the unnecessary details & showing only the essential parts/functionalities to the user.
- Data binding : Data binding is a process of binding the application UI and businesslogic. Any change made in the business logic will reflect directly to the application UI.


Abstraction is achieved in 2 ways :
- Abstract class
- Interfaces (Pure Abstraction)

1. Abstract Class
- An abstract class must be declared with an abstract keyword.
- It can have abstract and non-abstract methods.
- It cannot be instantiated.
- It can have constructors and static methods also.
- It can have final methods which will force the subclass not to change the body the method.

Constructor chaining, when we create the object of child class, first of all it call the constuctor of parent class then call the constructor of child class.

2. Interfaces ( pure abstraction)
- All the fields in interfaces are public, static and final by default
- All methods are public & abstract by default.
- A class that implements an interface must implement all the methods declared in the interface.
- Interfaces support the functionality of multiple inheritance.

example (Abstraction in a Remote Control) 
- Abstraction: RemoteControl 
- Methods: PowerOn, PowerOff, ChangeChannel
- Abstraction simplifies the interaction with a complex TV system, allowing users to control it without understanding its internal workings.


### class
- blue print, Class is a user-defined data type which defines its properties and functions. Class is the only logical representation of the data. For example, Human being is a class. The body parts of a human being are its properties, and the actions performed by the body parts are known as functions. The class does not occupy any memory space till the time an object is instantiated.

### object:
- entity of a class, property ( member variables), actions ( member functions). when a class is defined no memory is allocated but when it is instantiated ( i.e., object is created) of that class.
- Object is a run-time entity. It is an instance of the class. An object can represent a person, place or any other item. An object can operate on both data members and member functions.
- example human is a class. body parts is a member variables, action we performed is called the member functions.
- Note : When an object is created using a new keyword, then space is allocated for the variable in a heap, and the starting address is stored in the stack memory.
- ‘this’ keyword : ‘this’ keyword in Java that refers to the current instance of the class. In OOPS it is used to:
1. pass the current object as a parameter to another method
2. refer to the current class instance variable

i.e., pms.
 ```
class Passowrd{
 
     //data member
     String email;
     String password;

     //member function (methods)

//this: this is the keyword in the java,that tells which object calls this function. 
    public void showPassword(){
    System.out.println(this.email);
    System.out.println(this.password);
    }
}

public class Main(){
    public static void main(String args[]){
    
    //object of Passowrd class
  
     Passowrd obj1 = new Password();
    
     obj1.email = "test@gmail.com";
     obj1.password = "Tester@54321";

     //print infor
     obj1.showPassword();
}
```
example pen or oop class
```
package OOPs;
import java.util.Scanner;

//pen clas
class Pen{
    String color;
    String type;
    int price;

    public void write(){
        System.out.println("write some thing");
    }

    public void showInfo(){
        System.out.println(this.color);
        System.out.println(this.price);
        System.out.println(this.type);
    }
}
public class OOPs {

    public static void main(String args[]){

         Scanner scanner = new Scanner(System.in);


         Pen p1 = new Pen();
         p1.color = scanner.nextLine();
         p1.price = scanner.nextInt();
         p1.type = scanner.nextLine();


         //show details
        p1.showInfo();

    }
}
```

### Constructor 

- it is the special type of function that is automatically called when object is ceated. having same name as the class name.
- constructor does not return anything. ( dont have any return type)
- call only one time for one object. ( calls when object is created)


#### Example of constructor 
Student s1 = new Student();

- Student: data type of s1 object
- new: it is keyword in java that allocate a new space in memory with the name of Student. 
- Student(): non parameterized constructor. 

there are 3 types of constructor in java
1. non parameterized constructor
- A constructor which has no argument is known as non-parameterized constructor(or no-argumentconstructor). It is invoked at the time of creating an object. If we don’t create one then it is created by default by Java.

example
```
package OOPs;
import java.util.Scanner;
class Student {
    // non parameterized constructor
   
    String name;
    int marks;
    public void showInfo(){
        System.out.println(this.name);
        System.out.println(this.marks);
    }
     Student(){
        System.out.println("Object is Created");
    }
}
public class OOPs {
    public static void main(String args[]){
          Student s1 = new Student();
    }
}
```
2. Parameterized Constructor.
- A parameterized constructor is a type of constructor that accepts parameters when an object is created
example
```
package OOPs; 

import java.util.Scanner;

class Student {
    String name;
    int marks;
    Student(String name, int marks){
       this.name = name;
        this.marks = mar
    }
    
    public void showInfo(){
        System.out.println(this.name);
        System.out.println(this.marks);
    }
}

public class OOPs {
    public static void main(String args[]){
         Scanner scanner = new Scanner(System.in);
         String name = scanner.nextLine();
         int marks = scanner.nextInt();
         
          Student s1 = new Student(name,marks);
          s1.showInfor();
    }
}
```

3. copy constructor:  
- copy and object and put into and other object
example
```
package OOPs;

import java.util.Scanner;

class Student {
    String name;
    int marks;

    Student(Student s2){
        this.name = s2.name;
        this.marks = s2.marks;
    }
    
    Student(){

    }
    
    public void showInfo(){
        System.out.println(this.name);
        System.out.println(this.marks);
    }
}

public class OOPs {

    public static void main(String args[]){
          Scanner scanner = new Scanner(System.in);
          Student s1 = new Student();
          s1.name = scanner.nextLine();
          s1.marks = scanner.nextInt();
          
        Student s2 = new Student(s1);
        s2.showInfo();
    }
}
```
4. destructor
- Because Java is a garbage collected language you cannot predict when (or even if) an object will be destroyed. Hence there is no direct equivalent of a destructor.
  
### Polymorphism ( many forms)

1. function overloading - compile time
2. function overriding  - runtime


***Function overLoading  ( same name but different parameters)***

- make diff return type of paramerter if parameter are same in quantity
- make diff number of parameter in quantity if return type are same
example with code. 

Example of polymorphism
```
package OOPs;
class Student {
    String name;
    int marks;
    
    public void showInfo(String name, int marks){
        System.out.println(name);
        System.out.println(marks);
    }
    
    public void showInfo(String name){
        System.out.println(name);
    }
}

public class OOPs {

    public static void main(String args[]){
         Student s1 = new Student();
         s1.name = "test";
         s1.marks = 10;
         s1.showInfo(s1.name);
         s1.showInfo(s1.name, s1.marks);
    }
}
```
***Runtime Polymorphism : Runtime polymorphism is also known as dynamic polymorphism.***
- Function overriding is an example of runtime polymorphism. Function overriding means when the child class contains the method which is already present in the parent class. Hence, the child class overrides the method of the parent class. 
- In case of functionoverriding, parent and child classes both contain the same function with a different defination. the call to the function is determined at runtime is  known as run time polymorphism.

### Inheritance
- one class wants to use the property of other class

example
```
package OOPs;
class Person{
    String name;
    int age;
    int phone;
}
class Student extends Person{
    int marks;
    public void showDetails(){
        System.out.println(this.name+" "+ this.age+ " "+ this.marks);
    }
}
class Teacher extends  Person{
    int salary;
    public void showDetails(){
        System.out.println(this.name+" "+ this.age+ " "+ this.salary);
    }
}
public class OOPs {
    public static void main(String args[]){
         Student s1 = new Student();
         s1.marks = 12;
         s1.age = 20;
         s1.name = "student";
         s1.showDetails();

         Teacher t1 = new Teacher();
         t1.name = "Teacher";
         t1.age = 30;
         t1.salary = 1000;
         t1.showDetails();
    }
}
```
1. Single Level inheritance (we have one base class and one drive class)

example
```
class Shap{
    public void printArea(){
    
        System.out.println("Display Area");
    }
}

class Triangle extends Shap{

    public void printArea(int l, int h){
        System.out.println(1/2*l*h);
    }
}
```

2. Multi Level inheritance ( chaining of classes )

example
```
class Shap{

    public void printArea(){
    
        System.out.println("Display Area");
    }
}

class Triangle extends Shap{

    public void printArea(int l, int h){
        System.out.println(1/2*l*h);
    }
}
class EquilateralTriangle extends Triangle{

    public void printArea(int l, int h){
        System.out.println(1/2*l*h);
    }
}
```
3. Hierarchial Inheritance ( one base class and multiple child class inherit that base class )
example
```
class Person{

    String name;
    int age;
    int phone;
}

class Student extends Person{
    int marks;
   
    public void showDetails(){
        System.out.println(this.name+" "+ this.age+ " "+ this.marks);
    }
}

class Teacher extends  Person{
    int salary;
    public void showDetails(){
        System.out.println(this.name+" "+ this.age+ " "+ this.salary);
    }
}

```

5. Hybrid Inheritance ( combination  of one or more type) hierarchial plus multi-level.


### Access Modifiers 

1. Private: The access level of a private modifier is only within the class. It can not be accessed from outside the class.

2. Default: The access level of a default modifier is only within the package.  cannot be accessed from outside the package. If you do not specify any access level, it will be the default.

3. Protected: The access level of a protected modifier is within the package a outside the package through child class. If you do not make the child class, it cannot be accessed from outside the package.

4. Public: The access level of a public modifier is everywhere. It can be access from within the class, outside the class, within the package and outside the package.



### Getters & Setter
- get the value from the private variable
- set the value to private variable

Example of Setter and Getter.
```
package OOPs;
class Account{

    private int balance;
    
    public int getBalance(){
        return this.balance;
    }
    
    public void setBalance(int balance){
        this.balance = balance;
    }
}

public class OOPs {
    public static void main(String args[]){
    
        Account obj = new Account();
        obj.setBalance(100);
        System.out.println(obj.getBalance());
    }
}
```

### Abstraction 
- Data hiding is the process of protection members of a class from uninteded changes whereas, abstraction is hiding the implementation details and showing only important/ useful parts to the user.
- In simple terms, it is hiding the unnecessary details & showing only the essential parts/functionalities to the user.
- Data binding : Data binding is a process of binding the application UI and businesslogic. Any change made in the business logic will reflect directly to the application UI.


Abstraction is achieved in 2 ways :
- Abstract class
- Interfaces (Pure Abstraction)

1. Abstract Class
- An abstract class must be declared with an abstract keyword.
- It can have abstract and non-abstract methods.
- It cannot be instantiated.
- It can have constructors and static methods also.
- It can have final methods which will force the subclass not to change the body the method.

Constructor chaining, when we create the object of child class, first of all it call the constuctor of parent class then call the constructor of child class.

2. Interfaces ( pure abstraction)
- All the fields in interfaces are public, static and final by default
- All methods are public & abstract by default.
- A class that implements an interface must implement all the methods declared in the interface.
- Interfaces support the functionality of multiple inheritance.

example (Abstraction in a Remote Control) 
- Abstraction: RemoteControl 
- Methods: PowerOn, PowerOff, ChangeChannel
- Abstraction simplifies the interaction with a complex TV system, allowing users to control it without understanding its internal workings.

 Example of Abstract class
 ```
package OOPs;

abstract class  Animal{
    abstract public void walks();
}

class Hours extends Animal {
    public void walks() {
        System.out.println("Walks on 4 legs");
    }
}

public class OOPs {

    public static void main(String args[]){
      Hours hours = new Hours();
      hours.walks();
    }
}
```

2. Interfaces ( pure abstraction)
- All the fields in interfaces are public, static and final by default
- All methods are public & abstract by default.
- A class that implements an interface must implement all the methods declared in the interface.
- Interfaces support the functionality of multiple inheritance.

 Example of Interfaces
 ```
package OOPs;

interface Animal{

   String color = "Black";
    void walks();
}

interface Red { 
}

class Hours implements  Animal , Red{
    public void walks() {
        System.out.println("Walks on 4 legs");
    }
}

public class OOPs {

    public static void main(String args[]){
      Hours hours = new Hours();
      hours.walks();
    }
}
```
