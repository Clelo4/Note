- [1. Root WebApplicationContext](#1-root-webapplicationcontext)
  - [1.1 configure the root WebApplicationContext](#11-configure-the-root-webapplicationcontext)
    - [1.1.1 Using XML-based approach](#111-using-xml-based-approach)
    - [1.1.2 Using code-based approach](#112-using-code-based-approach)
- [2. DispatcherServlet](#2-dispatcherservlet)
  - [2.1 DispatcherServlet WebApplicationContext](#21-dispatcherservlet-webapplicationcontext)
  - [2.2 configure the Servlet WebApplicationContext](#22-configure-the-servlet-webapplicationcontext)
    - [2.2.1 Using XML-based approach](#221-using-xml-based-approach)
    - [2.2.2 Using code-based approach](#222-using-code-based-approach)
  - [2.3 Context Hierarchy](#23-context-hierarchy)
  - [2.4 DispatcherServlet initialization parameters](#24-dispatcherservlet-initialization-parameters)
  - [2.5 @Controller](#25-controller)
- [3. ContextLoaderListener](#3-contextloaderlistener)
- [4. WebApplicationInitializer](#4-webapplicationinitializer)
- [5. SpringServletContainerInitializer](#5-springservletcontainerinitializer)

# 1. Root WebApplicationContext

The root WebApplicationContext is the **top-level application context** in a Spring web application. 

## 1.1 configure the root WebApplicationContext

### 1.1.1 Using XML-based approach

```xml
<web-app xmlns="http://java.sun.com/xml/ns/javaee"
xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
xsi:schemaLocation="http://java.sun.com/xml/ns/javaee http://java.sun.com/xml/ns/javaee/web-app_2_5.xsd"
version="2.5">
<context-param>
    <param-name>contextClass</param-name>
    <param-value>org.springframework.web.context.support.XmlWebApplicationContext</param-value>
</context-param>
<context-param>
  <param-name>contextConfigLocation</param-name>
  <param-value>/WEB-INF/applicationContext.xml</param-value>
</context-param>

<listener>
  <listener-class>org.springframework.web.context.ContextLoaderListener</listener-class>
</listener>

</web-app>
```

- The actual initialization work for the root application context is performed by ContextLoader class, which is called by **ContextLoaderListener**. This class looks for a "**contextClass**" parameter at the **web.xml context-param level** to find the type of the context class. If no contextClass is defined, then by default, it uses **XmlWebApplicationContext**.

- It also processes a "**contextConfigLocation**" context-param and passes its value to the context instance. This parameter specifies the path for the spring configuration file. It may contain **multiple file paths** that can be separated by any number of commas and spaces, like "WEB-INF/applicationContext1.xml, WEB-INF/applicationContext2.xml".

### 1.1.2 Using code-based approach

```java
public class MyWebAppInitializer implements WebApplicationInitializer {
  @Override
  public void onStartup(ServletContext container) throws ServletException {
    // Create the 'root' Spring application context
    XmlWebApplicationContext rootContext = new XmlWebApplicationContext();
    rootContext.setConfigLocation("/WEB-INF/app-context.xml");

    // Manage the lifecycle of the root application context
    container.addListener(new ContextLoaderListener(rootContext));

    // // Create the dispatcher servlet's Spring application context
    // XmlWebApplicationContext dispatcherContext = new XmlWebApplicationContext();
    // dispatcherContext.setConfigLocation("/WEB-INF/servletOne-context.xml");

    // // Register and map the dispatcher servlet
    // ServletRegistration.Dynamic dispatcher = container.addServlet("dispatcher", new DispatcherServlet(dispatcherContext));
    // dispatcher.setLoadOnStartup(1);
    // dispatcher.addMapping("/");
  }
}
```

[How WebApplicationInitializer is work?](#4-webapplicationinitializer)

# 2. DispatcherServlet

DispatcherServlet, provides a shared algorithm for request processing, while actual work is performed by configurable delegate components.

## 2.1 DispatcherServlet WebApplicationContext

- **DispatcherServlet** expects a WebApplicationContext for its own configuration.

- WebApplicationContext is an extension of a plain ApplicationContext

## 2.2 configure the Servlet WebApplicationContext

### 2.2.1 Using XML-based approach

```xml
<web-app xmlns="http://java.sun.com/xml/ns/javaee"
xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
xsi:schemaLocation="http://java.sun.com/xml/ns/javaee http://java.sun.com/xml/ns/javaee/web-app_2_5.xsd"
version="2.5">
    <servlet>
        <servlet-name>app</servlet-name>
        <servlet-class>org.springframework.web.servlet.DispatcherServlet</servlet-class>
        <init-param>
            <param-name>contextClass</param-name>
            <param-value>org.springframework.web.context.support.XmlWebApplicationContext</param-value>
        </init-param>
        <init-param>
            <param-name>contextConfigLocation</param-name>
            <param-value>
                /WEB-INF/servlet-context.xml
            </param-value>
        </init-param>
        <load-on-startup>1</load-on-startup>
    </servlet>

    <servlet-mapping>
        <servlet-name>app</servlet-name>
        <url-pattern>/</url-pattern>
    </servlet-mapping>
</web-app>
```

### 2.2.2 Using code-based approach

```java
public class MyWebAppInitializer implements WebApplicationInitializer {
  @Override
  public void onStartup(ServletContext container) throws ServletException {
    // // Create the 'root' Spring application context
    // XmlWebApplicationContext rootContext = new XmlWebApplicationContext();
    // rootContext.setConfigLocation("/WEB-INF/app-context.xml");

    // // Manage the lifecycle of the root application context
    // container.addListener(new ContextLoaderListener(rootContext));

    // Create the dispatcher servlet's Spring application context <= !!!
    XmlWebApplicationContext dispatcherContext = new XmlWebApplicationContext();
    dispatcherContext.setConfigLocation("/WEB-INF/servletOne-context.xml");
    // dispatcherContext.setConfigLocations("/WEB-INF/servletOne-context.xml", "/WEB-INF/servletTwo-context.xml");

    // Register and map the dispatcher servlet
    ServletRegistration.Dynamic dispatcher = container.addServlet("dispatcher", new DispatcherServlet(dispatcherContext));
    dispatcher.setLoadOnStartup(1);
    dispatcher.addMapping("/");
  }
}
```

## 2.3 Context Hierarchy

> It is also possible to have a context hierarchy where **one root WebApplicationContext** is **shared** across **multiple DispatcherServlet** (or **other Servlet**) instances, each with its own child **WebApplicationContext** configuration.

![image mvc-context-hierarchy ](./pic/mvc-context-hierarchy.png)

## 2.4 DispatcherServlet initialization parameters

| Parameter | Explanation |
| --- | --- |
| contextClass | **Class that implements WebApplicationContext**, which instantiates the context used by this servlet. By default, the **XmlWebApplicationContext** is used.
| contextConfigLocation | **String that is passed to the context instance (specified by contextClass)** to indicate where context(s) can be found. The string consists potentially of multiple strings (using a comma as a delimiter) to support **multiple contexts**. In case of multiple context locations with beans that are defined twice, the latest location takes precedence. |
| namespace | Namespace of the WebApplicationContext. Defaults to [servlet-name]-servlet. |

## 2.5 @Controller

```java
@Controller
@RequestMapping(value = ControllerConstant.user)
public class UserController {
}
```

Two Way to make Spring to find controllers annotated with @Controller:

- Bean XML
  
  You can define annotated controller beans explicitly, using a standard Spring bean definition in the dispatcher's context.

  ```xml
  <beans:bean id="userController" class="com.chengjunjie.web.presentation.controller.UserController"></beans:bean>
  ```

- enable autodetection
  
  ```xml
  <context:component-scan base-package="com.chengjunjie.web.presentation.controller"/>
  ```

Why <context:component-scan> can work?

```java
@Target(ElementType.TYPE)
@Retention(RetentionPolicy.RUNTIME)
@Documented
@Component  // <- This is reason
public @interface Controller {
}
```

# 3. ContextLoaderListener

It is one of the essential components of the Spring MVC framework and used to create **root context** in Spring web applications, which is **shared by different servlet contexts** loaded by each **DispatcherServlet**.

- It usually contains generic spring beans like which **are not web specifics** like beans from service classes and Data Access object.
- ContextLoaderListener is that it's **optional** in Spring MVC.

# 4. WebApplicationInitializer

- Implementations of this Class will be **detected automatically** by **SpringServletContainerInitializer**, which itself is **bootstrapped automatically** by any **Servlet container**.

- **WebApplicationInitializer** is an interface in the Spring Framework that provides a way to configure a **ServletContext** programmatically, instead of using the traditional web.xml file.

- WebApplicationInitializer, used to configure the servlet container, **not just** for configuring MVC.

- As an alternative to the above, you can also extend from **AbstractAnnotationConfigDispatcherServletInitializer**

# 5. SpringServletContainerInitializer

- SpringServletContainerInitializer is a **ServletContainerInitializer** implementation that is provided by Spring.
- SpringServletContainerInitializer is responsible for loading and delegating to any user-defined **WebApplicationInitializer** implementations.

This class will be loaded and instantiated and have its **onStartup(java.util.Set<java.lang.Class<?>>, jakarta.servlet.ServletContext)** method invoked by any Servlet-compliant container during container startup assuming that the spring-web module JAR is present on the classpath. This occurs through the JAR Services API ServiceLoader.load(Class) method detecting the spring-web module's **META-INF/services/jakarta.servlet.ServletContainerInitializer** service provider configuration file.

```text
Servlet Container
   |
   | (throught SPI)
   |
   +-- SpringServletContainerInitializer
       |
       | (Detecting)
       |
       +-- WebApplicationInitializer implementations
           |
           +-- Register servlets, filters, and listeners
           +-- Configure other aspects of the Servlet container
```
