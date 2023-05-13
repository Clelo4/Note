- [1. Java Concept](#1-java-concept)
- [2. Documents And Specifications](#2-documents-and-specifications)
- [3. Essential](#3-essential)
- [4. Learning the Java Language](#4-learning-the-java-language)
  - [What is an Object?](#what-is-an-object)
  - [What is a Class?](#what-is-a-class)
  - [What is Inheritance?](#what-is-inheritance)
  - [What is an Interface?](#what-is-an-interface)
  - [What is a Package?](#what-is-a-package)
- [5. Language Basics](#5-language-basics)
  - [5.1 Variables](#51-variables)
  - [5.2 Naming](#52-naming)
  - [5.3 Primitive Data Types](#53-primitive-data-types)
  - [5.4 Literals](#54-literals)
    - [Integer Literals](#integer-literals)
    - [Floating-Point Literals](#floating-point-literals)
    - [Character and String Literals](#character-and-string-literals)
    - [null literal](#null-literal)
    - [class literal](#class-literal)
    - [Using Underscore Characters in Numeric Literals](#using-underscore-characters-in-numeric-literals)
  - [5.5 Reference Data Types:](#55-reference-data-types)
  - [5.6 Arrays](#56-arrays)
    - [Array Declaration](#array-declaration)
    - [Creating, Initializing, and Accessing an Array](#creating-initializing-and-accessing-an-array)
  - [5.7 Expressions](#57-expressions)
  - [5.8 Statements](#58-statements)
  - [5.9 Blocks](#59-blocks)
  - [5.10 The switch Statement](#510-the-switch-statement)
- [6. Classes](#6-classes)
  - [6.1 Classes Concept](#61-classes-concept)
  - [6.2 Class Overloading Methods](#62-class-overloading-methods)
  - [6.3 Class Default Constructor](#63-class-default-constructor)
  - [6.4 Passing Primitive Data Type Arguments](#64-passing-primitive-data-type-arguments)
  - [6.5 Passing Reference Data Type Arguments](#65-passing-reference-data-type-arguments)
- [7. Objects](#7-objects)
  - [7.1 Object Declaration](#71-object-declaration)
  - [7.2 Creating an Object(Instantiating a Class)](#72-creating-an-objectinstantiating-a-class)
  - [7.3 Initializing an Object](#73-initializing-an-object)
  - [7.4 Garbage Collection](#74-garbage-collection)
    - [The ways of dropping object reference](#the-ways-of-dropping-object-reference)
  - [7.5 Class or Interface type as return types](#75-class-or-interface-type-as-return-types)
  - [7.6 Using this with a Constructor](#76-using-this-with-a-constructor)
  - [7.7 Controlling Access to Members of a Class](#77-controlling-access-to-members-of-a-class)
    - [Member Access Levels](#member-access-levels)
    - [Tips on Choosing an Access Level](#tips-on-choosing-an-access-level)
  - [7.8 Class Variables(static field)](#78-class-variablesstatic-field)
  - [7.9 static methods](#79-static-methods)
  - [7.10 Constants](#710-constants)
  - [7.11 Nested Classes](#711-nested-classes)
    - [Non-static nested class(inner classes)](#non-static-nested-classinner-classes)
    - [Static nested classes](#static-nested-classes)
    - [Shadowing](#shadowing)
    - [Serialization](#serialization)
  - [7.12 local classes](#712-local-classes)
  - [7.13 anonymous classes](#713-anonymous-classes)
  - [7.14 Functional interface](#714-functional-interface)
  - [7.15 lambda expressions](#715-lambda-expressions)
    - [Syntax of Lambda Expressions](#syntax-of-lambda-expressions)
    - [lambda expression does not introduce a new level of scoping](#lambda-expression-does-not-introduce-a-new-level-of-scoping)
    - [Serialization](#serialization-1)
  - [7.16 Method References](#716-method-references)
  - [7.17 Enum Types](#717-enum-types)
- [8. Annotations](#8-annotations)
  - [Annotations uses](#annotations-uses)
- [9. Interface](#9-interface)
  - [The Interface Body](#the-interface-body)
  - [Using an Interface as a Type](#using-an-interface-as-a-type)
  - [Default method](#default-method)
  - [Static method](#static-method)
- [10. Inheritance](#10-inheritance)
  - [Casting Objects](#casting-objects)
  - [Overriding and Hiding Methods](#overriding-and-hiding-methods)
    - [Instance Methods](#instance-methods)
    - [Static Methods](#static-methods)
      - [Overriding an instance method vs Hiding a static method](#overriding-an-instance-method-vs-hiding-a-static-method)
    - [Interface Methods](#interface-methods)
      - [The **inheritance rules** to resolve the **name conflict** when the supertypes of a class or interface **provide multiple** default methods with the **same signature**](#the-inheritance-rules-to-resolve-the-name-conflict-when-the-supertypes-of-a-class-or-interface-provide-multiple-default-methods-with-the-same-signature)
    - [Modifiers](#modifiers)
    - [Defining a Method with the Same Signature as a Superclass's Method](#defining-a-method-with-the-same-signature-as-a-superclasss-method)
    - [Overload VS Override](#overload-vs-override)
    - [Extends vs implements](#extends-vs-implements)

# 1. Java Concept
* [Java Conceptual Diagram](https://docs.oracle.com/javase/8/docs/index.html)
* Java SE is means "Java Platform, Standard Edition"
* JDK VS JRE
  * Oracle has two products that implement Java SE: Java SE Development Kit (JDK) and Java SE Runtime Environment (JRE).
  * JDK is a superset of JRE, and contains everything that is in JRE, plus tools such as the compilers and debuggers necessary for developing applets and applications.
  * JRE provides the libraries, the Java Virtual Machine (JVM), and other components to run applets and applications written in the Java programming language.
  * Note that the JRE includes components not required by the Java SE specification, including both standard and non-standard Java components.
* JVM VS HotSpot Virtual Machine
  * JVM is means Java Virtual Machine, is also a Specification.
  * HotSpot Virtual Machine is a implementation production of JVM.

# 2. Documents And Specifications
* [Java SE(Java Platform, Standard Edition) Documentation](https://docs.oracle.com/en/java/javase/20/)
* [The Java Tutorials](https://docs.oracle.com/javase/tutorial/tutorialLearningPaths.html)
* [The Java Language Specification, Java SE 20 Edition](https://docs.oracle.com/javase/specs/jls/se20/html/index.html)
* [The Java Virtual Machine Specification, Java SE 20 Edition](https://docs.oracle.com/javase/specs/jvms/se20/html/index.html)
* [Java® Platform, Standard Edition & Java Development Kit
  Version 20 API Specification](https://docs.oracle.com/en/java/javase/20/docs/api/index.html)
* [JAR File Specification](https://docs.oracle.com/en/java/javase/20/docs/specs/jar/jar.html)
* [Core Libraries](https://docs.oracle.com/en/java/javase/20/core/java-core-libraries1.html)

# 3. Essential
* **The main Method**: In the Java programming language, every application must contain a main method whose signature is:
```java
public static void main(String[] args)
```

# 4. Learning the Java Language
## What is an Object?
An Object is a software bundle of related state and behavior. Software objects are often used to model the real-world objects that you find in everyday life.
## What is a Class?
A class is a blueprint or prototype from which objects are created. This section defines a class that models the state and behavior of a real-world object.
## What is Inheritance?
Inheritance provides a powerful and natural mechanism for organizing and structuring your software.
## What is an Interface?
An interface is a contract between a class and the outside world. When a class implements an interface, it promises to provide the behavior published by that interface.
## What is a Package?
A package is a namespace for organizing classes and interfaces in a logical manner. Placing your code into packages makes large software projects easier to manage.

# 5. Language Basics

## 5.1 Variables
* Instance Variables (Non-Static Fields)
* Class Variables (Static Fields)
* Local Variables
* Parameters

## 5.2 Naming
* Variable names are case-sensitive.
* Subsequent characters may be letters, digits, dollar signs, or underscore characters.
* If the name you choose consists of only one word, spell that word in all lowercase letters.
* If it consists of more than one word, capitalize the first letter of each subsequent word. The names gearRatio and currentGear are prime examples of this convention.
* If your variable stores a constant value, such as static final int NUM_GEARS = 6, the convention changes slightly, capitalizing every letter and separating subsequent words with the underscore character.

## 5.3 Primitive Data Types
| Date Type | Default Value | type                                                                                                       | Value range                                                                        |
|-----------|---------------|------------------------------------------------------------------------------------------------------------|------------------------------------------------------------------------------------|
| byte      | 0             | 8-bit signed                                                                                               | -128 ~ 127                                                                         |
| short     | 0             | 16-bit signed                                                                                              | -32768 ~ 32767                                                                     |
| int       | 0             | 32-bit signed                                                                                              | -2^31 ~ 2^31-1                                                                     |
| long      | 0L            | 64-bit                                                                                                     | signed long: -2^63 ~ 2^63-1 <br /> In Java SE 8 and late, unsigned long 0 ~ 2^64-1 |
| float     | 0.0f          | single-precision 32-bit IEEE 754 floating point                                                            |                                                                                    |
| double    | 0.0d          | double-precision 64-bit IEEE 754 floating point                                                            |                                                                                    |
| char      | '\u0000'      | single 16-bit Unicode character                                                                            | '\u0000' (or 0) ~ '\uffff' (or 65,535 inclusive)                                   |
| boolean   | false         | This data type represents one bit of information, but its "size" isn't something that's precisely defined. | true and false                                                                     |

> The String class is not technically a primitive data type, but considering the special support given to it by the language, you'll probably tend to think of it as such.

* **The compiler will assign a reasonable default value for fields of the above types(Primitive data types and String); for local variables, a default value is never assigned.**
* Primitive types are special data types built into the language; they are not objects created from a class.

## 5.4 Literals
A literal is the source code representation of a fixed value; literals are represented directly in your code without requiring computation.
### Integer Literals
An integer literal is of type long if it ends with the letter L or l; otherwise it is of type int.
```java
// The number 26, in decimal
int decVal = 26;
//  The number 26, in hexadecimal
int hexVal = 0x1a;
// The number 26, in binary
int binVal = 0b11010;
```
### Floating-Point Literals
A floating-point literal is of type float if it ends with the letter F or f; otherwise its type is double and it can optionally end with the letter D or d.

### Character and String Literals
Literals of types char and String may contain any Unicode (UTF-16) characters.

### null literal
* null can be used as a value for any reference type
* null may be assigned to any variable, **except variables of primitive types**.

### class literal
* TODO

### Using Underscore Characters in Numeric Literals
In Java SE 7 and later, any number of underscore characters (_) can appear anywhere between digits in a numerical literal. This feature enables you, for example. to separate groups of digits in numeric literals, which can improve the readability of your code.
```java
long creditCardNumber = 1234_5678_9012_3456L;
long socialSecurityNumber = 999_99_9999L;
float pi =  3.14_15F;
long hexBytes = 0xFF_EC_DE_5E;
long hexWords = 0xCAFE_BABE;
long maxLong = 0x7fff_ffff_ffff_ffffL;
byte nybbles = 0b0010_0101;
long bytes = 0b11010010_01101001_10010100_10010010;
```

## 5.5 Reference Data Types:
* strings
* arrays
* objects

## 5.6 Arrays
* An array is a container object that holds a fixed number of values of a single type.
* The length of an array is established when the array is created.
* After creation, its length is fixed.

### Array Declaration
An array declaration has two components: the array's **type** and the array's **name**.
```Java
// declares an array of integers
int[] anArray;
```
**The size of the array is not part of its type (which is why the brackets are empty).**

As with variables of other types, the declaration does not actually create an array; it simply tells the compiler that this variable will hold an array of the specified type.

```Java
byte[] anArrayOfBytes;
short[] anArrayOfShorts;
long[] anArrayOfLongs;
float[] anArrayOfFloats;
double[] anArrayOfDoubles;
boolean[] anArrayOfBooleans;
char[] anArrayOfChars;
String[] anArrayOfStrings;
```

### Creating, Initializing, and Accessing an Array
```Java
// create an array of integers
anArray = new int[10];
```

## 5.7 Expressions
- An expression is a construct made up of **variables**, **operators**, and **method invocations**, which are constructed according to the syntax of the language, that evaluates to a **single value**.
- The Java allow you to construct **compound expressions** from **various smaller expressions** as long as the data type required by one part of the expression matches the data type of the other

## 5.8 Statements
A statement forms a complete unit of execution.
- Expression statements
  - The following types of expressions can be made into a statement by terminating the expression with a semicolon (;).
    - Assignment expressions
    - Any use of ++ or --
    - Method invocations
    - Object creation expressions
      ```java
      // assignment statement
      aValue = 8933.234;
      // increment statement
      aValue++;
      // method invocation statement
      System.out.println("Hello World!");
      // object creation statement
      Bicycle myBike = new Bicycle();
      ```
- Declaration statements
  ```java
  // declaration statement
  double aValue = 8933.234;
  ```
- Control flow statements

  control flow statements regulate the order in which statements get executed.

## 5.9 Blocks
A block is a group of zero or more **statements** between **balanced braces** and can be used anywhere a **single statement** is allowed.

## 5.10 The switch Statement
A switch works with the **byte**, **short**, **char**, and **int** primitive data types. It also works with **enumerated types**, the **String** class, and a few special classes that wrap certain primitive types: **Character**, **Byte**, **Short**, and **Integer**

<br>

# 6. Classes
## 6.1 Classes Concept
* **Modifiers**: public, private(**The private modifier can only be applied to Nested Classes**)
* **interfaces**: A class can implement more than one interface.
* **Inherience**: A class can only extend (subclass) one parent.
## 6.2 Class Overloading Methods
* Method signatures: Method Name + parameter lists
* Class Overloading Methods means that methods within a class can have the same name if they have different parameter lists.
* The compiler does not consider return type when differentiating methods, so you cannot declare two methods with the same signature even if they have a different return type.
## 6.3 Class Default Constructor
If you don't have to provide any constructors for your class, the compiler automatically provides a no-argument, default constructor for any class without constructors. **It means all classes have a least one constructor**.
* **No-argument constructor** is not always a Default Constructor, but a Default Constructor is must be a No-argument constructor.
* Default constructor will call the no-argument constructor of the superclass.
  * In default constructor, the compiler will complain if the superclass doesn't have a no-argument constructor so you must verify that it does
  * If your class has no explicit superclass, then it has an implicit superclass of Object, which does have a no-argument constructor.

## 6.4 Passing Primitive Data Type Arguments
Primitive arguments, such as an int or a double, are passed into methods by value.
## 6.5 Passing Reference Data Type Arguments
Reference data type parameters, such as objects, are also passed into methods by value.
* However, the values of the object's fields can be changed in the method, if they have the proper access level.
```java
public class Main {
  public static class A {
    public int x = 0;
    public int y = 0;
    public A(int x, int y) {
      this.x = x;
      this.y = y;
    }
  }

  public static void passReferenceType(A a) {
    a.x += 1;
    a.y += 1;
    a = new A(1, 2);
  }

  public static void main(String[] args) {
    A a = new A(10, 11);
    passReferenceType(a);
    System.out.printf("x: %d, y: %d", a.x, a.y);
    // print "x: 11, y: 12"
  }
}
```

# 7. Objects
## 7.1 Object Declaration
```java
type name;
```
This notifies the compiler that you will use name to refer to data whose type is type.
* With a **primitive variable**, this declaration also reserves the proper amount of memory for the variable.
* With a **reference variable**, this declaration does not create an object.
## 7.2 Creating an Object(Instantiating a Class)
* The new operator instantiates a class by allocating memory for a new object and returning a reference to that memory.
## 7.3 Initializing an Object
...

## 7.4 Garbage Collection
The **Java runtime environment** deletes objects when it determines that they are no longer being used.
### The ways of dropping object reference
* Automatically: References that are held in a variable are usually dropped when the variable goes out of scope.
* Manually: Explicitly drop an object reference by setting the variable to the special value **null**.

**Note: [Garbage Collection is not part of the JVM specification](https://forums.oracle.com/ords/apexds/post/a-jvm-without-garbage-collection-is-it-possible-1309)**

## 7.5 Class or Interface type as return types
* Class names as return types: the class of the type of the returned object must be either a subclass of, or the exact class of, the return type.
* Interface names as return types: the object returned must implement the specified interface.

## 7.6 Using this with a Constructor
```java
public class Rectangle {
    private int x, y;
    private int width, height;
        
    public Rectangle() {
        this(0, 0, 1, 1); // the invocation of another constructor must be the first line in the constructor.
    }
    public Rectangle(int width, int height) {
        this(0, 0, width, height);
    }
    public Rectangle(int x, int y, int width, int height) {
        this.x = x;
        this.y = y;
        this.width = width;
        this.height = height;
    }
    // ...
}
```

## 7.7 Controlling Access to Members of a Class
| level               | items                                                                 |
|---------------------|-----------------------------------------------------------------------|
| Top Access level    | public, or package-private (no explicit modifier)                     |
| Member Access level | public, private, protected, or package-private (no explicit modifier) |

* Modifier public, in which case that class is visible to all classes everywhere.
* If a class has no modifier (the default, also known as package-private), it is visible only within its own package

### Member Access Levels
| Modifier                     | Class | Package | Subclass | World |
|------------------------------|-------|---------|----------|-------|
| public                       | Y     | Y       | Y        | Y     |
| protected                    | Y     | Y       | Y        | N     |
| package-private(no modifier) | Y     | Y       | N        | N     |
| private                      | Y     | N       | N        | N     |
* private: the private modifier specifies that the member can only be accessed in its own class.
* protected: the protected modifier specifies that the member can only be accessed within **its own package (as with package-private)** and, in addition, **by a subclass of its class in another package**.

### Tips on Choosing an Access Level
* Use the most restrictive access level that makes sense for a particular member. Use private unless you have a good reason not to.
* Avoid public fields except for constants. Public fields tend to link you to a particular implementation and limit your flexibility in changing your code.

## 7.8 Class Variables(static field)
Fields that have the static modifier in their declaration are called static fields or class variables.
## 7.9 static methods
Static methods, which have the static modifier in their declarations, should be invoked with the class name, without the need for creating an instance of the class, as in
```java
ClassName.methodName(args)
```
**Note: You can also refer to static methods and static field with an object reference like**
```java
instanceName.staticMethodName(args);
instanceName.staticFieldName;
```
but this is discouraged.

## 7.10 Constants
The static modifier, in combination with the final modifier, is also used to define constants.
> Note: If a primitive type or a string is defined as a constant and the value is known at compile time, the compiler replaces the constant name everywhere in the code with its value. This is called a compile-time constant. If the value of the constant in the outside world changes (for example, if it is legislated that pi actually should be 3.975), you will need to recompile any classes that use this constant to get the current value.

## 7.11 Nested Classes
### Non-static nested class(inner classes)
* In Java 8, it isn't allowed to define or declare any static members, Except **static constant variables**.
* But Since **Java 16**, it's allowed to define or declare static members either explicitly or implicitly.
```java
class OuterClass {
    ...
    class InnerClass {
        ...
    }
    public void fn() {
      InnerClass obj = new InnerClass();
    }
}
OuterClass outerObject = new OuterClass();
OuterClass.InnerClass innerObject = outerObject.new InnerClass();
```

### Static nested classes
```java
public class OuterClass {

    private int outerPrivateNum = 1;
    String outerField = "Outer field";
    static String staticOuterField = "Static outer field";

    class InnerClass {
        void accessMembers() {
            System.out.println(outerField);
            System.out.println(staticOuterField);
        }
    }

    static class StaticNestedClass {
        void accessMembers(OuterClass outer) {
            // Compiler error: Cannot make a static reference to the non-static field outerField
            // System.out.println(outerField);
            System.out.println(outer.outerField);
            System.out.println(staticOuterField);
            System.out.println(outer.outerPrivateNum);
        }
    }

    public static void main(String[] args) {
        System.out.println("Inner class:");
        System.out.println("------------");
        OuterClass outerObject = new OuterClass();
        OuterClass.InnerClass innerObject = outerObject.new InnerClass();
        innerObject.accessMembers();

        System.out.println("\nStatic nested class:");
        System.out.println("--------------------");
        StaticNestedClass staticNestedObject = new StaticNestedClass();        
        staticNestedObject.accessMembers(outerObject);
        
        System.out.println("\nTop-level class:");
        System.out.println("--------------------");
        TopLevelClass topLevelObject = new TopLevelClass();        
        topLevelObject.accessMembers(outerObject);                
    }
}
class TopLevelClass {
  void accessMembers(OuterClass outer) {     
      // Compiler error: Cannot make a static reference to the non-static field OuterClass.outerField
      // System.out.println(OuterClass.outerField);
      System.out.println(outer.outerPrivateNum);
      System.out.println(OuterClass.staticOuterField);
  }
}
```
### Shadowing
You cannot refer to a shadowed declaration by its name alone.
```java
public class ShadowTest {
    public int x = 0;

    class FirstLevel {
        public int x = 1;
        void methodInFirstLevel(int x) {
            System.out.println("x = " + x);
            System.out.println("this.x = " + this.x);
            System.out.println("ShadowTest.this.x = " + ShadowTest.this.x);
        }
    }

    public static void main(String... args) {
        ShadowTest st = new ShadowTest();
        ShadowTest.FirstLevel fl = st.new FirstLevel();
        fl.methodInFirstLevel(23);
    }
}
// x = 23
// this.x = 1
// ShadowTest.this.x = 0
```
### Serialization
Serialization of inner classes, including local and anonymous classes, is strongly discouraged.

## 7.12 local classes
Local classes are classes that are defined in a block, which is a group of zero or more statements between balanced braces. You typically find local classes defined in the body of a method.
* Can define a local class inside **any [block](#59-blocks)** .
* Can't access **local variables** in its enclosing scope that are not declared as **final** or **effectively final**.
* In Java 8, it isn't allowed to define or declare any static members, **Except static constant variables.**
* But Since [Java 16](https://openjdk.org/jeps/395), it's allowed to define or declare static members either explicitly or implicitly.
* You cannot declare an **[interface](#9-interface)** inside a block; **interfaces are inherently static**.
* Can't contains any of the **access modifiers public, protected, or private**, or the **modifier static**.

## 7.13 anonymous classes
* Can access to the members of its enclosing class.
* Cannot access **local variables** in its enclosing scope that are not declared as **final** or **effectively final**.
* In Java 8, it isn't allowed to define or declare any static members, Except static constant variables.
* But Since Java 16, it's allowed to define or declare static members either explicitly or implicitly.
* **Local classes** can be declared in anonymous classes just as local classes can be defined in any block.
* Anonymous classes cannot have any **constructor**.

## 7.14 Functional interface
A functional interface is any interface that **contains only one abstract method**.

(A functional interface may contain one or more default methods or static methods.)

**Instead of using an anonymous class expression, we use a lambda expression in Functional interface**.

```java
interface CheckPerson  {
  boolean test(Person);
}
void printPersons(List<Person> list, CheckPerson tester) {}
// Two way to invocate printPersons method
// First way: Use anonymous class expression
printPersons(list, new CheckPerson() {
  public boolean test(Person p) {
    return p.getAge() >= 18;
  }
});
// Second Way: Use lambda expression
printPersons(list, (Person p) -> p.getAge() >= 18);
```
## 7.15 lambda expressions
### Syntax of Lambda Expressions
  * A comma-separated list of formal parameters enclosed in parentheses
  * The arrow token, ->
  * A body, which consists of a single expression or a statement block. This example uses the following expression:
    ```java
    p.getGender() == Person.Sex.MALE 
      && p.getAge() >= 18
      && p.getAge() <= 25
    ```
    If you specify a single expression, then the Java runtime evaluates the expression and then returns its value. Alternatively, you can use a return statement:
    ```java
    p -> {
    return p.getGender() == Person.Sex.MALE
    && p.getAge() >= 18
    && p.getAge() <= 25;
    }
    ```
  * A return statement is not an expression; in a lambda expression, you must enclose statements in braces (**{}**).

    However, you do not have to enclose a **void method invocation** in braces. For example, the following is a valid lambda expression:
    ```java
    email -> System.out.println(email)
    ```

### lambda expression does not introduce a new level of scoping
  * Do not have any shadowing issues
  * **Lexically scoped**: this means that they do not inherit any names from a supertype or introduce a new level of scoping
  * Declarations in a lambda expression are interpreted just as they are in the enclosing environment.
    ```java
    public class Main {
      interface IntegerMath {
        int operation(int a, int b);
      }
      private final int fieldOne = 1;
      public void fn() {
        int z1 = 1;
        int a = 2;
        IntegerMath addtion = (a, b) -> a + b + z1 + this.fieldOne; // Compile error: Variable 'a' is already defined in the scope
      }
    }
    ```

  * Consequently, you can **directly access** fields, methods, and local variables of the enclosing scope.
  * Like local and anonymous classes, a lambda expression can only access **local variables** and **parameters** of the enclosing block that are **final** or **effectively final**.
    ```java
    public class Main {
        interface IntegerMath {
            int operation();
        }
        public void fn() {
            int z1 = 1;
            int z2 = 2;
            IntegerMath addtion = () -> {
                z2 = 3; // Compile error: Variable z2 used in lambda expression should be final or effectively final
                return z1; // Compile error: Variable z1 used in lambda expression should be final or effectively final
            };
            z1 = 2;
        }
    }
    ```
* Target Types and Method Arguments
  For method arguments, the Java compiler determines the target type with two other language features: **overload resolution** and **type argument inference**.
  ```java
  public interface Runnable {
      void run();
  }

  public interface Callable<V> {
      V call();
  }
  ```
  Suppose that you have overloaded the method invoke as follows (see Defining Methods for more information about overloading methods):
  ```java
  void invoke(Runnable r) {
      r.run();
  }

  <T> T invoke(Callable<T> c) {
      return c.call();
  }
  ```
  Which method will be invoked in the following statement?
  ```java
  String s = invoke(() -> "done");
  ```
  The method invoke(Callable<T>) will be invoked because that method returns a value; the method invoke(Runnable) does not. In this case, the type of the lambda expression () -> "done" is Callable<T>.

### Serialization

  You can serialize a lambda expression if its **target type** and its **captured arguments** are **serializable**. However, like inner classes, the serialization of lambda expressions is strongly **discouraged**.

## 7.16 Method References
Replace lambda expression with Method References.
```java
public class Person {
    public static int compareByAge(Person a, Person b) {
        return a.birthday.compareTo(b.birthday);
    }
}
```
The method reference **Person::compareByAge** is semantically the same as the lambda expression **(a, b) -> Person.compareByAge(a, b)**
<br />

There are four kinds of method references:

| Kind | Syntax | Examples |
| --- | --- | --- |
| Reference to a static method | ContainingClass::staticMethodName | Person::compareByAge |
| Reference to an instance method of a particular object | containingObject::instanceMethodName | myApp::appendStrings2 |
| Reference to an instance method of an arbitrary object of a particular type | ContainingType::methodName | String::concat |
| Reference to a constructor | ClassName::new | HashSet::new |

## 7.17 Enum Types
An enum type is a special data type that enables for a variable to be a set of predefined constants.
```java
public enum Day {
    SUNDAY = 1, MONDAY, TUESDAY, WEDNESDAY,
    THURSDAY, FRIDAY, SATURDAY 
}
```
* The enum declaration defines a class (called an enum type).
  * The enum class body can include methods and other fields.
  * The compiler automatically adds some special methods when it creates an enum.
* Note: All enums **implicitly extend java.lang.Enum**. Because a class can only extend one parent. So **no explicitly extends** clause allowed for enum.

```java
enum Day {
    ONE(1, "one"),
    TWO(2, "two");

    private final int value;
    private final String name;
    private Day(int val, String name) {
        this.value = val;
        this.name = name;
    }
    public int getValue() {
        return this.value;
    }
    public String getName() {
        return this.name;
    }
}

public class Main {
    public static void main(String[] args) {
        for (Day i : Day.values()) {
            System.out.printf("name: %s value: %d\n", i.getName(), i.getValue());
        }
    }
}
```

**Note The constructor for an enum type must be package-private or private access.**
* It automatically creates the constants that are defined at the beginning of the enum body.
* You cannot invoke an enum constructor yourself.


# 8. Annotations
* Annotations, a form of metadata, provide data about a program that is not part of the program itself.
* Annotations have no direct effect on the operation of the code they annotate.

## Annotations uses
* Information for the compiler — Annotations can be used by the compiler to detect errors or suppress warnings.
* Compile-time and deployment-time processing — Software tools can process annotation information to generate code, XML files, and so forth.
* Runtime processing — Some annotations are available to be examined at runtime.

# 9. Interface
An interface is a **reference data type**, similar to a class, that can contain only **constants, abstract method, default methods, static methods, and nested types**.
* Method bodies exist only for **default methods** and **static methods**.
* Interfaces cannot be instantiated, they can only be implemented by classes or extended by other interfaces.
* An interface can extend any number of interfaces.
  ```java
  public interface MainInterface extends OneInterface, SecondInterface {
  
  }
  ```

## The Interface Body
* The interface body can contain **abstract methods**, **default methods**, **static methods** and **constant declarations**.
* All abstract, default, and static methods in an interface are **implicitly public**, so you can omit the public modifier.
* **An interface can contain constant declarations**. All constant values defined in an interface are **implicitly public, static, and final**. Once again, you can omit these modifiers.
```java
interface A {
    // Implicitly final, static and public
    int a = 101;
    // Abstract method
    void abstractMethod();
    // Default method
    default void defaultMethod() {
        System.out.printf("%d == %d", this.a, A.a);
    }

    // Static Method
    static void staticMethod() {
        System.out.println("interface A: " + A.a);
    }
}
```

## Using an Interface as a Type
* Using an Interface as return type
  ```java
  interface A {}
  public class Main {
    public A returnType() {
      return a; // a is an instance of a class that implments the A interface.
    } 
  }
  ```
* Using an Interface as variable type
  ```java
  interface A {}
  class B implements A {}
  public class Main {
    public static void main(String[] args) {
      A a = new B(); // a is an instance of a class that implments the A interface.
    } 
  }
  ```
## Default method
**Extend an interface** that contains a default method, you can do the following:
* Not mention the default method at all, which lets your extended interface **inherit** the default method.
* Redeclare the default method, which makes it abstract.
* Redefine the default method, which **overrides** it. (Can use @Override annotation)
```java
interface A {
  default void fnOne() {}
  default void fnTwo() {}
  void fnThree();
}
interface B extends A {
  @Override
  void fnOne(); // makes it abstract
  @Override
  default void fnTwo() {
    // Do other implement
  }
  @Override
  default void fnThree() { // overrides it
    // 
  }
}
```

> Default methods enable you to add new functionality to existing interfaces and ensure binary compatibility with code written for older versions of those interfaces.

## Static method
Note: **Static methods in interfaces are never inherited**, but static methods in Class can be inherited.

# 10. Inheritance
Excepting Object, which has no superclass, every class has one and only one direct superclass (single inheritance). In the absence of any other explicit superclass, every class is implicitly a subclass of **Object**.
* A subclass inherits all the members (fields, methods, and nested classes) from its superclass.
* **Constructors are not members, so they are not inherited by subclasses**, but the constructor of the superclass can be invoked from the subclass.
* You can write a subclass constructor that invokes the constructor of the superclass, either implicitly or by using the keyword super.
  ```java
  class A {
    A() {
      supper(); // The supper is refer to Object.
    }
  }
  ```

## Casting Objects
```java
class A {
    public void fn() {}
}
class B {}
Object objA = new A();
Object objB = new B();
A objOne = objA;       // Get a compile-time error
A objTwo = (A) objA;   // OK
objOne.fn();           // OK
// No compile-time error, bug get a runtime error.
// Because this cast inserts a runtime check that objB is assigned the A type,
// so that the compiler can safely assume that objB is A type.
// If objB is not the A type at runtime, an exception will be thrown.
A objThree = (A) objB;
objThree.fn();         // It will not run, because of the above statement throw an exception.
```
**Note** You can make a logical test as to the type of a particular object using the instanceof operator. This can save you from a runtime error owing to an improper cast. For example:
```java
if (objB instanceof A) {
    A objThree = (A) objB;
}
```

## Overriding and Hiding Methods
### Instance Methods
An instance method in a subclass with the **same signature** (name, plus the number and the type of its parameters) and **return type** as an instance method in the superclass overrides the superclass's method.
* If an instance method in a subclass with the **different signature**, it just **overload** an instance method in the superclass.
* An overriding method can also **return a subtype** of the type returned by the overridden method. This subtype is called a **covariant return type**.
```java
class A {}
class B extends A {}
class SupperClass {
  public A print() { return new A(); }
}
class SubClass extends SupperClass {
  @Override
  public B print() { return new B(); }
}
```
### Static Methods
If a subclass defines a static method with the same signature as a static method in the superclass, then the method in the subclass hides the one in the superclass.
```java
class SupperClass {
    public static void print() {
        System.out.println("from SupperClass");
    }
}
class SubClass extends SupperClass {
    public static void print() {
        System.out.println("from SubClass");
    }
    void fn() {
        print(); // from SubClass
        SupperClass.print(); // from SupperClass
    }
}
```
#### Overriding an instance method vs Hiding a static method
* The version of the overridden instance method that gets invoked is the one in the subclass.
* The version of the hidden static method that gets invoked depends on whether it is invoked from the superclass or the subclass.

### Interface Methods
**Default methods** and **abstract methods** in interfaces are **inherited** like instance methods.
#### The **inheritance rules** to resolve the **name conflict** when the supertypes of a class or interface **provide multiple** default methods with the **same signature**
* Instance methods are preferred over interface default methods.
```java
public class Horse {
  public String identifyMyself() {
    return "I am a horse.";
  }
}
public interface Flyer {
  default public String identifyMyself() {
    return "I am able to fly.";
  }
}
public interface Mythical {
  default public String identifyMyself() {
    return "I am a mythical creature.";
  }
}
public class Pegasus extends Horse implements Flyer, Mythical {
  public static void main(String... args) {
    Pegasus myApp = new Pegasus();
    System.out.println(myApp.identifyMyself()); // I am a horse.
  }
}
```
* Methods that are already overridden by other candidates are ignored. This circumstance can arise when supertypes share a common ancestor.
```java
interface Animal {
  default public String identifyMyself() {
    return "I am an animal";
  }
}
interface EggLayer extends Animal {
  default public String identifyMyself() {
    return "I am an egg";
  }
}
interface FireBreather extends Animal {}
public class Dragon implements EggLayer, FireBreather {
  public void main(String... args) {
    Dragon dg = new Dragon();
    System.out.println(dg.identifyMyself()); // I am an egg
  }
}
```
* If two or more independently defined **default methods conflict**, or a **default method conflicts with an abstract method**, then the Java compiler produces a compiler error. You must explicitly override the supertype methods.
```java
public interface OperateCar {
    default public int startEngine(EncryptedKey key) {
        // Implementation
    }
}
public interface FlyCar {
    default public int startEngine(EncryptedKey key) {
        // Implementation
    }
}
public class FlyingCar implements OperateCar, FlyCar {
    public int startEngine(EncryptedKey key) {
        FlyCar.super.startEngine(key);
        OperateCar.super.startEngine(key);
    }
}
```
> The name preceding **super** (in this example, FlyCar or OperateCar) must refer to a direct super interface that defines or inherits a default for the invoked method. 
* ***Inherited** instance methods from classes can **override** abstract interface methods
```java
public interface Mammal {
    String identifyMyself();
}
public class Horse {
    public String identifyMyself() {
        return "I am a horse.";
    }
}
public class Mustang extends Horse implements Mammal {
    public static void main(String... args) {
        Mustang myApp = new Mustang();
        System.out.println(myApp.identifyMyself()); // I am a horse.
    }
}
```
The method Mustang.identifyMyself returns the string I am a horse. The class Mustang inherits the method identifyMyself from the class Horse, which overrides the abstract method of the same name in the interface Mammal.
> **Note: Static methods in interfaces are never inherited**, but static methods in Class can be inherited.

### Modifiers
* The **access specifier** for an **overriding** method **can allow more, but not less**, access than the overridden method.
  * For example, a protected instance method in the superclass can be made public, but not private, in the subclass.
* You will get a compile-time error if you attempt to change an **instance method in the superclass** to a **static method in the subclass**, and vice versa.

### Defining a Method with the Same Signature as a Superclass's Method
| Type                     | Superclass Instance Method     | Superclass Static Method       |
|--------------------------|--------------------------------|--------------------------------|
| Subclass Instance Method | Overrides                      | Generates a compile-time error |
| Subclass Static Method   | Generates a compile-time error | 	Hides                        |

### Overload VS Override
Note: In a subclass, you can overload the methods inherited from the superclass. Such overloaded methods neither hide nor override the superclass instance methods—they are new methods, unique to the subclass.

### Extends vs implements
> extends should go before implements
```java
interface InterA {
  abstract void fn();
  abstract void fnTwo();
}
class ClassA {
  public void fn() {}
}
class ClassB extends ClassA implements InterA {
  @Override
  public void fnTwo() {}
}
```
<br />

https://www.freecodecamp.org/chinese/news/a-quick-intro-to-dependency-injection-what-it-is-and-when-to-use-it/
https://www.freecodecamp.org/chinese/news/solid-principles/
https://docs.oracle.com/javase/tutorial/java/IandI/defaultmethods.html
