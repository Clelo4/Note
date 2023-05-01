# Java
## Java SE Specifications
* [The Java Tutorials](https://docs.oracle.com/javase/tutorial/tutorialLearningPaths.html)
* [The Java Languaage Specification, Java SE 20 Edition](https://docs.oracle.com/javase/specs/jls/se7/html/index.html)
* [The Java Virtual Machine Specification, Java SE 20 Edition](https://docs.oracle.com/javase/specs/jvms/se20/html/index.html)
* [Java® Platform, Standard Edition & Java Development Kit
Version 20 API Specification](https://docs.oracle.com/en/java/javase/20/docs/api/index.html)
* [JAR File Specification](https://docs.oracle.com/en/java/javase/20/docs/specs/jar/jar.html)
* [Core Libraries](https://docs.oracle.com/en/java/javase/20/core/java-core-libraries1.html)


## Essential
* ***The main Method***: In the Java programming language, every application must contain a main method whose signature is:
``` Java
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
| Date Type | Default Value | type | Value range |
| --- | --- | --- | --- |
| byte | 0 | 8-bit signed | -128 ~ 127 |
| short	| 0 | 16-bit signed | -32768 ~ 32767 |
| int	| 0 | 32-bit signed  | -2^31 ~ 2^31-1 |
| long | 0L | 64-bit | signed long: -2^63 ~ 2^63-1 <br /> In Java SE 8 and late, unsigned long 0 ~ 2^64-1 |
| float	| 0.0f | single-precision 32-bit IEEE 754 floating point | ｜
| double | 0.0d | double-precision 64-bit IEEE 754 floating point ｜ |
| char| '\u0000' | signle 16-bit Unicode character | '\u0000' (or 0) ~ '\uffff' (or 65,535 inclusive) |
| boolean| false | This data type represents one bit of information, but its "size" isn't something that's precisely defined. | true and false |

> The String class is not technically a primitive data type, but considering the special support given to it by the language, you'll probably tend to think of it as such.

* ***The compiler will assign a reasonable default value for fields of the above types(Primitive data types and String); for local variables, a default value is never assigned.***
* Primitive types are special data types built into the language; they are not objects created from a class.

#### Literals
A literal is the source code representation of a fixed value; literals are represented directly in your code without requiring computation.
##### Integer Literals
An integer literal is of type long if it ends with the letter L or l; otherwise it is of type int.
``` Java
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
* null may be assigned to any variable, except variables of primitive types. 

#### class literal

### Using Underscore Characters in Numeric Literals
In Java SE 7 and later, any number of underscore characters (_) can appear anywhere between digits in a numerical literal. This feature enables you, for example. to separate groups of digits in numeric literals, which can improve the readability of your code.
``` Java
long creditCardNumber = 1234_5678_9012_3456L;
long socialSecurityNumber = 999_99_9999L;
float pi =  3.14_15F;
long hexBytes = 0xFF_EC_DE_5E;
long hexWords = 0xCAFE_BABE;
long maxLong = 0x7fff_ffff_ffff_ffffL;
byte nybbles = 0b0010_0101;
long bytes = 0b11010010_01101001_10010100_10010010;
```

### Arrays
* An array is a container object that holds a fixed number of values of a single type. 
* The length of an array is established when the array is created.
* After creation, its length is fixed.

#### Array Declaration
An array declaration has two components: the array's ***type*** and the array's ***name***.
``` Java
// declares an array of integers
int[] anArray;
```
***The size of the array is not part of its type (which is why the brackets are empty).***

As with variables of other types, the declaration does not actually create an array; it simply tells the compiler that this variable will hold an array of the specified type.

``` Java
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
``` Java
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

### Objects
### Nested Classes
* Static nested classes
* inner classes
* anonymous inner classes
* local classes
* lambda expressions

## Enum Types
