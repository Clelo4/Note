[Top 30 Spring Core, Spring MVC and Spring Security Interview Questions Answers](https://www.java67.com/2012/08/spring-interview-questions-answers.html)

## 1. What difference between loadClass and Class.forName?

classloader?
https://stackoverflow.com/questions/11377018/tomcat-error-java-sql-sqlexception-no-suitable-driver-found-for-jdbcsqlserver

- loadClass() is a method in the **ClassLoader** class, while Class.**forName**() is a static method in the Class class. This means that loadClass() can only be called from **within a class loader**, while Class.forName() can be **called from anywhere**.
- loadClass() only loads the class, while Class.forName() loads the class and **initializes** it. This means that if you call loadClass() on a class that has **static initializers**, those **initializers will not be executed**. However, if you call Class.forName() on a class that has **static initializers**, those initializers will be executed.
- loadClass() does not throw any exceptions, while Class.forName() can throw a ClassNotFoundException if the class cannot be found.

| Feature |	loadClass() | Class.forName() |
| --- | --- | --- |
| Scope |	Only callable from within a class loader | Can be called from anywhere |
| Initialization | Does not initialize the class(static initializers) | Initializes the class(static initializers) |
| Exceptions | Does not throw any exceptions | Can throw a ClassNotFoundException |
