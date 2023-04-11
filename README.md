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
15. What is the difference between static and non-static context?
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
5. What is the use of @SpringBootApplication?
6. What is Springboot Actuator?
7. How do you communicate between services in two different boot services?
8. Can we have two @ControllerAdvice in one project?
9. What are the propagations and isolations levels do you know in Spring?
10. Explain the difference between Spring Boot and Spring framework
11. What is @Qualifier used for in Spring?

### Hibernate
1.  What is the use of @Lazy and @Eager in hibernate?
2. What are the design patterns used in hibernate framework?
3. How to enable the second-level cache?

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
