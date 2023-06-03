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
| Property |	Explained in…​ |
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
-  "**factory bean**" refers to a bean that is configured in the Spring container and that creates objects through an instance or static factory method.
-  **FactoryBean** refers to a Spring-specific FactoryBean implementation class.

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
