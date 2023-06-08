# Spring Boot Concepts
  
  ## Inversion of Control (IOC)
  - It's a Design Pattern that promotes loosing coupling, modularity and simplicity of the application development;
  - The control over the creation and management of objects is inverted or handed over to a container or framework. The responsability of new object creating is delagated to a container or framework and it's also responsible for managing the lifecycle of objects and their dependencies;
  - **IOC Container in Spring Boot: Spring Container or Application Context**
  - **Java Objects in Spring Boot: Beans**
  - How it works:
  1. **Dependencies Injection (DI):** Spring Boot injects dependencies into a bean at runtime with constructor, setter or field injection;
  2. **Configuration:** Spring Boot uses a configuration metadata file as XML-based configuration or usually annotation-based configuration as @Component, @Service, @Repository, and @Autowired defining the beans and their dependencies;
  3. **Bean Lifecycle:** when application starts, the containers creates and initialize the beans and when it shut downs, the containers handle the destruction;
  4. **Loosing Coupling:** remove explicity dependencies between classes, they're expressed through interfaces or abastractions insted.
 
 ## Aspect-Oriented Programming (AOP)
  - It's a programming paradigm and powerful mechanism for managing cross-cutting concerns in applications. 
  - It allows you to modularize behavior that cuts across multiple components, promotes code modularity, and improves the maintainability of the Spring Boot applications.
  - Complement object oriented programming (OOP) by addressing cross-cutting concerns in software development
  - **Cross-cutting concern:** functionality or feature that cuts accross multiples modules or components of an application
     - Examples: logging, security, transaction management, caching, and error handling
  -  Do this through the concept of aspects, which encapsulate behavior that can be applied to multiple components or objects in a declarative manner
  -  Key concepts and features of AOP in Spring Boot:
  1. **Aspect:** modular unit that encapsulates cross-cutting concerns and defines reusable pieces of code that can be applied to different components, consisting of advice and pointcuts;
  2. **Advice:** represents the behavior that is applied to the target objects, as before advice, after returning advice, after throwing advice, after advice, around advice;
  3. **Pointcut:**  a predicate that defines the join points where an aspect's advice should be applied. Join points represent specific moments during the execution of an application, such as method invocations, field access, or exception handling;
  4. **AspectJ Expressions:** used by Spring AOP to define pointcuts. Povide a rich and flexible syntax to specify the join points based on method signatures, package names, annotations, and more;
  5. **Weaving:** the process of applying aspects to the target objects or join points at runtime. It can be done either at compile-time or dynamically during runtime. Spring Boot performs runtime weaving, meaning that aspects are applied dynamically as the application runs;
  6. **Proxy:** Spring Boot uses dynamic proxies or byte code manipulation (through libraries like CGLIB) to create AOP proxies. Proxies intercept method invocations and apply the advice defined in aspects;
  7. **AOP Support in Spring Boot:** the integration of AOP with the Spring Framework allow the use of annotations like @Aspect, @Before, @After, @Around, etc., to define aspects and advice. Additionally, Spring Boot offers auto-configuration for common cross-cutting concerns, such as transaction management and logging.

 ## Profile
  - Mechanism for configuring an application based on different environments, deployment scenarios, or specific runtime conditions
  - Allow you to define and manage multiple sets of configuration properties and beans, which can be activated selectively depending on the current runtime environment
  - It's useful when there's different configurations for various deployment environments, such as development, testing, staging, and production
  - How it works:
  1. **Configuration Properties:** Spring Boot allows you to define configuration properties specific to each profile, by using profiles, you can have separate property files or sections in the same file for each environment;
  2. **Profile-Specific Configuration Files:** allows to organize the configuration by placing profile-specific property files alongside the main application.properties or application.yml file. The convention is to name these files as application-{profile}.properties or application-{profile}.yml, where {profile} is the name of the profile (e.g., application-dev.properties);
  3. **Default Profile:** If no profile is explicitly activated, Spring Boot uses the default profile. The default profile is typically used when running the application without specifying any active profiles. By default, Spring Boot looks for properties in the main application.properties or application.yml file.

 ## Spring Boot Actuator
  - Module in the Spring Boot framework that provides production-ready features for monitoring and managing Spring Boot applications
  - Allows to gain valuable insights into the application 
  - It offers a set of built-in endpoints, metrics, and health indicators that enable to gather valuable runtime information and perform various management tasks
  - **Endpoint Exposure:** Actuator provides a collection of RESTful endpoints that expose management and monitoring information about the application. These endpoints are typically available under the /actuator base path and provide various operations for different purposes, such as health checks, metrics, environment details, logging configuration, thread dumps, and more.
  
