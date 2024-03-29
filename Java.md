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
  - [5.5 Reference Data Types](#55-reference-data-types)
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
  - [7.10 static initializers](#710-static-initializers)
  - [7.11 Constants](#711-constants)
  - [7.12 Nested Classes](#712-nested-classes)
    - [Non-static nested class(inner classes)](#non-static-nested-classinner-classes)
    - [Static nested classes](#static-nested-classes)
    - [Shadowing](#shadowing)
    - [Serialization](#serialization)
  - [7.13 local classes](#713-local-classes)
  - [7.14 anonymous classes](#714-anonymous-classes)
  - [7.15 Functional interface](#715-functional-interface)
  - [7.16 lambda expressions](#716-lambda-expressions)
    - [Syntax of Lambda Expressions](#syntax-of-lambda-expressions)
    - [lambda expression does not introduce a new level of scoping](#lambda-expression-does-not-introduce-a-new-level-of-scoping)
    - [Serialization](#serialization-1)
  - [7.17 Method References](#717-method-references)
  - [7.18 Enum Types](#718-enum-types)
  - [7.19 Record](#719-record)
    - [Compact Constructors](#compact-constructors)
    - [Restrictions on Records](#restrictions-on-records)
- [8. Annotations](#8-annotations)
  - [Annotations uses](#annotations-uses)
  - [Type Annotations](#type-annotations)
- [9. Interface](#9-interface)
  - [The Interface Body](#the-interface-body)
  - [Using an Interface as a Type](#using-an-interface-as-a-type)
  - [Default method](#default-method)
  - [Static method](#static-method)
- [10. Inheritance](#10-inheritance)
  - [10.1 Casting Objects](#101-casting-objects)
  - [10.2 Overriding and Hiding Methods](#102-overriding-and-hiding-methods)
    - [10.2.1 Instance Methods](#1021-instance-methods)
    - [10.2.2 Static Methods](#1022-static-methods)
      - [Overriding an instance method vs Hiding a static method](#overriding-an-instance-method-vs-hiding-a-static-method)
    - [10.2.3 Interface Methods](#1023-interface-methods)
      - [The **inheritance rules** to resolve the **name conflict** when the supertypes of a class or interface **provide multiple** default methods with the **same signature**](#the-inheritance-rules-to-resolve-the-name-conflict-when-the-supertypes-of-a-class-or-interface-provide-multiple-default-methods-with-the-same-signature)
    - [10.2.4 Modifiers](#1024-modifiers)
    - [10.2.5 Defining a Method with the **Same Signature** as a Superclass's Method](#1025-defining-a-method-with-the-same-signature-as-a-superclasss-method)
    - [10.2.6 Overload VS Override](#1026-overload-vs-override)
    - [10.2.7 Extends vs implements](#1027-extends-vs-implements)
  - [10.3 Object as a Superclass](#103-object-as-a-superclass)
    - [10.3.1 The finalize() Method](#1031-the-finalize-method)
  - [10.4 Final](#104-final)
  - [10.5 abstract class](#105-abstract-class)
- [11. Packages](#11-packages)
  - [11.1 Naming Conventions](#111-naming-conventions)
  - [11.2 Using Package Members](#112-using-package-members)
    - [Packages are **not hierarchical**](#packages-are-not-hierarchical)
    - [The Static Import Statement](#the-static-import-statement)
  - [11.3 CLASSPATH System Variable](#113-classpath-system-variable)
- [12. Exception](#12-exception)
  - [12.1 The Catch or Specify Requirement](#121-the-catch-or-specify-requirement)
  - [12.2 The Three Kinds of Exceptions](#122-the-three-kinds-of-exceptions)
  - [12.3 Catching More Than One Type of Exception with One Exception Handler](#123-catching-more-than-one-type-of-exception-with-one-exception-handler)
  - [12.4 The finally Block](#124-the-finally-block)
  - [12.5 The try-with-resources Statement](#125-the-try-with-resources-statement)
    - [12.5.1 The order](#1251-the-order)
    - [12.5.2 Suppressed Exceptions](#1252-suppressed-exceptions)
    - [12.5.3 Retrieve suppressed exceptions](#1253-retrieve-suppressed-exceptions)
  - [12.6 Chained Exceptions](#126-chained-exceptions)
  - [12.7 unchecked exceptions](#127-unchecked-exceptions)
    - [12.7.1 Why should specify checked exceptions in method's API?](#1271-why-should-specify-checked-exceptions-in-methods-api)
    - [12.7.2 Why not specify runtime exceptions in method's API?](#1272-why-not-specify-runtime-exceptions-in-methods-api)
    - [12.7.3 How to use RuntimeException properly?](#1273-how-to-use-runtimeexception-properly)
    - [12.7.4 Choose unchecked exception or checked exception](#1274-choose-unchecked-exception-or-checked-exception)
- [13. Java Bean](#13-java-bean)
  - [13.1 What's the Java Bean?](#131-whats-the-java-bean)
  - [13.2 JavaBeans guidelines](#132-javabeans-guidelines)
  - [13.3 JavaBeans Properties](#133-javabeans-properties)
  - [13.4 Advantages](#134-advantages)
  - [13.5 Disadvantages](#135-disadvantages)
- [14 Reflection](#14-reflection)
- [15 Generic](#15-generic)
  - [15.1 Type Parameter and Type Argument Terminology](#151-type-parameter-and-type-argument-terminology)
  - [15.2 Parameterized Types](#152-parameterized-types)
  - [15.3 Raw Types](#153-raw-types)
  - [15.4 Bounded Type Parameters](#154-bounded-type-parameters)
  - [15.5 Generics, Inheritance, and Subtypes](#155-generics-inheritance-and-subtypes)
  - [15.6 Wildcards](#156-wildcards)
    - [15.6.1 Unbounded Wildcards](#1561-unbounded-wildcards)
    - [15.6.2 Wildcards and Subtyping](#1562-wildcards-and-subtyping)
    - [15.6.3 Wildcard Capture and Helper Methods](#1563-wildcard-capture-and-helper-methods)
  - [15.7 Wildcard Guidelines:](#157-wildcard-guidelines)
  - [15.8 Type Erasure](#158-type-erasure)
  - [15.9 Non-Reifiable Types](#159-non-reifiable-types)
    - [Examples](#examples)
  - [15.10 Heap Pollution](#1510-heap-pollution)
  - [15.11 Restrictions on Generics](#1511-restrictions-on-generics)
- [16 Collection](#16-collection)
  - [Collection interface](#collection-interface)
  - [Map interface](#map-interface)
  - [Traversing Collections](#traversing-collections)
    - [Iterator](#iterator)
    - [Use Iterator instead of the for-each construct when you need to](#use-iterator-instead-of-the-for-each-construct-when-you-need-to)
  - [Collection Interface Bulk Operations](#collection-interface-bulk-operations)
  - [Collection Interface Array Operations](#collection-interface-array-operations)
  - [Aggregate operation](#aggregate-operation)
  - [The Set interface and implementations](#the-set-interface-and-implementations)
    - [Set implementations](#set-implementations)
    - [Equals and hashCode operations](#equals-and-hashcode-operations)
  - [The List interface and implementations](#the-list-interface-and-implementations)
    - [Support operations](#support-operations)
    - [Implementations](#implementations)
    - [Equals and hashCode method](#equals-and-hashcode-method)
  - [The Queue Interface and implementations](#the-queue-interface-and-implementations)
    - [Queue implementations generally do not allow insertion of null elements](#queue-implementations-generally-do-not-allow-insertion-of-null-elements)
- [17. Module](#17-module)
- [18. IO](#18-io)
  - [18.1 IO Stream](#181-io-stream)
- [19. POJO](#19-pojo)
- [20. Service Provider Interface (SPI)](#20-service-provider-interface-spi)
  - [20.1 Examples](#201-examples)
  - [20.2 More detailed example](#202-more-detailed-example)

# 1. Java Concept

- [Java Conceptual Diagram](https://docs.oracle.com/javase/8/docs/index.html)
- Java SE is means "Java Platform, Standard Edition"
- JDK VS JRE
  - Oracle has two products that implement Java SE: Java SE Development Kit (JDK) and Java SE Runtime Environment (JRE).
  - JDK is a superset of JRE, and contains everything that is in JRE, plus tools such as the compilers and debuggers necessary for developing applets and applications.
  - JRE provides the libraries, the Java Virtual Machine (JVM), and other components to run applets and applications written in the Java programming language.
  - Note that the JRE includes components not required by the Java SE specification, including both standard and non-standard Java components.
- JVM VS HotSpot Virtual Machine
  - JVM is means Java Virtual Machine, is also a Specification.
  - HotSpot Virtual Machine is a implementation production of JVM.

# 2. Documents And Specifications

- https://docs.oracle.com/javase/8/docs/technotes/guides/
- [Java SE(Java Platform, Standard Edition) Documentation](https://docs.oracle.com/en/java/javase/20/)
- [The Java Tutorials](https://docs.oracle.com/javase/tutorial/tutorialLearningPaths.html)
- [The Java Language Specification, Java SE 20 Edition](https://docs.oracle.com/javase/specs/jls/se20/html/index.html)
- [The Java Virtual Machine Specification, Java SE 20 Edition](https://docs.oracle.com/javase/specs/jvms/se20/html/index.html)
- [Java® Platform, Standard Edition & Java Development Kit
  Version 20 API Specification](https://docs.oracle.com/en/java/javase/20/docs/api/index.html)
- [JAR File Specification](https://docs.oracle.com/en/java/javase/20/docs/specs/jar/jar.html)
- [Core Libraries](https://docs.oracle.com/en/java/javase/20/core/java-core-libraries1.html)
- [**SEI CERT Oracle Coding Standard for Java**](https://wiki.sei.cmu.edu/confluence/pages/viewpage.action?pageId=88487912)

# 3. Essential

- **The main Method**: In the Java programming language, every application must contain a main method whose signature is:

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

- Instance Variables (Non-Static Fields)
- Class Variables (Static Fields)
- Local Variables
- Parameters

## 5.2 Naming

- Variable names are case-sensitive.
- Subsequent characters may be letters, digits, dollar signs, or underscore characters.
- If the name you choose consists of only one word, spell that word in all lowercase letters.
- If it consists of more than one word, capitalize the first letter of each subsequent word. The names gearRatio and currentGear are prime examples of this convention.
- If your variable stores a constant value, such as static final int NUM_GEARS = 6, the convention changes slightly, capitalizing every letter and separating subsequent words with the underscore character.

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

- **The compiler will assign a reasonable default value for fields of the above types(Primitive data types and String); for local variables, a default value is never assigned.**
- Primitive types are special data types built into the language; they are not objects created from a class.

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

- null can be used as a value for any reference type
- null may be assigned to any variable, **except variables of primitive types**.

### class literal

- TODO

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

## 5.5 Reference Data Types

- strings
- arrays
- objects

## 5.6 Arrays

- An array is a container object that holds a fixed number of values of a single type.
- The length of an array is established when the array is created.
- After creation, its length is fixed.

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

- **Modifiers**: public, private(**The private modifier can only be applied to Nested Classes**)
- **interfaces**: A class can implement more than one interface.
- **Inherience**: A class can only extend (subclass) one parent.

## 6.2 Class Overloading Methods

- Method signatures: Method Name + parameter lists
- Class Overloading Methods means that methods within a class can have the same name if they have different parameter lists.
- The compiler does not consider return type when differentiating methods, so you cannot declare two methods with the same signature even if they have a different return type.

## 6.3 Class Default Constructor

If you don't have to provide any constructors for your class, the compiler automatically provides a no-argument, default constructor for any class without constructors. **It means all classes have a least one constructor**.

- **No-argument constructor** is not always a Default Constructor, but a Default Constructor is must be a No-argument constructor.
- Default constructor will call the no-argument constructor of the superclass.
  - In default constructor, the compiler will complain if the superclass doesn't have a no-argument constructor so you must verify that it does
  - If your class has no explicit superclass, then it has an implicit superclass of **Object**, which does have a no-argument constructor.

## 6.4 Passing Primitive Data Type Arguments

Primitive arguments, such as an int or a double, are passed into methods by value.

## 6.5 Passing Reference Data Type Arguments

Reference data type parameters, such as objects, are also passed into methods by value.

- However, the values of the object's fields can be changed in the method, if they have the proper access level.

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

- With a **primitive variable**, this declaration also reserves the proper amount of memory for the variable.
- With a **reference variable**, this declaration does not create an object.

## 7.2 Creating an Object(Instantiating a Class)

- The new operator instantiates a class by allocating memory for a new object and returning a reference to that memory.

## 7.3 Initializing an Object

...

## 7.4 Garbage Collection

The **Java runtime environment** deletes objects when it determines that they are no longer being used.

### The ways of dropping object reference

- Automatically: References that are held in a variable are usually dropped when the variable goes out of scope.
- Manually: Explicitly drop an object reference by setting the variable to the special value **null**.

**Note: [Garbage Collection is not part of the JVM specification](https://forums.oracle.com/ords/apexds/post/a-jvm-without-garbage-collection-is-it-possible-1309)**

## 7.5 Class or Interface type as return types

- Class names as return types: the class of the type of the returned object must be either a subclass of, or the exact class of, the return type.
- Interface names as return types: the object returned must implement the specified interface.

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

- Modifier public, in which case that class is visible to all classes everywhere.
- If a class has no modifier (the default, also known as package-private), it is visible only within its own package

### Member Access Levels

| Modifier                     | Class | Package | Subclass | World |
|------------------------------|-------|---------|----------|-------|
| public                       | Y     | Y       | Y        | Y     |
| protected                    | Y     | Y       | Y        | N     |
| package-private(no modifier) | Y     | Y       | N        | N     |
| private                      | Y     | N       | N        | N     |

- private: the private modifier specifies that the member can only be accessed in its own class.
- protected: the protected modifier specifies that the member can only be accessed within **its own package (as with package-private)** and, in addition, **by a subclass of its class in another package**.

### Tips on Choosing an Access Level

- Use the most restrictive access level that makes sense for a particular member. Use private unless you have a good reason not to.
- Avoid public fields except for constants. Public fields tend to link you to a particular implementation and limit your flexibility in changing your code.

## 7.8 Class Variables(static field)

Fields that have the static modifier in their declaration are called static fields or class variables.

## 7.9 static methods

Static methods, which have the static modifier in their declarations, should be invoked with the class name, without the need for creating an instance of the class, as in

```java
ClassName.methodName(args)~~~~
```

**Note: You can also refer to static methods and static field with an object reference like**

```java
instanceName.staticMethodName(args);
instanceName.staticFieldName;
```

but this is discouraged.


## 7.10 static initializers

A static initialization block is a normal block of code enclosed in braces, { }, and preceded by the static keyword. Here is an example:

```java
static {
    // whatever code is needed for initialization goes here
}
```

A class can have **any number** of static initialization blocks, and they can appear anywhere in the class body. The runtime system guarantees that static initialization blocks are called in **the order that they appear in the source code**.

> A static initializer is executed **when a class is loaded**. Static initializers are used to initialize static variables, which are variables that are shared by all instances of a class.

There is an alternative to static blocks — you can write a private static method:

```java
class Whatever {
    public static varType myVar = initializeClassVariable();
        
    private static varType initializeClassVariable() {

        // initialization code goes here
    }
}
```

## 7.11 Constants

The static modifier, in combination with the final modifier, is also used to define constants.
> Note: If a primitive type or a string is defined as a constant and the value is known at compile time, the compiler replaces the constant name everywhere in the code with its value. This is called a compile-time constant. If the value of the constant in the outside world changes (for example, if it is legislated that pi actually should be 3.975), you will need to recompile any classes that use this constant to get the current value.

## 7.12 Nested Classes

### Non-static nested class(inner classes)

- In Java 8, it isn't allowed to define or declare any static members, Except **static constant variables**.
- But Since **Java 16**, it's allowed to define or declare static members either explicitly or implicitly.

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

## 7.13 local classes

Local classes are classes that are defined in a block, which is a group of zero or more statements between balanced braces. You typically find local classes defined in the body of a method.

- Can define a local class inside **any [block](#59-blocks)** .
- Can't access **local variables** in its enclosing scope that are not declared as **final** or **effectively final**.
- In Java 8, it isn't allowed to define or declare any static members, **Except static constant variables.**
- But Since [Java 16](https://openjdk.org/jeps/395), it's allowed to define or declare static members either explicitly or implicitly.
- In Java 8, you cannot declare an **[interface](#9-interface)** inside a block, because **interfaces are inherently static**(Allowed Since Java 16).
- Can't contains any of the **access modifiers public, protected, or private**, or the **modifier static**.

## 7.14 anonymous classes

- Can access to the members of its enclosing class.
- Cannot access **local variables** in its enclosing scope that are not declared as **final** or **effectively final**.
- In Java 8, it isn't allowed to define or declare any static members, Except static constant variables.
- But Since Java 16, it's allowed to define or declare static members either explicitly or implicitly.
- **Local classes** can be declared in anonymous classes just as local classes can be defined in any block.
- Anonymous classes cannot have any **constructor**.

## 7.15 Functional interface

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

## 7.16 lambda expressions

### Syntax of Lambda Expressions

- A comma-separated list of formal parameters enclosed in parentheses
- The arrow token, ->
- A body, which consists of a single expression or a statement block. This example uses the following expression:

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

- A return statement is not an expression; in a lambda expression, you must enclose statements in braces (**{}**).

    However, you do not have to enclose a **void method invocation** in braces. For example, the following is a valid lambda expression:

    ```java
    email -> System.out.println(email)
    ```

### lambda expression does not introduce a new level of scoping

- Do not have any shadowing issues
- **Lexically scoped**: this means that they do not inherit any names from a supertype or introduce a new level of scoping
- Declarations in a lambda expression are interpreted just as they are in the enclosing environment.

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

- Consequently, you can **directly access** fields, methods, and local variables of the enclosing scope.
- Like local and anonymous classes, a lambda expression can only access **local variables** and **parameters** of the enclosing block that are **final** or **effectively final**.

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

- Target Types and Method Arguments
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

## 7.17 Method References

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

## 7.18 Enum Types

An enum type is a special data type that enables for a variable to be a set of predefined constants.

```java
public enum Day {
    SUNDAY = 1, MONDAY, TUESDAY, WEDNESDAY,
    THURSDAY, FRIDAY, SATURDAY 
}
```

- The enum declaration defines a class (called an enum type).
  - The enum class body can include methods and other fields.
  - The compiler automatically adds some special methods when it creates an enum.
- Note: All enums **implicitly extend java.lang.Enum**. Because a class can only extend one parent. So **no explicitly extends** clause allowed for enum.

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

- It automatically creates the constants that are defined at the beginning of the enum body.
- You cannot invoke an enum constructor yourself.

## 7.19 Record

A record is a restricted form of a class. It’s ideal for "plain data carriers," classes that contain data not meant to be **altered** and only the most fundamental methods such as **constructors** and **accessors**.

```java
record Rectangle(float length, float width) { }
```

A record acquires these members automatically:

- A **private** **final** field for each of its components
- A **public** **read accessor** method for each component with the same name and type of the component; in this example, these methods are Rectangle::length() and Rectangle::width()
- A **public** **constructor** whose signature is derived from the record components list. The constructor initializes each private field from the corresponding argument.
- Implementations of the **equals**() and **hashCode**() methods, which specify that two records are equal if they are of the same type and their corresponding record components are equal
- An implementation of the **toString**() method that includes the string representation of all the record's components, with their names

### Compact Constructors

If you want your record's constructor to do more than initialize its private fields, you can define a custom constructor for the record. However, unlike a class constructor, **a record constructor doesn't have a formal parameter list**; **this is called a compact constructor**.

```java
record HelloWorld(String message) {
    public HelloWorld {
        java.util.Objects.requireNonNull(message);
    }
}
```

### Restrictions on Records

The following are restrictions on the use of records:

- Records cannot **extend** any class
- Records cannot **declare instance fields** (other than the private final fields that correspond to the components of the record component list); any other declared fields must be static
- Records cannot be **abstract**; they are **implicitly final**
- The components of a record are **implicitly final**

Beyond these restrictions, records behave like regular classes:

- You can declare them inside a class; **nested records are implicitly static**
- You can create **generic** records
- Records can implement **interfaces**
- You instantiate records with the **new** keyword
- You can declare in a record's body **static methods, static fields, static initializers, constructors, instance methods, and nested types**
- You can **annotate** records and a record's individual components


# 8. Annotations

- Annotations, a form of metadata, provide data about a program that is not part of the program itself.
- Annotations have no direct effect on the operation of the code they annotate.

## Annotations uses

- Information for the compiler — Annotations can be used by the compiler to detect errors or suppress warnings.
- Compile-time and deployment-time processing — Software tools can process annotation information to generate code, XML files, and so forth.
- Runtime processing — Some annotations are available to be examined at runtime.

## Type Annotations

- primitive type
- String
- Class or an invocation of Class (§4.5)
- enum type
- annotation type
- ...

# 9. Interface

An interface is a **reference data type**, similar to a class, that can contain only **constants, abstract method, default methods, static methods, and nested types**.

- Method bodies exist only for **default methods** and **static methods**.
- Interfaces cannot be instantiated, they can only be implemented by classes or extended by other interfaces.
- An interface can extend any number of interfaces.

  ```java
  public interface MainInterface extends OneInterface, SecondInterface {
  
  }
  ```

## The Interface Body

- The interface body can contain **abstract methods**, **default methods**, **static methods** and **constant declarations**.
- All abstract, default, and static methods in an interface are **implicitly public**, so you can omit the public modifier.
- **An interface can contain constant declarations**. All constant values defined in an interface are **implicitly public, static, and final**. Once again, you can omit these modifiers.

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

- Using an Interface as return type

  ```java
  interface A {}
  public class Main {
    public A returnType() {
      return a; // a is an instance of a class that implments the A interface.
    } 
  }
  ```

- Using an Interface as variable type

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

- Not mention the default method at all, which lets your extended interface **inherit** the default method.
- Redeclare the default method, which makes it abstract.
- Redefine the default method, which **overrides** it. (Can use @Override annotation)

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

Note: **Static methods in interfaces** are never inherited, but **static methods in Class** can be inherited.

# 10. Inheritance

Excepting Object, which has no superclass, every class has one and only one direct superclass (single inheritance). In the absence of any other explicit superclass, every class is implicitly a subclass of **Object**.

- A subclass inherits all the members (fields, methods, and **nested classes**) from its superclass.
- **Constructors are not members, so they are not inherited by subclasses**, but the constructor of the superclass can be invoked from the subclass.
- You can write a subclass constructor that invokes the constructor of the superclass, either implicitly or by using the keyword super.

  ```java
  class A {
    A() {
      supper(); // The supper is refer to Object.
    }
  }
  ```

## 10.1 Casting Objects

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

## 10.2 Overriding and Hiding Methods

### 10.2.1 Instance Methods

An instance method in a subclass with the **same signature** (name, plus the number and the type of its parameters) and **return type*** as an instance method in the superclass overrides the superclass's method.

- If an instance method in a subclass with the **different signature**, it just **overload** an instance method in the superclass.
- An overriding method can also **return a subtype** of the type returned by the overridden method. This subtype is called a **covariant return type**.

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

### 10.2.2 Static Methods

If a subclass defines a static method with the **same signature** as a static method in the superclass, then the method in the subclass hides the one in the superclass.

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

- The version of the overridden instance method that gets invoked is the one in the subclass.
- The version of the hidden static method that gets invoked depends on whether it is invoked from the superclass or the subclass.

### 10.2.3 Interface Methods

**Default methods** and **abstract methods** in interfaces are **inherited** like instance methods.

#### The **inheritance rules** to resolve the **name conflict** when the supertypes of a class or interface **provide multiple** default methods with the **same signature**

- Instance methods are preferred over interface default methods.

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

- Methods that are already overridden by other candidates are ignored. This circumstance can arise when supertypes share a common ancestor.

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

- If two or more independently defined **default methods conflict**, or a **default method conflicts with an abstract method**, then the Java compiler produces a compiler error. You must explicitly override the supertype methods.

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

> The name preceding **super** (in this example, FlyCar or OperateCar) must refer to a direct super **interface** that defines or inherits a default for the invoked method.

- ***Inherited** instance methods from classes can **override** abstract interface methods

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

### 10.2.4 Modifiers

- The **access specifier** for an **overriding** method **can allow more, but not less**, access than the overridden method.
  - For example, a protected instance method in the superclass can be made public, but not private, in the subclass.
- You will get a compile-time error if you attempt to change an **instance method in the superclass** to a **static method in the subclass**, and vice versa.

### 10.2.5 Defining a Method with the **Same Signature** as a Superclass's Method

| Type                     | Superclass Instance Method     | Superclass Static Method       |
|--------------------------|--------------------------------|--------------------------------|
| Subclass Instance Method | Overrides                      | Generates a compile-time error |
| Subclass Static Method   | Generates a compile-time error |  Hides                        |

### 10.2.6 Overload VS Override

Note: In a subclass, you can overload the methods inherited from the superclass. Such overloaded methods neither hide nor override the superclass instance methods—they are new methods, unique to the subclass.

### 10.2.7 Extends vs implements
>
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

## 10.3 Object as a Superclass

### 10.3.1 The finalize() Method

- The Object class provides a callback method, **finalize**(), that may be invoked on an object when it becomes garbage.
- Object's implementation of **finalize**() does nothing—you can override finalize() to do cleanup, such as freeing resources.
- The **finalize**() method may be called **automatically** by the system, but when it is called, or even if it is called, is **uncertain**
  - don't rely on this method to do your cleanup for you.
  - Instead, use a **try-with resources statement** to automatically close your application's resources.
  - [see more](https://docs.oracle.com/javase/8/docs/technotes/guides/vm/gctuning/considerations.html#sthref63)

## 10.4 Final

- Methods called from **constructors** should generally be declared final.
  - If a constructor calls a non-final method, **a subclass may redefine that method** with surprising or undesirable results.

## 10.5 abstract class

- An abstract class is a class that is declared abstract--It **may or may not include abstract methods**.
- Abstract classes cannot be instantiated, but they can be subclassed.
- However, to define a class that **does not implement all of the interface's methods**, provided that the class is declared to be **abstract**.

# 11. Packages

Definition: A package is a grouping of related types providing **access protection** and **name space management**.

## 11.1 Naming Conventions

- Package names are written in **all lower case** to avoid conflict with the names of classes or interfaces.
- Companies use their **reversed Internet domain name** to begin their package names

## 11.2 Using Package Members

- Refer to the member by its fully qualified name

  ```java
  package graphics.Rectangle;
  graphics.Rectangle myRect = new graphics.Rectangle();
  ```

- Import the package member

  ```java
  import graphics.Rectangle;
  Rectangle myRectangle = new Rectangle();
  ```

- Import the member's entire package

  ```java
  import graphics.*;
  Circle myCircle = new Circle();
  ```

- Import the **public nested classes** of an enclosing class

  ```java
  import graphics.Rectangle;
  import graphics.Rectangle.*;
  ```

  **Be aware that the second import statement will not import Rectangle.**
- Automatically imports
  
  the Java compiler automatically imports two entire packages for each source file:
  - (1) the **java.lang** package
  - (2) the **current** package (the package for the current file).

### Packages are **not hierarchical**

- **java.awt.font** are not included in the **java.awt** package.
- Importing **java.awt.\*** does not **import java.awt.color, java.awt.font or any other java.awt.xxxx** packages. It just imports all of the types in the **java.awt** package.

### The Static Import Statement

A static import statement in Java allows you to **import static members of a class** into the current scope

```java
import static <package>.<class>.<static_member>;
import static java.lang.Math.PI;
import static java.lang.Math.*;
```

## 11.3 CLASSPATH System Variable

For example, if <path_two>\classes is your class path, and the package name is

```java
com.example.graphics
```

then the compiler and JVM look for .class files in

```java
<path_two>\classes\com\example\graphics
```

- By default, the compiler and the JVM search the current directory and the JAR file containing the Java platform classes so that these directories are automatically in your class path.
<br />

# 12. Exception

Definition: **An exception is an event**, which occurs during the execution of a program, that **disrupts the normal flow** of the program's instructions.

## 12.1 The Catch or Specify Requirement

The Catch or Specify Requirement means that code that might throw certain exceptions must be enclosed by either of the following:

- A try statement that catches the exception.
- A method that specifies that it can throw the exception.

> Only checked exception is subject to the Catch or Specify Requirement

## 12.2 The Three Kinds of Exceptions

| Kind of exception | Description | Checked by compiler? |
| - | - | - |
|Checked exception | These are exceptional conditions that a well-written application should **anticipate** and **recover** from | Yes |
| Runtime exception | These are exceptional conditions that are internal to the application, and that the application usually cannot anticipate or recover from. These usually indicate programming **bugs**, such as **logic errors** or **improper use** of an API | No |
| Error | These are exceptional conditions that are **external** to the application, and that the application usually cannot anticipate or recover from | No |

Example:
| Kind of Exception  | Example                                                                            |
|--------------------|------------------------------------------------------------------------------------|
| Checked Exception  | FileNotFoundException <br> IOException <br> SQLException                           |
| runtime exceptions | ArithmeticException <br>  NullPointerException <br> ArrayIndexOutOfBoundsException |
| errors             | OutOfMemoryError <br> StackOverflowError                                           |
> **Checked exceptions** are subject to the Catch or Specify Requirement. All exceptions are checked exceptions, except for those indicated by **Error**, **RuntimeException**, and **their subclasses**.

## 12.3 Catching More Than One Type of Exception with One Exception Handler

In Java SE 7 and later, a single catch block can handle more than one type of exception

```java
catch (IOException|SQLException ex) {
  logger.log(ex);
  throw ex;
}
```

**Note**: If a catch block handles more than one exception type, then the catch parameter is **implicitly final**.

## 12.4 The finally Block

- The finally block always executes except that JVM crash or System.exit() is called.
- Even if the **try block** throws an error or returns.
- Even if the **catch block** throws an error or returns.

## 12.5 The try-with-resources Statement

- The try-with-resources statement **ensures** that each resource is closed at the end of the statement
  eg:

  ```java
  static String readFirstLineFromFile(String path) throws IOException {
     try (FileReader fr = new FileReader(path);
          BufferedReader br = new BufferedReader(fr)) {
         return br.readLine();
     }
  }
  ```

- Any object that implements java.lang.**AutoCloseable**, which includes all objects which implement java.io.**Closeable**, can be used as a resource.

### 12.5.1 The order

- Note that the **close methods** of resources are called in the **opposite order of their creation**.
- In a try-with-resources statement, any **catch** or **finally** block is **run after** the resources declared have been **closed**.

```java
class A implements Closeable {
    private final String name;
    A(String name) {
        this.name = name;
    }
    public void doSomething() throws IOException {
        throw new IOException("DoSomething");
    }

    @Override
    public void close() throws RuntimeException {
        System.err.println("close: " + this.name);
        throw new RuntimeException("close error " + this.name);
    }
}

public class Main {
    public static void main(String[] args) {
        try (A a = new A("1"); A b = new A("2")) {
            a.doSomething();
        } catch (Exception error) {
            error.printStackTrace();
        } finally {
            System.err.println("end");
        }
    }
}
// Output:
close: 2
close: 1
java.io.IOException: DoSomething
 at org.example.A.doSomething(Main.java:12)
 at org.example.Main.main(Main.java:25)
 Suppressed: java.lang.RuntimeException: close error 2
  at org.example.A.close(Main.java:18)
  at org.example.Main.~~main~~(Main.java:24)
 Suppressed: java.lang.RuntimeException: close error 1
  at org.example.A.close(Main.java:18)
  at org.example.Main.main(Main.java:24)
end
```

### 12.5.2 Suppressed Exceptions

- An exception can be thrown from the block of code associated with the **try-with-resources statement**.
  
  eg:
  - a.doSomeThing() method
  - a.close() method
- If there are **more than one exception** is thrown from the try block or the try-with-resources statement, then the **first** one exception will be **throwed**, the other exceptions are **suppressed**.
  
  **Note**: If one exception is thrown from the **try block**, then this exception is the **first** one before any other exceptions are thrown from the try-with-resources statement.

```java
// eg1:
public class Main {
    public static void main(String[] args) {
        try (A a = new A("1"); A b = new A("2")) {
        } catch (Exception error) {
            error.printStackTrace();
        } finally {
            System.err.println("end");
        }
    }
}
// Output1:
close: 2
close: 1
java.lang.RuntimeException: close error 2
 at org.example.A.close(Main.java:19)
 at org.example.Main.main(Main.java:26)
 Suppressed: java.lang.RuntimeException: close error 1
  at org.example.A.close(Main.java:19)
  at org.example.Main.main(Main.java:25)
end

// eg2:
public class Main {
    public static void main(String[] args) {
        try (A a = new A("1"); A b = new A("2")) {
          a.doSomething();
        } catch (Exception error) {
            error.printStackTrace();
        } finally {
            System.err.println("end");
        }
    }
}
// Output2:
close: 2
close: 1
catch
java.io.IOException: DoSomething
 at org.example.A.doSomething(Main.java:13)
 at org.example.Main.main(Main.java:26)
 Suppressed: java.lang.RuntimeException: close error 2
  at org.example.A.close(Main.java:19)
  at org.example.Main.main(Main.java:25)
 Suppressed: java.lang.RuntimeException: close error 1
  at org.example.A.close(Main.java:19)
  at org.example.Main.main(Main.java:25)
end
```

### 12.5.3 Retrieve suppressed exceptions

Call the Throwable.getSuppressed method from the exception thrown by the try block.

```java
public class Main {
    public static void main(String[] args) {
        try (A a = new A("1"); A b = new A("2")) {
          a.doSomething();
        } catch (Exception error) {
            error.getSuppressed(); // Retrieve suppressed exceptions
        } finally {
            System.err.println("end");
        }
    }
}
```

## 12.6 Chained Exceptions

With exception chaining, an exception can point to the exception that caused it, which can in turn point to the exception that caused it, and so on.

The following are the methods and constructors in Throwable that support chained exceptions.

```java
Throwable getCause()
Throwable initCause(Throwable)
Throwable(String, Throwable)
Throwable(Throwable)
```

## 12.7 unchecked exceptions

- RuntimeException
- Error
- And their subclasses

### 12.7.1 Why should specify checked exceptions in method's API?

- Any checked Exception that can be thrown by a method is part of the method's **public programming interface**.
- Those who call a method must know about the exceptions that a method can throw so that they can **decide what to do** about them.

### 12.7.2 Why not specify runtime exceptions in method's API?

- Runtime exceptions **can occur anywhere** in a program, and in a typical one they can be very **numerous**.
- Having to add runtime exceptions in every method declaration would **reduce a program's clarity**.
- Thus, the compiler does not require that you **catch or specify runtime exceptions** (although you can).

### 12.7.3 How to use RuntimeException properly?

- One case where it is common practice to throw a **RuntimeException** is when the user calls a method incorrectly.
  - For example, a method can check if one of its arguments is incorrectly null. If an argument is null, the method might throw a NullPointerException, which is an unchecked exception.

### 12.7.4 Choose unchecked exception or checked exception

| Type | When |
| ----| ---- |
|**checked** exception | If a client can reasonably be expected to **recover** from an exception |
| **unchecked** exception | If a client **cannot do anything to recover** from the exception |

# 13. Java Bean

## 13.1 What's the Java Bean?

A bean is a Java class with method names that follow the **JavaBeans guidelines**.

## 13.2 JavaBeans guidelines

- A JavaBean must have a **no-arg constructor**.
- All JavaBean properties must have public **getter** and **setter** methods.
- All JavaBean instance variables should be **private**.
- JavaBeans must be **serializable**.

## 13.3 JavaBeans Properties

| Type                   | Desc                                                                                   |
|------------------------|----------------------------------------------------------------------------------------|
| Normal Properties      | supply public getter and setter methods                                                |
| Indexed Properties     | An indexed property is an array instead of a single value.                             |
| Bound Properties       | A bound property notifies listeners when its value changes.  |
| Constrained Properties | For a constrained property, the bean keeps track of a set of veto listeners.<br/>When a constrained property is about to change, the listeners are consulted about the change.<br/>Any one of the listeners has a chance to veto the change, in which case the property remains unchanged.                                                                                       |

## 13.4 Advantages

| Item             | Desc                                                                                                |
|------------------|-----------------------------------------------------------------------------------------------------|
| Reusability      | JavaBeans can be reused in a variety of applications                                                |
| Extensibility    | JavaBeans can be extended to add new features or functionality                                      |
| Serialization    | JavaBeans can be serialized and deserialized, which makes them easy to save and restore             |
| Persistence      | JavaBeans can be persisted to a database or other persistent storage mechanism                      |
| Interoperability | avaBeans can be used with other Java technologies, such as JavaServer Pages (JSP) and Java Servlets |

## 13.5 Disadvantages

| Item       | Desc                                            |
|------------|-------------------------------------------------|
| Complexity | JavaBeans can be complex to develop and use     |
| Overhead   | JavaBeans can add some overhead to applications |
| Dependency | JavaBeans are dependent on the Java platform    |

# 14 Reflection

Reflection is commonly used by programs which require the ability to examine or modify the runtime behavior of applications running in the **Java virtual machine**.

# 15 Generic

## 15.1 Type Parameter and Type Argument Terminology

one provides type arguments in order to create a parameterized type.

Therefore, the T in Foo\<T> is a type **parameter** and the String in Foo\<String> f is a type **argument**.

## 15.2 Parameterized Types

You can also substitute a type parameter (that is, K or V) with a parameterized type (that is, List\<String>). For example, using the OrderedPair<K, V> example:

```java
OrderedPair<String, Box<Integer>> p = new OrderedPair<>("primes", new Box<Integer>(...));
```

## 15.3 Raw Types

A raw type is the name of a generic class or interface without any type arguments.

```java
public class Box<T> {
    public void set(T t) { /* ... */ }
    // ...
}
Box rawBox = new Box(); // If the actual type argument is omitted, you create a raw type of Box<T>:
```

> Box is the raw type of the generic type Box\<T>. However, a non-generic class or interface type is not a raw type.

## 15.4 Bounded Type Parameters

Why? to Restrict the types that can be used as type arguments in a parameterized type.

## 15.5 Generics, Inheritance, and Subtypes

- Box\<Integer> is not a subtype of Box\<Number> even though Integer is a subtype of Number.
  
  ![image 12](./pic/generics-subtypeRelationship.gif)

- A sample Collections hierarchy
  
  ![image 13](./pic/generics-sampleHierarchy.gif)

## 15.6 Wildcards

In generic code, the question mark (?), called the wildcard, represents an unknown type.

### 15.6.1 Unbounded Wildcards

The unbounded wildcard type is specified using the wildcard character (?)

### 15.6.2 Wildcards and Subtyping

![image 1](./pic/generics-listParent.gif)

![image 2](./pic/generics-wildcardSubtyping.gif)

### 15.6.3 Wildcard Capture and Helper Methods

```java
import java.util.List;

public class WildcardError {

    void foo(List<?> i) {
        i.set(0, i.get(0)); // Wildcard Error
    }
}
```

Fix with helper methods

```java
public class WildcardFixed {

    void foo(List<?> i) {
        fooHelper(i);
    }


    // Helper method created so that the wildcard can be captured
    // through type inference.
    private <T> void fooHelper(List<T> l) {
        l.set(0, l.get(0));
    }

}
```

## 15.7 Wildcard Guidelines:

- An "**in**" variable is defined with an **upper** bounded wildcard, using the extends keyword.
- An "**out**" variable is defined with a **lower** bounded wildcard, using the super keyword.
- In the case where the "**in**" variable can be accessed using methods defined in the **Object** class, use an **unbounded** wildcard.
- In the case where the code needs to access the variable as both an "**in**" and an "**out**" variable, **do not use a wildcard**.

> Note: These guidelines do not apply to a **method's return type**. Using a wildcard as a return type should be avoided because it forces programmers using the code to deal with wildcards.

## 15.8 Type Erasure

- Why need generics?
  - Generics were introduced to the Java language to provide tighter type checks at compile time and to support generic programming.
- How to implement generics?
  
  the Java compiler applies type erasure to:
  - **Replace all type parameters in generic types with their bounds or Object if the type parameters are unbounded**. The produced bytecode, therefore, contains only ordinary classes, interfaces, and methods.
  - **Insert type casts** if necessary to preserve type safety.
  - Generate **bridge methods** to preserve **polymorphism** in extended generic types.

- Generics incur no runtime overhead
  
  Type erasure ensures that no new classes are created for parameterized types;

- How to keep polymorphism?
  
  origin

  ```java
  public class Node<T> {

      public T data;

      public Node(T data) { this.data = data; }

      public void setData(T data) {
          System.out.println("Node.setData");
          this.data = data;
      }
  }

  public class MyNode extends Node<Integer> {
      public MyNode(Integer data) { super(data); }

      public void setData(Integer data) {
          System.out.println("MyNode.setData");
          super.setData(data);
      }
  }
  ```

  After type erasure
  
  ```java
  public class Node {

    public Object data;

    public Node(Object data) { this.data = data; }

    public void setData(Object data) {
        System.out.println("Node.setData");
        this.data = data;
    }
  }
  public class MyNode extends Node {

    public MyNode(Integer data) { super(data); }

    public void setData(Integer data) {
        System.out.println("MyNode.setData");
        super.setData(data);
    }
  }
  ```

  Add bridge method

  ```java
  class MyNode extends Node {

      // Bridge method generated by the compiler
      //
      public void setData(Object data) {
          setData((Integer) data);
      }

      public void setData(Integer data) {
          System.out.println("MyNode.setData");
          super.setData(data);
      }

      // ...
    }
  ```
  
  Consider the following code:
  
  ```java
  MyNode mn = new MyNode(5);
  Node n = mn;            // A raw type - compiler throws an unchecked warning
  n.setData("Hello");     // Causes a ClassCastException to be thrown.
  Integer x = mn.data;
  ```

  After type erasure, this code becomes:

  ```java
  MyNode mn = new MyNode(5);
  Node n = mn;            // A raw type - compiler throws an unchecked warning
                          // Note: This statement could instead be the following:
                          //     Node n = (Node)mn;
                          // However, the compiler doesn't generate a cast because
                          // it isn't required.
  n.setData("Hello");     // Causes a ClassCastException to be thrown.
  Integer x = (Integer)mn.data; // preserve type safety
  ```

## 15.9 Non-Reifiable Types

- A reifiable type is a type whose type information is fully available at **runtime**. This includes primitives, non-generic types, **raw types**, and invocations of **unbound wildcards**.

- Non-reifiable types are types where information has been **removed at compile-time** by **type erasure** — **invocations of generic types that are not defined as unbounded wildcards**. 

### Examples

List\<String> and List\<Number> are non-reifiable types

The JVM cannot tell the difference between thest types at runtime.

## 15.10 Heap Pollution

Heap pollution occurs when a variable of a **parameterized type** refers to an object that is **not** of that parameterized type.

For example, heap pollution occurs when **mixing raw types and parameterized types**, or when performing **unchecked casts**.

## 15.11 Restrictions on Generics

- Cannot Instantiate Generic Types with **Primitive Types**
- Cannot Create Instances of **Type Parameters**
- Cannot Declare Static Fields Whose Types are **Type Parameters**
- Cannot Use Casts or instanceof With **Parameterized Types**
- Cannot Create Arrays of **Parameterized Types**
- Cannot **Create**, **Catch**, or **Throw** Objects of **Parameterized Types**
- Cannot Overload a Method Where the Formal Parameter Types of Each Overload **Erase** to the **Same Raw Type**

# 16 Collection

![image The core collection interfaces.](./pic/colls-coreInterfaces.gif)

The core collection interface trees.

- Collection interface
- Map interface

## Collection interface

| Type | Desc |
| -- | -- |
| Set | does not allow duplicate elements <br> SortedSet:  provides for ordering of elements in the set. |
| List | provides for an ordered collection <br> allow duplicate elements |
| Queue | enables additional insertion, extraction, and inspection operations. <br> Queues typically, but **not necessarily**, order elements in a FIFO (first-in-first-out) manner. |
| Deque |  enables insertion, deletion, and inspection operations at both the ends. Elements in a Deque can be used in both LIFO and FIFO |

## Map interface

| Type | Desc |
| -- | -- |
| Map | maps keys and values similar to a Hashtable |
| SortedMap | maintains its key-value pairs in ascending order or in an order specified by a Comparator |

## Traversing Collections

- using aggregate operations
- with the for-each construct
- by using Iterators.

### Iterator

- hasNext method: return true if the iteration has more elements.
- next method: return next element in the iteration.
- remove method: removes the last element that was returned by next from the underlying Collection.
- The remove method may be called **only once per call** to next and throws an exception if this rule is violated.
- **Note that Iterator.remove is the only safe way to modify a collection during iteration**; the behavior is unspecified if the underlying collection is modified in any other way while the iteration is in progress.

### Use Iterator instead of the for-each construct when you need to

- Remove the **current** element.
- Iterate over **multiple collections** in parallel. ???

## Collection Interface Bulk Operations

- containsAll
- addAll
- removeAll
- retainAll
- clear

## Collection Interface Array Operations

The toArray methods are provided as a bridge between collections and older APIs that expect arrays on input.

```java
Object[] a = c.toArray(); // suppose that c is a Collection.
```

## Aggregate operation

the new aggregate operations do not modify the underlying collection. When using the new aggregate operations and lambda expressions, you must take care to **avoid mutation** so as not to introduce problems in the future, should your code be run later from a **parallel stream**.

## The Set interface and implementations

### Set implementations

- HashSet
- TreeSet
- LinkedHashSet

| Implementation | Desc |
| -- | -- |
| HashSet | Stores its elements in a hash table, is the **best-performing** implementation <br> Makes no guarantees concerning the order of iteration |
| TreeSet | Stores its elements in a **red-black** tree, **orders** its elements based on their values <br> It is substantially slower than HashSet
| LinkedHashSet | It is implemented as a **hash table** with a **linked list** running through it <br> Orders its elements based on the order in which they were inserted into the set (**insertion-order**). |

### Equals and hashCode operations

Two Set instances are equal if they contain the **same elements**, even if their **implementation** types differ

## The List interface and implementations

### Support operations

| Operation | Methods |
| -- | --- |
| Positional access | get, set, add, addAll, and remove |
| Search | indexOf and lastIndexOf |
| Iteration | listIterator |
| Range-view | sublist |

### Implementations

- ArrayList
- LinkedList

### Equals and hashCode method

Two List objects can be compared for logical equality without regard to their implementation classes.<br>
Two List objects are equal if they contain the same elements in the same order.

## The Queue Interface and implementations

A Queue is a collection for holding elements prior to processing.
| Type of Operation | Throws exception | Returns special value |
| -- | -- | -- |
| Insert | add(e) | offer(e) |
| Remove | remove() | poll() |
| Examine | element() | peek() |

### Queue implementations generally do not allow insertion of null elements

The LinkedList implementation, which was retrofitted to implement Queue, is an exception.

```java
Queue<Integer> queue = new LinkedList<>();
queue.add(null); // not recommend
```

For historical reasons, it permits null elements, but you should refrain from taking advantage of this, because null is used as a special return value by the poll and peek methods.

# 17. Module

# 18. IO

## 18.1 IO Stream

- Byte Stream vs Character Stream
  - Byte Stream operate 8 bits data each time.
  - Character Stream operate 16bit data echo time.

- Buffered Streams
  - Buffered input streams read data from a memory area known as a buffer; the native input API is called only when the buffer is empty.
  - Buffered output streams write data to a buffer, and the native output API is called only when the buffer is full.

# 19. POJO

A Plain Old Java Object (POJO) is a simple Java class that:

- Does not **extend** any other class (except java.lang.Object)
- Does not **implement** any interfaces (except java.io.Serializable)
- Has no **special** methods (such as methods with two underscores)
- Has fields that are **public**, **private**, or **protected**

# 20. Service Provider Interface (SPI)

Service Provider Interface (SPI) is a **mechanism** in Java that allows for the **dynamic loading of implementation classes for a given interface**. This is useful for frameworks that need to be **extensible**, as it allows different vendors to provide their own implementations of the framework's interfaces.

SPI works by having the framework define an interface that all implementations must implement. The framework then looks for implementation classes for this interface in a specific location, such as the **META-INF/services** directory. When the framework finds an implementation class, it loads it and creates an instance of it.

## 20.1 Examples

- Java Servlet API
- Java JDBC API
- Java Imaging API

## 20.2 More detailed example

```java
// The interface that all implementations must implement.
public interface MySPI {

    String getName();
}

// An implementation of MySPI.
public class MySPIImpl implements MySPI {

    @Override
    public String getName() {
        return "MySPIImpl";
    }
}

// A file that lists the implementation classes for MySPI.
META-INF/services/MySPI
MySPIImpl
```

- The **META-INF/services/MySPI** file lists the implementation classes for the MySPI interface.
- When the framework loads the MySPI interface, it will **look for implementation classes** in the **META-INF/services/MySPIfile**. If it finds theMySPIImpl` class, it will load it and create an instance of it.

<https://www.freecodecamp.org/chinese/news/a-quick-intro-to-dependency-injection-what-it-is-and-when-to-use-it/>
<https://www.freecodecamp.org/chinese/news/solid-principles/>
<https://docs.oracle.com/javase/tutorial/java/IandI/defaultmethods.html>
