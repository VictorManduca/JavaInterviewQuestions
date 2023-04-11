<h1 align="center">A Java and Spring source of interview questions</h1>

<h2 align="center">Questions</h2>

### Java
1. What is the difference between string buffer and string builder?  
```
  String buffer and StringBuilder both are mutable classes which can be used to do operation on 
  string objects such as reverse of string, concating string and etc. We can modify string without 
  creating a new object of the string. 
  A string buffer is thread-safe whereas string builder is not thread-safe
```

2. Where do the normal variables, objects store in memory?
```
  Stack in java is a section of memory which contains methods, local variables, and reference variables
  And in Java, all objects are dynamically allocated on Heap
```

3. Is java 100% OOP language? Explain it.
```
  No, because it uses primitive datatypes like int, float, char, double. 
  A pure OOP language can use nothing, but objects i.e everything must be a class. 
```

4. Why do we have different memories like heap memory, stack memory, dynamic memory?
```
In Java, we have different types of memory allocation to store data during program execution. 
Each type of memory serves a specific purpose, and the choice of memory allocation depends on 
the nature of the data being stored and how long it needs to be stored.

- Stack memory: It is used to store variables that are declared inside a method or 
a block of code. The stack is a LIFO (Last-In-First-Out) data structure, which means 
that the last item to be pushed onto the stack is the first one to be popped off. 
When a method is called, a new frame is created on the stack, which contains the local 
variables and the return address. When the method returns, the frame is removed from the stack.

- Heap memory: It is used to store objects that are dynamically allocated using the "new" keyword. 
The heap is a region of memory that is shared among all threads of the program, and objects can 
be accessed from any part of the program. The heap is managed by the garbage collector, 
which frees up memory that is no longer being used.

- Dynamic memory is typically used for data structures that need to grow or shrink dynamically, 
such as arrays and linked lists. When you allocate dynamic memory, the memory is allocated 
from the heap, and a pointer to the memory is returned. You can then use this pointer to access the memory.

In summary, the different types of memory allocation in Java serve different purposes and are 
used to store data that has different lifetimes and scopes. Understanding these memory types is 
essential for writing efficient and reliable Java programs.
```

5. Why is string immutable? In which memory does it store data?
```
The String is immutable in Java because of the security, synchronization and concurrency, 
caching, and class loading. The reason of making string final is to destroy the 
immutability and to not allow others to extend it. The String objects are cached in 
the String pool, and it makes the String immutable.
```

6. How is the data stored in HashMap?
```
In Java, a HashMap stores key-value pairs using an array of buckets, where each bucket contains 
a linked list of entries. When a new key-value pair is added, the key is hashed to determine the 
bucket index and the new entry is added to the linked list at that index. To retrieve a value for 
a given key, the key is hashed to find the corresponding bucket, and the linked list at that index 
is searched for the entry with the matching key. If the number of entries becomes too large, 
the HashMap automatically resizes the array to maintain performance.
```

7. What is the difference between HashMap and HashTable?
```
In Java, both HashMap and Hashtable are data structures that store key-value pairs using a hash table. 
However, there are some key differences between the two:

- Thread-safety: Hashtable is synchronized, meaning that it is thread-safe, 
while HashMap is not synchronized by default. However, you can make a HashMap 
thread-safe by wrapping it using the Collections.synchronizedMap() method.

- Null values: Hashtable does not allow null keys or values, while HashMap allows null keys and values.

- Iteration: The iteration order of Hashtable is not guaranteed, while HashMap does not maintain 
insertion order by default, but allows you to maintain insertion order using the LinkedHashMap class.

- Performance: HashMap is generally faster than Hashtable, due to its lack of synchronization.

In summary, while both HashMap and Hashtable are hash table data structures that store key-value pairs, 
Hashtable is synchronized and does not allow null keys or values, while HashMap is not synchronized 
by default, allows null keys and values, and has a more flexible iteration and ordering options.
```

8. What is the difference between HashSet and TreeSet?
9. Can we extend a class to interface?
```
In Java, you cannot extend a class to an interface, but you can implement an interface in a class.

When you extend a class in Java, you are creating a subclass that inherits the properties and
methods of the parent class. In contrast, when you implement an interface, you are defining a 
contract that the implementing class must follow, by providing implementations for all the methods defined in the interface.

Interfaces are a way to achieve abstraction and polymorphism in Java, allowing you to define a 
set of methods that must be implemented by any class that wants to conform to the interface. 
By implementing an interface, a class can provide a common behavior that can be used by different parts of the program.

In summary, you can implement an interface in a class in Java, but you cannot extend a class to an interface.
```

10. How will you clone the object in java? Which interface is used? Which method is used for cloning?
12. What is the use of java streams? Why should we use streams?
13. Why main function has a public static void? What does it mean?
14. What is the difference between errors and exceptions?
```
In Java, errors and exceptions are both types of throwable objects that can be used to handle 
unexpected or exceptional situations in a program. However, there are some differences between the two:

- Cause: Errors are typically caused by problems that are outside the control of the program, 
such as hardware failures, out-of-memory errors, or stack overflow errors. Exceptions, on the other hand, 
are typically caused by problems that are within the control of the program, such as invalid input, 
missing resources, or logic errors.

- Handling: Errors are usually not recoverable, and they typically indicate a severe problem that 
requires the program to terminate. As such, errors are usually not caught or handled by the program, 
and they are usually reported to the system or user in some way. Exceptions, on the other hand, 
are usually recoverable, and they can be caught and handled by the program using try-catch blocks or other mechanisms.

- Hierarchy: Errors and exceptions are both subclasses of the throwable class, but they are located at 
different levels in the hierarchy. Errors are located at the top of the hierarchy, 
and they are subclasses of the error class. Exceptions are located below errors, 
and they are further divided into checked exceptions and unchecked exceptions.

- Checked vs. Unchecked: Checked exceptions are exceptions that must be caught or declared in the method 
signature using the throws keyword, and they typically indicate a recoverable problem that the program can handle. 
Unchecked exceptions are exceptions that do not need to be caught or declared, and they typically indicate a more 
severe or unexpected problem that the program cannot handle.

In summary, errors are typically caused by problems outside the control of the program and are not recoverable, 
while exceptions are typically caused by problems within the control of the program and are usually recoverable. 
Errors are usually not handled by the program, while exceptions can be caught and handled using try-catch blocks.
```

15. What is the difference between static and non-static context?
```
Static context refers to methods and variables that are associated with the class itself, 
while non-static context refers to methods and variables that are associated with instances of the class. 
In a static context, only static methods and variables can be accessed directly, 
and they are initialized when the class is loaded into memory. In a non-static context, 
both static and non-static methods and variables can be accessed directly, 
and they are initialized when an instance of the class is created.
```

16. Can you name some synchronized collections?
17. What is the difference between the sleep and wait for method in a thread? Which method is invoked once a thread is waiting?

### Spring
1. What is the difference between @Controller and @RestController?
```
In the Spring Framework, @Controller and @RestController are used to define classes 
that handle HTTP requests. However, there are some key differences between the two:

- @Controller is used to define a class that handles HTTP requests and returns a view, 
typically in the form of an HTML page. @RestController is used to define a class that handles 
HTTP requests and returns data in the form of JSON, XML, or any other format that can be consumed by another application.

- With @Controller, the method that handles the HTTP request must return a view name, 
which is resolved by the view resolver to a concrete view. With @RestController, 
the method that handles the HTTP request typically returns a data object that is automatically 
converted to the requested format (e.g. JSON) using a message converter.

- @RestController is a combination of @Controller and @ResponseBody annotations. The @ResponseBody 
annotation is used to indicate that the method return value should be bound to the web response body. 
Therefore, @RestController eliminates the need to annotate every request handling method of the controller class with @ResponseBody.

In summary, @Controller is used to handle HTTP requests and return views, while @RestController 
is used to handle HTTP requests and return data in the form of JSON or any other format that can be consumed by another application.
```

2. What is the @Transaction in Spring?
3. What is the use of @ControllerAdvice in Spring?
4. What is the difference between spring MVC and Spring boot?
```
Spring MVC and Spring Boot are both frameworks developed by the Spring community for building 
web applications in Java. However, there are some key differences between the two:

- Configuration: Spring MVC requires a lot of manual configuration to set up a web application, 
including configuring the dispatcher servlet, view resolver, database connection, and more. 
In contrast, Spring Boot reduces the amount of boilerplate configuration required by providing 
auto-configuration that detects and configures many of the components needed to build a web application.

- Embedded Server: Spring Boot provides an embedded server (Tomcat, Jetty, or Undertow) 
that is included in the application. This allows developers to quickly and easily run and deploy the 
application without the need for an external web server. Spring MVC, on the other hand, 
requires an external web server to run the application.

- Convention over Configuration: Spring Boot follows the "convention over configuration" principle, 
which means that it uses sensible defaults and conventions to minimize the need for explicit configuration. 
Spring MVC, on the other hand, requires more explicit configuration.

- Dependency Management: Spring Boot provides dependency management out-of-the-box, which means 
that it automatically manages the versions of all dependencies used in the application. 
Spring MVC, on the other hand, requires developers to manage dependencies manually.

In summary, Spring MVC is a framework for building web applications that requires a lot of manual 
configuration, while Spring Boot is a framework that provides auto-configuration, an embedded server, 
and follows the "convention over configuration" principle to reduce the amount of boilerplate code needed to build a web application.
```

5. What is the use of @SpringBootApplication?
```
@SpringBootApplication is a convenience annotation provided by the Spring Boot framework 
that combines several other annotations commonly used in Spring applications. It is used to enable the 
Spring Boot features, such as auto-configuration, component scanning, and more.

Here are the annotations that @SpringBootApplication combines:

- @Configuration: This annotation is used to indicate that the class declares one or 
more @Bean methods that are used to configure the Spring application context.

- @EnableAutoConfiguration: This annotation is used to enable Spring Boot's auto-configuration mechanism. 
This mechanism automatically configures the Spring application based on the dependencies on the classpath.

- @ComponentScan: This annotation is used to enable component scanning in the Spring application context. 
It allows Spring to scan and detect the beans (components, services, repositories, etc.) in 
your application and make them available for dependency injection.

By using @SpringBootApplication, you can avoid manually configuring all of these annotations in your 
application. It is a shortcut to enable all the commonly used features of Spring Boot and helps to reduce boilerplate code.

In summary, @SpringBootApplication is a convenience annotation that combines several other commonly 
used annotations in Spring applications. It is used to enable Spring Boot's features, 
such as auto-configuration, component scanning, and more.
```

6. What is Springboot Actuator?
7. How do you communicate between services in two different boot services?
8. Can we have two @ControllerAdvice in one project?
9. What are the propagations and isolations levels do you know in Spring?
10. Explain the difference between Spring Boot and Spring framework
```
Spring Boot is a more opinionated, lightweight, and streamlined version of the Spring Framework that 
provides auto-configuration, an embedded server, and dependency management to reduce the amount of 
boilerplate code needed to build a web application. Spring Framework is a more comprehensive and complex 
framework that provides a wide range of features and capabilities for building enterprise-level applications, 
but requires more manual configuration and management.
```

11. What is @Qualifier used for in Spring?

### Hibernate
1.  What is the use of @Lazy and @Eager in hibernate?
2. What are the design patterns used in hibernate framework?
```
Hibernate is a popular Object-Relational Mapping (ORM) framework that provides a set of design 
patterns to simplify the database interaction and management in Java applications. 
Here are some of the design patterns used in Hibernate:

- Factory Method Pattern: Hibernate uses a SessionFactory to create Session instances, 
which represent a connection to the database. The SessionFactory is created using the Factory Method Pattern, 
which allows for flexibility and customization in creating the SessionFactory.

- Proxy Pattern: Hibernate uses the Proxy Pattern to implement lazy loading of data. 
When a persistent object is loaded, Hibernate creates a proxy object that represents the persistent object. 
The proxy object does not load the data until it is needed, which improves performance.

- DAO Pattern: Hibernate encourages the use of the Data Access Object (DAO) Pattern to separate the 
database access logic from the business logic of the application. The DAO Pattern provides a simple 
interface for accessing the database, which can be easily replaced with a different implementation if needed.

- Unit of Work Pattern: Hibernate uses the Unit of Work Pattern to track changes to persistent objects and 
manage transactions. The Unit of Work Pattern ensures that changes to persistent objects are 
synchronized with the database and that transactions are atomic.

- Template Method Pattern: Hibernate provides a template for performing common database operations, 
such as CRUD (Create, Read, Update, Delete) operations. The template uses the Template Method Pattern to 
define the overall structure of the operation, while allowing for customization of individual steps.

In summary, Hibernate uses a variety of design patterns, including the Factory Method Pattern, 
Proxy Pattern, DAO Pattern, Unit of Work Pattern, and Template Method Pattern, 
to simplify database interaction and management in Java applications.
```

3. How to enable the second-level cache?
```
To enable the second-level cache in Hibernate, you need to follow these steps:

- Add the necessary cache provider dependencies to your project.
- Configure the cache provider and the cache region in your Hibernate configuration file.
- Annotate the entity classes you want to cache with the @Cacheable annotation.
- Enable caching for queries by setting the hibernate.cache.use_query_cache configuration property to true.

Once the second-level cache is enabled, Hibernate will cache the entity data and query results in memory, 
reducing the number of database queries and improving performance.
```

### Database | SQL
1. What is View in POSTGRESQL | Materialized View in POSTGRESQL | Refresh Materialized view | SQL Views?
```
  In a database, a view is the result set of a stored query on the data, which the 
  database users can query just as they would in a persistent database collection object. 
  This pre-established query command is kept in the database dictionary
```

2. What is the difference between vertical partitioning vs horizontal partitioning in database?
3. Hany types of indexes are there? What are they? When to use what? Is indexing DBA Job or Developer job?
4. What is the best way to modify the existing composite key in SQL?
5. Consider if any update is taking time. What are the consequences that are causing performance issues? How can you avoid it?
```
If updates are taking a long time to complete, it can cause several performance issues in an application:

- Increased response time: Slow updates can increase the response time of the application, 
which can lead to a poor user experience.

- Locking and blocking: If updates are locking the database table or blocking other transactions, 
it can cause contention and reduce concurrency, leading to further performance issues.

- Increased resource usage: Slow updates can increase the CPU, memory, and disk usage of the application 
server and database server, reducing overall system performance.

To avoid these issues and improve the performance of updates, you can try the following techniques:

- Optimize database design: Make sure the database schema is properly designed and normalized, 
and that indexes are created on the appropriate columns to speed up queries.

- Optimize SQL queries: Ensure that SQL queries are optimized by using proper syntax, 
avoiding unnecessary joins or subqueries, and using indexed columns in the WHERE clause.

- Batch updates: If you are updating a large number of records, 
consider using batch updates to minimize the number of round trips to the database.

- Use caching: Consider caching frequently accessed data in memory to reduce the number of database queries.

- Use asynchronous processing: If updates are taking a long time to complete, 
consider using asynchronous processing techniques such as background tasks or queues to avoid blocking the application.

By applying these techniques, you can improve the performance of updates and avoid performance issues in your application.
```
