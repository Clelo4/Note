- [IoC Container](#ioc-container)
- [ApplicationContext](#applicationcontext)
- [Why Spring IoC container need configuration metadata?](#why-spring-ioc-container-need-configuration-metadata)
- [How to represente configuration metadata](#how-to-represente-configuration-metadata)
- [Beans](#beans)
- [The bean definition](#the-bean-definition)
- [How Instantiate a bean?](#how-instantiate-a-bean)
- ["factory bean" VS "FactoryBean"](#factory-bean-vs-factorybean)
- [Dependency Injection](#dependency-injection)
- [Dependency Injection Variants](#dependency-injection-variants)
- [Use Constructor-based or setter-based DI?](#use-constructor-based-or-setter-based-di)
- [When to create bean?](#when-to-create-bean)
- [How to deal with Circular dependencies](#how-to-deal-with-circular-dependencies)
- [collaborating bean](#collaborating-bean)
- [Inner Beans](#inner-beans)
- [Why need depends-on attribute?](#why-need-depends-on-attribute)
- [What'is Lazy-initialized Bean?](#whatis-lazy-initialized-bean)
- [Autowiring Collaborators](#autowiring-collaborators)
- [Limitations and Disadvantages of Autowiring](#limitations-and-disadvantages-of-autowiring)
- [Why need Method Injection?](#why-need-method-injection)
- [Solution One - forego some inversion of control](#solution-one---forego-some-inversion-of-control)
- [Lookup Method Injection](#lookup-method-injection)
- [Arbitrary Method Replacement](#arbitrary-method-replacement)
- [Bean Scopes](#bean-scopes)
- [The Prototype Scope](#the-prototype-scope)
- [Spring doesn't manage the complete lifecycle of a prototype bean](#spring-doesnt-manage-the-complete-lifecycle-of-a-prototype-bean)
    - [Why?](#why)
- [Singleton Beans with Prototype-bean Dependencies](#singleton-beans-with-prototype-bean-dependencies)
- [The Lifecycle Callbacks of Bean](#the-lifecycle-callbacks-of-bean)
- [The three options for controlling bean lifecycle behavior](#the-three-options-for-controlling-bean-lifecycle-behavior)
- [Initialization Callbacks of Bean](#initialization-callbacks-of-bean)
  - [Way One: implements InitializingBean](#way-one-implements-initializingbean)
  - [Way Two: configurate metadata](#way-two-configurate-metadata)
- [Destruction Callbacks](#destruction-callbacks)
  - [Way one: implements DisposableBean](#way-one-implements-disposablebean)
  - [Way two: configurate metadata](#way-two-configurate-metadata-1)
- [Multiple lifecycle mechanisms](#multiple-lifecycle-mechanisms)
- [BeanPostProcessor](#beanpostprocessor)


# IoC Container

- [IoC is also known as dependency injection (DI)](https://docs.spring.io/spring-framework/reference/core/beans/introduction.html)
- The [BeanFactory](https://docs.spring.io/spring-framework/docs/6.0.9/javadoc-api/org/springframework/beans/factory/BeanFactory.html) interface provides an advanced configuration mechanism capable of managing any type of object.
- [ApplicationContext](https://docs.spring.io/spring-framework/docs/6.0.9/javadoc-api/org/springframework/context/ApplicationContext.html) is a sub-interface of **BeanFactory**.

| Interface | Diff |
| -- | -- |
| BeanFactory |  provides the configuration framework and basic functionality |
| ApplicationContext | adds more enterprise-specific functionality. |

# ApplicationContext

- ApplicationContext interface represents the Spring IoC container
- Is responsible for instantiating, configuring, and assembling the beans.
![image The Spring IoC container](./pic/container-magic.png)

# Why Spring IoC container need configuration metadata?

The configuration metadata tell the Spring IoC container to **instantiate**, **configure**, and **assemble** the objects in your application.

# How to represente configuration metadata

- XML-based
- Annotation-based
- Java-based configuration

# Beans

- A **bean** is an object that is instantiated, assembled, and managed by a Spring IoC container.
- Beans are created with the configuration metadata.

# The bean definition

| Property | Explained in…​ |
| -- | -- |
| Class | [Instantiating Beans](https://docs.spring.io/spring-framework/reference/core/beans/definition.html#beans-factory-class) |
| Name | [Naming Beans](https://docs.spring.io/spring-framework/reference/core/beans/definition.html#beans-beanname) |
| Scope | [Bean Scopes](https://docs.spring.io/spring-framework/reference/core/beans/factory-scopes.html) |
| Constructor arguments | [Dependency Injection](https://docs.spring.io/spring-framework/reference/core/beans/dependencies/factory-collaborators.html) |
| Properties | [Dependency Injection](https://docs.spring.io/spring-framework/reference/core/beans/dependencies/factory-collaborators.html) |
| Autowiring mode| [Autowiring Collaborators](https://docs.spring.io/spring-framework/reference/core/beans/dependencies/factory-autowire.html) |
| Lazy initialization mode | [Lazy-initialized Beans](https://docs.spring.io/spring-framework/reference/core/beans/dependencies/factory-lazy-init.html) |
| Initialization method | [Initialization Callbacks](https://docs.spring.io/spring-framework/reference/core/beans/factory-nature.html#beans-factory-lifecycle-initializingbean) |
| Destruction method | [Destruction Callbacks](https://docs.spring.io/spring-framework/reference/core/beans/factory-nature.html#beans-factory-lifecycle-disposablebean) |

# How Instantiate a bean?

- Instantiation with a Constructor
- Instantiation with a **Static** Factory Method

  ```XML
  <bean id="clientService"
    class="examples.ClientService"
    factory-method="createInstance"/>
  ```

- Instantiation by Using an **Instance** Factory Method
  - In the **factory-bean** attribute, specify the name of a bean in the current (or parent or ancestor) container

  ```XML
  <!-- the factory bean, which contains a method called createInstance() -->
  <bean id="serviceLocator" class="examples.DefaultServiceLocator">
  <!-- inject any dependencies required by this locator bean -->
  </bean>

  <!-- the bean to be created via the factory bean -->
  <bean id="clientService"
  factory-bean="serviceLocator"
  factory-method="createClientServiceInstance"/>
  ```

# "factory bean" VS "FactoryBean"

- "**factory bean**" refers to a bean that is configured in the Spring container and that creates objects through an instance or static factory method.
- **FactoryBean** refers to a Spring-specific FactoryBean implementation class.

# Dependency Injection

- Dependency injection (DI) is a process whereby objects define their dependencies
- The IoC container then injects their dependencies when it creates the bean.

# Dependency Injection Variants

- Constructor-based Dependency Injection
- Setter-based Dependency Injection

# Use Constructor-based or setter-based DI?

- Use constructors for **mandatory(required)** dependencies
- Use setter methods or configuration methods for **optional** dependencies.

# When to create bean?

- Beans that are **singleton-scoped** and set to be **pre-instantiated (the default)** are created when the container is created.
- Otherwise, the bean is created only when it is requested.

# How to deal with Circular dependencies

- Inject dependencies by setters rather than constructors.

# collaborating bean

If no circular dependencies exist, when one or more collaborating beans are being injected into a dependent bean, each collaborating bean is totally configured prior to being injected into the dependent bean.

# Inner Beans

The container also ignores the scope flag of inner beans on creation, because inner beans are always anonymous and are always created with the outer bean.

# Why need depends-on attribute?

- Control initialization order
  
  The **depends-on** attribute can explicitly force one or more beans to be initialized before the bean using this element is initialized.
  - for example, a static initializer in a class needs to be triggered, such as for database driver registration.
- In the case of singleton beans only, depends-on can also control shutdown order.
  
   Dependent beans that define a depends-on relationship with a given bean are destroyed first, prior to the given bean itself being destroyed.

# What'is Lazy-initialized Bean?

- By default, **ApplicationContext** implementations eagerly create and configure all **singleton** beans as part of the initialization process.
- A lazy-initialized bean tells the IoC container to create a bean instance when it is **first requested**, rather than at **startup**.
- When a lazy-initialized bean is a dependency of a singleton bean that is not lazy-initialized, the ApplicationContext creates the lazy-initialized bean at startup, because it must satisfy the singleton’s dependencies.

# Autowiring Collaborators

The Spring container can autowire relationships between collaborating beans.

| Mode | Explanation |
| -- | -- |
| no | (Default) No autowiring. Bean references must be defined by ref elements. Changing the default setting is not recommended for larger deployments, because specifying collaborators explicitly gives greater control and clarity. To some extent, it documents the structure of a system. |
| byName | Autowiring by property name. Spring looks for a bean with the same name as the property that needs to be autowired. For example, if a bean definition is set to autowire by name and it contains a master property (that is, it has a setMaster(..) method), Spring looks for a bean definition named master and uses it to set the property. |
| byType | Lets a property be autowired if exactly one bean of the property type exists in the container. If more than one exists, a fatal exception is thrown, which indicates that you may not use byType autowiring for that bean. If there are no matching beans, nothing happens (the property is not set). |
| constructor | Analogous to byType but applies to constructor arguments. If there is not exactly one bean of the constructor argument type in the container, a fatal error is raised. |

# Limitations and Disadvantages of Autowiring

- Cannot autowire simple properties such as primitives, Strings, and Classes (and arrays of such simple properties). This limitation is by-design.
- Autowiring is less exact than explicit wiring
- Wiring information may not be available to tools that may generate documentation from a Spring container.
- Multiple bean definitions within the container may match the type specified by the setter method or constructor argument to be autowired. If no unique bean definition is available, an exception is thrown.

# Why need Method Injection?

Suppose **singleton** bean A needs to use **non-singleton** (prototype) bean B, perhaps on each method invocation on A. The container creates the singleton bean A only **once**, and thus only gets **one opportunity** to set the properties. The container cannot provide bean A with a new instance of bean B every time one is needed.

# Solution One - forego some inversion of control

Make bean A aware of the container by implementing the **ApplicationContextAware** interface

```java
package com.chengjunjie.app.service;

import org.springframework.beans.BeansException;
import org.springframework.context.ApplicationContext;
import org.springframework.context.ApplicationContextAware;

public class MethodInjectionWithForegoIoC implements ApplicationContextAware {
    private ApplicationContext applicationContext;
    public void process() {
        EmployeeService employeeService = this.applicationContext.getBean("employeeService", EmployeeService.class);
        employeeService.checkDepartment();
    }
    @Override
    public void setApplicationContext(ApplicationContext context) throws BeansException {
        this.applicationContext = context;
    }
}
```

> Note: The above solution is not desirable, because the business code is aware of and coupled to the Spring Framework.

# Lookup Method Injection

- Lookup method injection is the ability of the container to **override** methods on container-managed beans and return the lookup result for **another named bean** in the container.
- The Spring Framework implements this method injection by using **bytecode** generation from the CGLIB library to **dynamically generate a subclass that overrides the method**.

```java
package com.chengjunjie.app.service;

public abstract class MethodInjectionExample {

    protected abstract EmployeeService getEmployeeService();

    public void process() {
        EmployeeService employeeService = this.getEmployeeService();
        employeeService.checkDepartment();
    }
}
```

```XML
<bean id="employeeService"
      class="com.chengjunjie.app.service.EmployeeService"
      scope="prototype"
>
</bean>

<bean id="methodInjectionExample" class="com.chengjunjie.app.service.MethodInjectionExample">
    <lookup-method name="getEmployeeService" bean="employeeService"/>
</bean>
```

> Note: For this **dynamic subclassing** to work, the class that the Spring bean container **subclasses** cannot be **final**, and the **method** to be **overridden** cannot be **final**, either.

# Arbitrary Method Replacement

A less useful form of method injection than lookup method injection is the ability to replace arbitrary methods in a managed bean with another method implementation.

```java
public class MyValueCalculator {

 public String computeValue(String input) {
  // some real code...
 }

 // some other methods...
}

/**
 * meant to be used to override the existing computeValue(String)
 * implementation in MyValueCalculator
 */
public class ReplacementComputeValue implements MethodReplacer {

 public Object reimplement(Object o, Method m, Object[] args) throws Throwable {
  // get the input value, work with it, and return a computed result
  String input = (String) args[0];
  ...
  return ...;
 }
}
```

```XML
<bean id="myValueCalculator" class="x.y.z.MyValueCalculator">
 <!-- arbitrary method replacement -->
 <replaced-method name="computeValue" replacer="replacementComputeValue">
  <arg-type>String</arg-type>
 </replaced-method>
</bean>

<bean id="replacementComputeValue" class="a.b.c.ReplacementComputeValue"/>
```

# Bean Scopes

| Scope | Description |
| -- | -- |
| singleton | (Default) Scopes a single bean definition to a single object instance for each Spring IoC container. |
| prototype | Scopes a single bean definition to any number of object instances. |

# The Prototype Scope

The non-singleton prototype scope of bean deployment results in the creation of a new bean instance every time a request for that specific bean is made.

# Spring doesn't manage the complete lifecycle of a prototype bean

### Why?

The IoC container instantiates, configures, and otherwise assembles a prototype object and **hands it to the client**, with no further record of that prototype instance.

In the case of prototypes, configured destruction lifecycle callbacks are not called.

# Singleton Beans with Prototype-bean Dependencies

If you need a new instance of a prototype bean at runtime more than once, see Method Injection.

# The Lifecycle Callbacks of Bean

- Initialization Callbacks
- Destruction Callbacks
- Startup and Shutdown Callbacks

# The three options for controlling bean lifecycle behavior

- The **InitializingBean** and **DisposableBean** callback interfaces
- Custom init() and destroy() methods
- The **@PostConstruct** and **@PreDestroy** annotations

# Initialization Callbacks of Bean

## Way One: implements InitializingBean

The **org.springframework.beans.factory.InitializingBean** interface lets a bean perform **initialization** work **after** the container **has set all necessary properties** on the bean.

```java
public class AnotherExampleBean implements InitializingBean {

 @Override
 public void afterPropertiesSet() {
  // do some initialization work
 }
}
```

## Way Two: configurate metadata

```XML
<bean id="exampleInitBean" class="examples.ExampleBean" init-method="init"/>
```

```java
public class ExampleBean {

 public void init() {
  // do some initialization work
 }
}
```

# Destruction Callbacks

## Way one: implements DisposableBean

Implementing **the org.springframework.beans.factory.DisposableBean** interface lets a bean get a callback when the container that contains it is **destroyed**.

```java
public class AnotherExampleBean implements DisposableBean {

 @Override
 public void destroy() {
  // do some destruction work (like releasing pooled connections)
 }
}
```

## Way two: configurate metadata

```XML
<bean id="exampleInitBean" class="examples.ExampleBean" destroy-method="cleanup"/>
```

```java
public class ExampleBean {

 public void cleanup() {
  // do some destruction work (like releasing pooled connections)
 }
}
```

# Multiple lifecycle mechanisms

Multiple lifecycle mechanisms configured for the same bean, with different initialization methods, are called as follows:

- 1. Methods annotated with **@PostConstruct**
- 2. **afterPropertiesSet()** as defined by the InitializingBean callback interface
- 3. A custom configured **init()** method

Destroy methods are called in the same order:

- 1. Methods annotated with **@PreDestroy**
- 2. **destroy()** as defined by the DisposableBean callback interface
- 3. A custom configured **destroy()** method

# BeanPostProcessor
