# Java

## Java Concept
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

## Documents And Specifications
* [Java SE(Java Platform, Standard Edition) Documentation](https://docs.oracle.com/en/java/javase/20/)
* [The Java Tutorials](https://docs.oracle.com/javase/tutorial/tutorialLearningPaths.html)
* [The Java Language Specification, Java SE 20 Edition](https://docs.oracle.com/javase/specs/jls/se20/html/index.html)
* [The Java Virtual Machine Specification, Java SE 20 Edition](https://docs.oracle.com/javase/specs/jvms/se20/html/index.html)
* [Java® Platform, Standard Edition & Java Development Kit
  Version 20 API Specification](https://docs.oracle.com/en/java/javase/20/docs/api/index.html)
* [JAR File Specification](https://docs.oracle.com/en/java/javase/20/docs/specs/jar/jar.html)
* [Core Libraries](https://docs.oracle.com/en/java/javase/20/core/java-core-libraries1.html)

## Essential
* ***The main Method***: In the Java programming language, every application must contain a main method whose signature is:
```java
public static void main(String[] args)
```

## Learning the Java Language
### What is an Object?
An Object is a software bundle of related state and behavior. Software objects are often used to model the real-world objects that you find in everyday life.
### What is a Class?
A class is a blueprint or prototype from which objects are created. This section defines a class that models the state and behavior of a real-world object.
### What is Inheritance?
Inheritance provides a powerful and natural mechanism for organizing and structuring your software.
### What is an Interface?
An interface is a contract between a class and the outside world. When a class implements an interface, it promises to provide the behavior published by that interface.
### What is a Package?
A package is a namespace for organizing classes and interfaces in a logical manner. Placing your code into packages makes large software projects easier to manage.

## Language Basics

### Variables
* Instance Variables (Non-Static Fields)
* Class Variables (Static Fields)
* Local Variables
* Parameters

### Naming
* Variable names are case-sensitive.
* Subsequent characters may be letters, digits, dollar signs, or underscore characters.
* If the name you choose consists of only one word, spell that word in all lowercase letters.
* If it consists of more than one word, capitalize the first letter of each subsequent word. The names gearRatio and currentGear are prime examples of this convention.
* If your variable stores a constant value, such as static final int NUM_GEARS = 6, the convention changes slightly, capitalizing every letter and separating subsequent words with the underscore character.

### Primitive Data Types
| Date Type | Default Value | type                                                                                                   | Value range                                                                |
|-----------|---------------|--------------------------------------------------------------------------------------------------------|----------------------------------------------------------------------------|
| byte      | 0             | 8-bit signed                                                                                           | -128 ~ 127                                                                 |
| short	    | 0             | 16-bit signed                                                                                          | -32768 ~ 32767                                                             |
| int	      | 0             | 32-bit signed                                                                                          | -2^31 ~ 2^31-1                                                             |
| long      | 0L            | 64-bit                                                                                                 | signed long: -2^63 ~ 2^63-1 <br /> In Java SE 8 and late, unsigned long 0 ~ 2^64-1 |
| float	    | 0.0f          | single-precision 32-bit IEEE 754 floating point                                                        |                                                                            |
| double    | 0.0d          | double-precision 64-bit IEEE 754 floating point                                                        |                                                                            |
| char      | '\u0000'      | signle 16-bit Unicode character                                                                        | '\u0000' (or 0) ~ '\uffff' (or 65,535 inclusive)                           |
| boolean   | false         | This data type represents one bit of information, but its "size" isn't something that's precisely defined. | true and false                                                             |

> The String class is not technically a primitive data type, but considering the special support given to it by the language, you'll probably tend to think of it as such.

* ***The compiler will assign a reasonable default value for fields of the above types(Primitive data types and String); for local variables, a default value is never assigned.***
* Primitive types are special data types built into the language; they are not objects created from a class.

#### Literals
A literal is the source code representation of a fixed value; literals are represented directly in your code without requiring computation.
##### Integer Literals
An integer literal is of type long if it ends with the letter L or l; otherwise it is of type int.
```java
// The number 26, in decimal
int decVal = 26;
//  The number 26, in hexadecimal
int hexVal = 0x1a;
// The number 26, in binary
int binVal = 0b11010;
```
##### Floating-Point Literals
A floating-point literal is of type float if it ends with the letter F or f; otherwise its type is double and it can optionally end with the letter D or d.

#### Character and String Literals
Literals of types char and String may contain any Unicode (UTF-16) characters.

#### null literal
* null can be used as a value for any reference type
* null may be assigned to any variable, ***except variables of primitive types***.

#### class literal

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

### Reference Data Types:
* strings
* arrays
* objects

### Arrays
* An array is a container object that holds a fixed number of values of a single type.
* The length of an array is established when the array is created.
* After creation, its length is fixed.

#### Array Declaration
An array declaration has two components: the array's ***type*** and the array's ***name***.
```Java
// declares an array of integers
int[] anArray;
```
***The size of the array is not part of its type (which is why the brackets are empty).***

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

#### Creating, Initializing, and Accessing an Array
```Java
// create an array of integers
anArray = new int[10];
```

### The switch Statement
A switch works with the ***byte***, ***short***, ***char***, and ***int*** primitive data types. It also works with ***enumerated types*** (discussed in Enum Types), the ***String*** class, and a few special classes that wrap certain primitive types: ***Character***, ***Byte***, ***Short***, and ***Integer***

## Classes and Objects
### Classes
* ***Modifiers***: public, private(The private modifier can only be applied to Nested Classes)
* ***interfaces***: A class can implement more than one interface.
* ***Inherience***: A class can only extend (subclass) one parent.
#### Class Overloading Methods
* Method signatures: Method Name + parameter lists
* Class Overloading Methods means that methods within a class can have the same name if they have different parameter lists.
* The compiler does not consider return type when differentiating methods, so you cannot declare two methods with the same signature even if they have a different return type.
#### Class Default Constructor
If you don't have to provide any constructors for your class, the compiler automatically provides a no-argument, default constructor for any class without constructors. ***It means all classes have a least one constructor***.
* ***No-argument constructor*** is not always a Default Constructor, but a Default Constructor is must be a No-argument constructor.
* Default constructor will call the no-argument constructor of the superclass.
    * In default constructor, the compiler will complain if the superclass doesn't have a no-argument constructor so you must verify that it does
    * If your class has no explicit superclass, then it has an implicit superclass of Object, which does have a no-argument constructor.

#### Passing Primitive Data Type Arguments
Primitive arguments, such as an int or a double, are passed into methods by value.
#### Passing Reference Data Type Arguments
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

### Objects
#### Object Declaration
```java
type name;
```
This notifies the compiler that you will use name to refer to data whose type is type.
* With a ***primitive variable***, this declaration also reserves the proper amount of memory for the variable.
* With a ***reference variable***, this declaration does not create an object.
#### Creating an Object(Instantiating a Class)
* The new operator instantiates a class by allocating memory for a new object and returning a reference to that memory.
#### Initializing an Object
...

### Garbage Collection
The ***Java runtime environment*** deletes objects when it determines that they are no longer being used.
#### The ways of dropping object reference
* Automatically: References that are held in a variable are usually dropped when the variable goes out of scope.
* Manually: Explicitly drop an object reference by setting the variable to the special value ***null***.

***Note: [Garbage Collection is not part of the JVM specification](https://forums.oracle.com/ords/apexds/post/a-jvm-without-garbage-collection-is-it-possible-1309)***

### Returning a Class or Interface
* Class names as return types: the class of the type of the returned object must be either a subclass of, or the exact class of, the return type.
* Interface names as return types: the object returned must implement the specified interface.

### Using this with a Constructor
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
    ...
}
```

### Controlling Access to Members of a Class
| level               | items                                                                 |
|---------------------|-----------------------------------------------------------------------|
| Top Access level    | public, or package-private (no explicit modifier)                     |
| Member Access level | public, private, protected, or package-private (no explicit modifier) |

* Modifier public, in which case that class is visible to all classes everywhere.
* If a class has no modifier (the default, also known as package-private), it is visible only within its own package

#### Member Access Levels
| Modifier    | Class | Package | Subclass | World |
|-------------|-------|---------|----------|-------|
| public      | Y     | Y       | Y        | Y     |
| protected   | Y     | Y       | Y        | N     |
| no modifier | Y     | Y       | N        | N     |
| private     | Y     | N       | N        | N     |
* private: the private modifier specifies that the member can only be accessed in its own class.
* protected: the protected modifier specifies that the member can only be accessed within ***its own package (as with package-private)*** and, in addition, ***by a subclass of its class in another package***.

#### Tips on Choosing an Access Level
* Use the most restrictive access level that makes sense for a particular member. Use private unless you have a good reason not to.
* Avoid public fields except for constants. Public fields tend to link you to a particular implementation and limit your flexibility in changing your code.

### Class Variables
Fields that have the static modifier in their declaration are called static fields or class variables.
### static methods
Static methods, which have the static modifier in their declarations, should be invoked with the class name, without the need for creating an instance of the class, as in
```java
ClassName.methodName(args)
```
***Note: You can also refer to static methods with an object reference like***
```java
instanceName.methodName(args)
```
but this is discouraged because it does not make it clear that they are class methods.

### Constants
The static modifier, in combination with the final modifier, is also used to define constants.
> Note: If a primitive type or a string is defined as a constant and the value is known at compile time, the compiler replaces the constant name everywhere in the code with its value. This is called a compile-time constant. If the value of the constant in the outside world changes (for example, if it is legislated that pi actually should be 3.975), you will need to recompile any classes that use this constant to get the current value.

### Nested Classes
* Static nested classes
* inner classes
* anonymous inner classes
* local classes
* lambda expressions

## Enum Types

