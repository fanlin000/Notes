JAVA CORE

Java 8 new feature
Lambda Expressions（it similar to methods, no body but take a parameter and return a value）/Functional Interface(an interface with maximum one abstract method)
Default methods (the ability to add full implementations in interfaces besides abstract methods)
Method References(enable us to define Lambda Expressions by referring to methods directly using their names)

## JRE/JDK/JVM:
JDK is a software development environment. It includes the JRE, an interpreter/loader (Java), a compiler (javac), an archiver (jar), a documentation generator (Javadoc), and other tools needed in Java development. 
JRE provides the minimum requirements for executing a Java application; It consists of the JVM, core classes, and supporting files.
A JVM is a virtual machine that enables a computer to run Java programs as well as programs written in other languages that are also compiled to Java bytecode.

Is Java "pass-by-reference" or "pass-by-value"?      Java is always pass by value.

a hash table, it is internally implemented by using an array and linked list data structure. The array data structure is used as a bucket, while a linked list is used to store all mappings which land in the same bucket. From Java 8 onwards, the linked list is dynamically replaced by binary search tree, once a number of elements in the linked list cross a certain threshold to improve performance.

## Diff between final, finally, finalize.
Final: The final keyword is used to make any class or amethod or a field as unchangeable. You can’t extend a final class, you can’t override a final method and you can’t change the value of a final field.
Finally: . The finally block executes whether exception rise or not and whether exception handled or not. The finally block in java is used to put important codes such as clean up code e.g. closing the file or closing the connection
Finalize: It is a method that the Garbage Collector to perform clean-up activity. Clean-up activity means closing the resources associated with that object like Database Connection, Network Connection

### throws/ throw
The throw keyword is used to explicitly throw an exception from a method or any block of code. We can throw either checked or unchecked exception. The throw keyword is mainly used to throw custom exceptions.

The Throws keyword is used in the signature of method to indicate that this method might throw one of the listed type exceptions. The caller to these methods has to handle the exception using a try-catch block. Throws keyword is required only for checked exception and usage of throws keyword for unchecked exception is meaningless.
throws keyword is required only to convince compiler and usage of throws keyword does not prevent abnormal termination of program. By the help of throws keyword we can provide information to the caller of the method about the exception.
The signature of a method consists of the name of the method and its parameters.

String: String variables are immutable
### String Buffer: 
string values are stored in a stack. If the values are changed then the new value replaces the older value. The string buffer is synchronized which is thread-safe. Performance is slower than the String Builder.
### String Builder: 
This is the same as String Buffer except for the String Builder which is not threaded safely that is not synchronized. So obviously the performance is fast.

### Multithreading 
refers to a process of executing two or more threads simultaneously for maximum utilization of the CPU. 
### The error 
occurs due to the lack of system resources and our application should not catch errors. E.g. system crash error and out of memory error. Errors mostly occur at runtime. 
Exceptions are the problems which can occur at runtime and compile time. It mainly occurs in the code written by the developers. 

### daemon thread
a thread that does not prevent the JVM from exiting when the program finishes but the thread is still running. An example for a daemon thread is the garbage collection. Daemon thread is a low priority thread that runs in background to perform tasks such as garbage collection.

In Java, a static member is a member of a class that isn't associated with an instance of a class. Instead, the member belongs to the class itself. As a result, you can access the static member without first creating a class instance.

what's the pros/cons using static in memory management
pros: it provides a performance advantage. Static methods can be called with less overhead so any method that doesn't need a reference to this ought to be made static. It’s always in stack.
Cons: The main disadvantage is that you cannot swap, override or choose method implementations at runtime.

HashSet：HashSet is internally implemented using HashTable and Set interface.

HashSet : set interface , HashMap : map interface
HashMap requires two objects put(K key, V Value) to add an element to HashMap object, while HashSet requires only one object 

DualHashBidiMap: use key to find value, use value to find keys.

### array vs arraylist
1. Array is a fixed length data structure whereas ArrayList is a variable length Collection class. We cannot change length of array once created in Java but ArrayList can be changed.
2.  ArrayList can only store objects. But array can contain both primitives and objects in Java. Since Java 5, primitives are automatically converted in objects which is known as auto-boxing.

### arraylist vs linkedlist
1. ArrayList internally uses a dynamic array. LinkedList internally uses a doubly linked list. 
2. Manipulation with ArrayList is slow， If any element is removed from the array, all the bits are shifted in memory. Manipulation with LinkedList is faster. 
3. ArrayList is better for storing and accessing data. LinkedList is better for manipulating data. 
4. An ArrayList class can act as a list only because it implements List only. LinkedList class can act as a list and queue both because it implements List and Deque interfaces.

### Diff between List and set
List allows duplicate elements. Set doesn’t allow duplicate elements.
The List is an ordered sequence. The Set is an unordered sequence.
List implementations are ArrayList, LinkedList, Vector, Stack. Set implementations are HashSet, LinkedHashSet.

hashmap? a hash table is a data structure. key-value pair. O(1).

### hash table & hash map
1. HashMap is non-synchronized. It is not thread-safe whereas Hashtable is synchronized. It is thread-safe and can be shared with many threads. 
2. HashMap allows null keys and values whereas Hashtable doesn’t allow null key or value.

### stack/heap/queue
Heap: A tree-based data structure. It is ordered. heap can be either a min heap or a max heap. Usually for kth largest value in a array.
A queue can be implemented using an array. FIFO
A stack can be implemented using an array or a linked list. LIFO

Types of Memory areas allocated by the JVM:
Class(Method) Area/Heap/Stack/Program Counter Register/Native Method Stack

### Difference between Java Heap Space and Stack Memory
1. Java Heap Space is used throughout the application, but Stack is only used for the currently running methods 
2. The Heap Space contains all objects are created, but Stack contains any reference to those objects and primitive. 
3. Memory allocation in the Heap Space is accessed through a complex, young-generation, old-generation system. Stack is accessed through a last-in, first-out (LIFO) memory allocation system.
4. Heap Spaces larger than Stack. Stack is temporary, but faster.

The garbage collector finds these unused objects and deletes them to free up memory.

### how to declare a thread: 
a) Extend Thread class 
b) Implement Runnable interface
You can create threads by implementing the runnable interface and overriding the run() method. Then, you can create a thread object and call the start() method.

What is the purpose of a Volatile Variable?
Used to make thread safe.  variables are going to get read by multiple threads, but written to by only one thread . variable stored in main memory
### Volatile
The values of the volatile variable will never be cached and always fetched from main memory. All writes and reads will be done from the main memory. Can cause data inconsistency problem. 

volatile vs Synchronization
Volatile keyword is not a substitute of synchronized keyword
Use Volatile when you variables are going to get read by multiple threads, but written to by only one thread.
Use Synchronized when your variables will get read and written to by multiple threads.

Checked Exception: are checked by the compiler at the time of compilation.  Classes that extend Throwable class except Runtime exception and Error are called checked Exception. Checked Exceptions must either declare the exception using throws keyword (or) surrounded by appropriate try/catch. For Example, ClassNotFound Exception
Unchecked Exception: These exceptions are not checked during the compile time by the compiler. e.g Arithmetic Exception/ArrayIndexOutOfBounds Exception

### getter/setter,
getters retrieves the private variables. A setters set the values of the attributes.

Why are Getter and Setter better than directly changing and retrieving fields ?
Better control of class attributes and methods
Class attributes can be made read-only (if you only use the get method), or write-only (if you only use the set method)
Flexible: the programmer can change one part of the code without affecting other parts
Increased security of data
 Validations can be performed before setting the variables. 
Join () method is used to join one thread with the end of the currently running thread.

the flow of execution is called Thread.

## OOP
explain four fundamentals of OOP
（PIED）Inheritance, Encapsulation, Polymorphism, and Data abstraction.

## Encapsulation
Java is a mechanism of wrapping the variables and methods together as a single unit. In encapsulation, the variables of a class will be hidden from other classes, and can be accessed only through the methods of their current class. Therefore, it is also known as data hiding.
In Java, Data Abstraction is defined as the process of reducing the object to its essence so that only the necessary characteristics are exposed to the users.
The abstract keyword is a non-access modifier, used for classes and methods:

### Abstract class is a restricted class that cannot be used to create objects (to access it, it must be inherited from another class). Abstract classes should have at least one abstract method. , i.e., methods without a body. It can have multiple concrete methods.

### Inheritance vs. Polymorphism
1. Inheritance is allows a class to inherit behavior and data from other class.
2. Polymorphism allows a single method to behave in different ways in different object. (overriding & overloading)

###  overload / override
1. Overriding implements Runtime Polymorphism whereas Overloading implements Compile time polymorphism.
2. The method Overriding occurs between superclass and subclass. Overloading occurs between the methods in the same class.
3. Overriding methods have the same signature. Overloaded method names are the same but the parameters are different.
4. With Overloading, the method to call is determined at the compile-time. With overriding, the method call is determined at the runtime based on the object type.
5. If overriding breaks, it can cause serious issues in our program because the effect will be visible at runtime. Whereas if overloading breaks, the compile-time error will come and it’s easy to fix.

Downside of multi-inheritance
The main consequence of multiple inheritance is the diamond problem. It causes ambiguity and complexity.

###  When to use interface
1. We want to specify the behaviour of a particular data type, but not concerned about implementations.
2. To build loosely coupled, entensible, testable applications.

Abstract Class vs Interface?， and difference
Abstract class: is a restricted class that cannot be used to create objects (to access it, it must be inherited from another class).
An interface is a template which has only method declarations and not the method implementation. Multiple inheritances cannot be achieved in java. To overcome this problem the Interface concept is introduced.
Abstract Class:(3)
Abstract classes have a default constructor.
The class which extends the Abstract class shouldn’t require the implementation of all the methods, only Abstract methods need to be implemented in the concrete sub-class.
Abstract class contains instance variables.
Interface:
It doesn’t have any constructor and couldn’t be instantiated.
The abstract method alone should be declared.
Classes that implement the interface should provide the implementation for all the methods.
The interface contains only constants.

### Abstract keyword
abstract keyword is a non-access modifier, used for classes and methods:
abstract class: is a restricted class that cannot be used to create objects (to access it, it must be inherited from another class). 
Abstract method: can only be used in an abstract class, and it does not have a body. The body is provided by the subclass (inherited from).

why does abstract class have a contructor
We need contructor to initialize the non-abstract methods and instance variables. The constructor inside the abstract class can only be called during constructor chaining i.e. when we create an instance of sub-classes. 

A local variable is a variable that is declared inside a method or a constructor. 
An instance variable is a variable declared in a class, but outside a method. These variables represent the object state throughout the class.  Any object of that class has its own copy of that instance variable. 

Protected: Protected members of a class are visible within the package. Therefore, we can only access within the package but can be accessed to the subclasses outside the package through the inheritance only.

Why do we use inheritance? The aim of inheritance is to provide the reusability of code. 


###  SQL
what is transaction
When a group of database operations is done as a single unit then it is called a transaction. It is mandatory to complete all the tasks of a transaction to make the transaction successful.

### mysql and nosql
SQL databases are table-based on the other hand NoSQL databases are either key-value pairs, document-based, graph databases or wide-column stores. 
SQL databases are primarily called as Relational Databases; whereas NoSQL database are primarily called as non-relational or distributed database. 
SQL databases are not suited for hierarchical data storage. NoSQL databases are best suited for hierarchical data storage.
SQL databases are best suited for complex queries. NoSQL databases are not so good for complex queries

### primary key vs foreign key
A primary key is a set of columns in a table whose values uniquely identify a row in the table.  A foreign key is a set of columns in a table whose values correspond to the values of the primary key in another table(parent table)

### The differences between these two keys are mentioned below:
The primary key can never accept a NULL value but foreign key accepts a NULL value.
The primary key uniquely identifies a record, whereas foreign key refers to the primary key of another table.
When a record is inserted in a table that contains the primary key then it is not necessary to insert the value on the table that contains this primary key field as the foreign key.
When a record is deleted from the table that contains the primary key then the corresponding record must be deleted from the table containing the foreign key for data consistency. But any record can be deleted from the table that contains a foreign key without deleting a related record of another table.


### what's the query
A query is a request for data or information from database tables

**Union** is used to combine two or more queries into a single result set using the select statements. 
UNION ALL command is equal to UNION command, The difference between Union and Union all is that Union all will not eliminate duplicate rows.

**Group by** statement is used to group the rows that have the same value. 
Order by keyword sort the result-set either in ascending or in descending order. 


### Protected vs public
Protected can be declared for Variables, methods, and constructor(but not class neither interface), it makes can be accessed only by the subclasses(whether this's in package or outside of package).

The public keyword is an access modifier used for classes, attributes, methods and constructors, making them accessible by any other class

protected and private can not be used with class, which means they can only be used to method and variable.

class can only be default class or public class

Interface are by default public.

### final
final class: can not extent the class
final variable: no change
final method: no override

### Deep copy VS shallow copy
shallow copy only copy the references of those objects. One object, two reference variable.
Deep copy means a new object will be created, and all the values of original object will be copied to the new object. Two object, two reference variable. We have to override the clone() method to use deep copy.
 
### ConcurrentHashMap
ConcurrentHashMap class is thread-safe. It works by dividing complete hashtable array into segments or portions and allowing parallel access to those segments. The locking is at a much finer granularity at a hashmap bucket level(all methods are synchronized on Hashtable instances using the synchronized keyword). ConcurrentHashMap does not allow NULL values, so the key can not be null in ConcurrentHashMap.

If a thread-safe highly-concurrent implementation is desired, then it is recommended to use ConcurrentHashMap in place of Hashtable.

### Synchronized HashMap
It locks the whole map. Performance of ConcurrentHashMap is relatively better than the Synchronized HashMap. Synchronized HashMap allows inserting null as a key. ConcuurentHashMap doesn’t allow inserting null as a key or value.

### referency data type
Reference datatypes in java are those which contains reference/address of dynamically created objects. These are not predefined like primitive data types.

Following are the reference types in Java.

1. class types − This reference type points to an object of a class.

2. array types − This reference type points to an array.

3. interface types − This reference type points to an object of a class which implements an interface.

Once we create a variable of these types (i.e. when we create an array or object, class or interface).

1. These variables only store the address of these values.

2. Default value of any reference variable is null.

3. A reference variable can be used to refer any object of the declared type or any compatible type.

### static method and default method introduced in Java 8
They are used to create a common feature/action for the class implantate them. 

Static method in interface means we can directly use the method by use the interfaceName.methodName or className.methodName.

default methods which allow the interfaces to have methods with implementation.

### Switch
two point to memorize:
1. use break. Without break, it will continue execute to the next case. 
2. default statement is used when none of the cases is true.

### access modifer is used for encapsulation

### change the final reference is a checked exception.

### immutable class
An immutable class is simply a class whose instances cannot be modified. 
e.g. String, Integer...

### how to customize our own immutable class (The memory trick to follow the order of writing a class)
1. Declare the class as final so it can’t be extended.
2. Make all fields private and final so that direct access is not allowed.
3. Initialize all the fields via a constructor performing deep copy
4. Don’t provide setter methods for variables.
5. Perform cloning of objects in the getter methods to return a copy rather than returning the actual object reference.

### Memory area (it is the logical way)
1.Method Area: It stores class level data of every class such as the runtime constant pool, field and method data, the code for methods, Static block. Also called class area
2.Heap
3. Stack
4. Program Counter Register
5. Native Method Stack

### Junit 4.0
Unit is the testing framework, it is used for unit testing of Java code. JUnit = Java + Unit Testing  

The process of testing individual functionality (known as a unit) of the application is called unit testing.

### Maven
Maven is a dependency management system. It provides the developer a complete build lifecycle framework. On executing Maven commands, it will look for POM file in Maven; it will run the command on the resources described in the POM.

POM
POM (Project Object Model) is the fundamental unit of work. It is an XML file which holds the information about the project and configuration details used to build a project by Maven.

Explain what is Maven artifact?
In Maven terminology, an artifact is an output generated after a Maven project build. It can be, for example, a jar, war, or any other executable file.

Explain what is Maven Repository? What are their types?

A Maven repository is a location where all the project jars, library jars, plugins or any other particular project related artifacts are stored and can be easily used by Maven.

### JDK/JRE/JVM
the relation of subset
JVM = stands for Java Virtual Machine, is a virtual machine that understands and runs java bytecodes. JVM has the memory structure is the explicit difference from normal VM.
JRE = JVM + java SE stardard librart
JDK: JRE + dev tools

### Garabage collector
#### How does it internally works?
Minor GC is fot the young generation,counter to count the life cycle, one the life cycle pass the max tenuring threshold, the object will be move the old generations. Major GC for the old generation.

#### Serial collector:
a basic collector runs in single thread.

#### concurent mark sweep collector(CMS):
A thread that performs GC along with application execution as the application runs. it doesn't wait for the old gernation to be full to begin the major collections. It stops the world only during mark/remark.  The newer garbage-first collector (G1) replace CMS since JAVA 9.

#### parallel collector
This is the default GC for Java 8
Use multiple CPUs to perform GC, mutlipple threads doing mark/sweep etc, it doen't kick in untill heap is full or near-full, stop the world when it runs. So it's not concurrent

#### when to use which?(hardware capability + Application requirements) 
use CMS when: there is more memory, CPUS. Application require responsive and short lantency.
Use parallel GC when: thre is less memory, CPUs,  Application require high throughput and withstand pause.

Throughput is the amount of a product or service that a company can produce and deliver to a client within a specified period of time. 

#### ZGC is a concurrent GC 

#### java 11 use G1 GC

### Java hotspot
HotSpot, also called Java HotSpot Virtual Machine, or HotSpot JVM, is an implementation of the JVM (Java Virtual Machine) Specification originallly developed by Sun Microsystems and now supported by Oracle Corporation.

HotSpot has key feature called adaptive compiler that application code will be analyzed as it runs to detect performance bottlenecks, or "hot spots". HotSpot will then compile those hot spots for a boost in performance.

### casting
implicit casting: coverting without losing data. e.g. int ---> double

explicit casting: Coverting with losing data. 

Down casting: form superclass to subclass  ---> explicitly

Up casting: from subclass to a superclass ---> implicity

### autobox / unboxing
Autoboxing is the automatic convert primitive types to their corresponding object wrapper classes.
unboxing is the automatic convert object wrapper classes to their corresponding primitive types.

### Interface vs Abstract class (multi-inheritance+ final+ access modifier)
1. Interface can do multi-inheritance.
2. Final Variables: Variables declared in interface are by default final and static. An abstract class may contain non-final variables.
3. Accessibility of Data Members: Members of a Java interface are public by default. A Java abstract class can have class members like private, protected, etc.

### class loader
Class loaders are responsible for loading Java classes during runtime dynamically to the JVM.  Also, they are part of the JRE.
***bootstrap or primordial class loader*** loads the java.lang.ClassLoader itself. It's mainly responsible for loading JDK internal classes. This bootstrap class loader is part of the core JVM and is written in native code.

The ***extension class loader*** is a child of the bootstrap class loader and are reponsible for loading the extensions of the standard core Java classes so that it's available to all applications running on the platform. It loads the jar package.

***application class loader***loads all the application level classes into the JVM. It loads files found in the classpath environment variableAlso, it's a child of Extensions classloader.

![image](https://user-images.githubusercontent.com/35554521/146659820-85a60803-d9f5-4534-8e3e-1fd117a3fb20.png)

### Where is constant string pool
in heap memory. Constant string pool stores literal string values.

### Method area
In the method area, all class level information like class name, immediate parent class name, methods and variables information etc. are stored, including static variables.

### static
static method and static variable are in method area. method area are in the metaspace.

static method have to use static variable

### throw 
two purpose:
1. let caller know that there is an error and he should handle it gracefully.
2. used for custom exception. Exceptions that are specific to the business logic and workflow. These help the application users or the developers understand what the exact problem is.

### Error 
stackoverflow is error

### final, Finally, finalize.
The final keyword can be used with class method and variable. A final class cannot be inherited, a final method cannot be overridden and a final variable cannot be reassigned.

The finally,used in try-catch, whatever exception happened or not, the finally block will excuted. Using a finally block allows you to run any cleanup-type statements to realse to resource. System exit can interrupt the finally

finalize() method is used to perform clean-up activity before the GC. Clean-up activity means closing the resources associated with that object like Database Connection, Network Connection or we can say resource de-allocation. Remember it is not a reserved keyword. Once the finalize method completes immediately Garbage Collector destroy that object.


### thread
Thread share method area and heap, but each thread have their own stack

Thread safe is about reference.

### why to override hashcode() and equals()
If we override the equals(), then we have to override hashcode(). Otherwise, it could cause some problems for hash based data structures. For example, the same object value would have different hash value, then they woule both be added to the hashmap, then the keys would be duplicate. The Reverse is not true, it would cause any troubles, but it's the convention and best pratice to override them both. I will override them both.

### Hashset
Hashset internally use HashMap. It takes the keys as its elements, but set the values to be null always.

Sets.intersection(a,b) / Sets.Union(a, b) / set1.removeAll(set2)

### Integer
Integer cache values from –128 to +127. 

### == equal equal sign

### Vector
Vector is also a dynamic array. Vector is synchronized. vector increments 100% of the current array size if the number of elements exceeds its capacity. Arraylist is preferred than vector.

### comparator / comparable
1.	Different implementation. Comparable is used to defined the natural ordering of the object. It’s the object class implement the comparable class and override the compareTo() method. 
2.	You can only have one compareTo()(comaparable) implementation for an object, while you can define multiple Comparator for comparing objects on different parameters. THEREFORE, The Comparator is usually used to define any alternative ordering for an object.

It's also a best practice to declare Comparator as nested static classes in Java, because they are closely associated with objects they compare.
compareTo() and compare() method in Java must be consistent with equals() implementation i.e. if two methods are equal by equals() method then compareTo() and compare() must return zero.

### So why use a Comparator if we already have Comparable?
1. Sometimes we can't modify the source code of the class whose objects we want to sort.
2. Using Comparators allows us to avoid adding additional code to our domain classes
3. We can define multiple different comparison strategies, which isn't possible when using Comparable

### Static block
A static block run once for each time a class is loaded into memory. It's stored in method area.

### Throws vs Throw
Throws clause is used to declare an exception in the method signature, which means it works similar to the try-catch block. The exception of throws in superclass have to be the superclass of exception of throws in subclass。

Throw keyword is used to throw an exception explicitly in the method body.

### Serializable
Serialization is the process of turning ***an object in memory*** into a ***stream of bytes*** so you can do stuff like store it on disk or send it over the network.

Deserialization is the reverse process: turning a stream of bytes into an object in memory.

implement Serializable interface ---> FileOutputStream ---> ObjectOutputStream

InputStream and OutputStream are two parent classes of byteStream

Reader and Writer are two parents classes of character stream

#### What is need of Serialization?
Answer:
Serialization is usually used when there is need to send your data over network or to store in files. By data I mean objects and not text.

Now the problem is your Network infrastructure and your Hard disk is hardware components that understand bits and bytes but not Java objects.

Serializable is marker interface.Marker interface in Java is interfaces with no field or methods or in simple word empty interface in java is called marker interface.

#### Can you Serialize static variables?
Answer :
No,you can’t.As you know static variable are at class level not at object level and you serialize a object so you can’t serialize static variables.

#### How can you avoid certain member variable of class to be serialized?
You can mark that variable as either static or transient. Let’s see a simple example using transient variable.
Transient variable is the variable whose value is not serialized during serialization. You will get default value for these variable when you deserialize it.

#### What  if superclass is Serializable?  Does that mean child class is automatically Serializable?
Answer : Yes. If you don’t want subclass to serializable then you need to implement writeObject() and readObject() method and need to throw NotSerializableException from this methods.

### Java double lose precision
Use BigDecimal.  -- > bigDecimal1.subtract(bigDecimal2)

x^2 / x to the power of 2 is always accurate.

### String[] args
args stands for the name of String array. The parameter of main method can not be changed

### There is no static local variable

### volatile 
The Java volatile keyword is used to mark a Java variable as "being stored in main memory". So any changes to the variable are across threads.

### Enum
Enum is the lists of constants. 

Q: Can Enum constants can be declared as static and final?
A: Yes. Enum constants are public static and final and are accessible directly using enum name.

Q: Can a constuctor be invoked using an Enum?
A: Yes we can use the constuctor with the name of Enum.

Q: Can we extend an Enum to add elements?
A: No, we cannot extend Enum further in the Code. It is defined only with keyword Enum and filled with elements but these elements cannot be added further in the program using some alternative method.

Q: Can we create object of Enum?
A: No, it is not possible to create the object of Enum.

Q: Can Enum implement an interface in Java?
A: Yes, Enum can implement an interface in Java. Since enum is a type, similar to class and interface, it can implement an interface. This gives a lot of flexibility to use Enum as a specialized implementation in some cases. You can further see here an example of Enum implementing an interface in Java.

### @Retention and Annotation
annotation helps to change the runtime exception to be compiler time exception
@inherited is a type of meta-annotation used to annotate custom annotations so that the subclass can inherit those custom annotations. 

By default, Java annotations are not shown in the documentation created using the Javadoc tool. To ensure that our custom annotations are shown in the documentation, we use @Documented annotation to annotate our custom annotations. @Documented is a meta-annotation (an annotation applied to other annotations)

Q1. What Are Annotations? What Are Their Typical Use Cases?
Annotations are metadata bound to java class, method, interface or variables and have no effect on the operation of the code they operate.

Their typical uses cases are:
1. Information for the compiler – with annotations, the compiler can detect errors or suppress warnings
2. Compile-time and deployment-time processing – software tools can process annotations and generate code, configuration files, etc.
3. Runtime processing – annotations can be examined at runtime to customize the behavior of a program

Q3. How Can You Create an Annotation?
```
public @interface SimpleAnnotation {
    //whose body contains annotation type element
    String value();

    int[] types();
}
```

Q6. Is There a Way to Limit the Elements in Which an Annotation Can Be Applied?
```
@Target({ ElementType.FIELD, ElementType.METHOD, ElementType.PACKAGE })
//pass multiple constants if we want to make it applicable in more contexts
@Target({})
//it cannot be used to annotate anything
```

Q7. What Are Meta-Annotations?
Meta-Annotations? Are annotations that apply to other annotations.

All annotations that aren't marked with @Target, or are marked with it but include ANNOTATION_TYPE constant are also meta-annotations
'''
@Target(ElementType.ANNOTATION_TYPE)
public @interface SimpleAnnotation {
    // ...
}
'''

Q9. How Can You Retrieve Annotations? How Does This Relate to Its Retention Policy?
You can use the Reflection API or an annotation processor to retrieve annotations.

The @Retention annotation and its RetentionPolicy parameter affect how you can retrieve them. There are three constants in RetentionPolicy enum:

RetentionPolicy.SOURCE – makes the annotation to be discarded by the compiler but annotation processors can read them

RetentionPolicy.CLASS – indicates that the annotation is added to the class file(.class) but not accessible through reflection

RetentionPolicy.RUNTIME –Annotations are recorded in the class file by the compiler and retained by the JVM at runtime so that they can be read reflectively

Here's an example code to create an annotation that can be read at runtime:
```
@Retention(RetentionPolicy.RUNTIME)
public @interface Description {
    String value();
}
```
Now, annotations can be retrieved through reflection:
```
Description description
  = AnnotatedClass.class.getAnnotation(Description.class);
System.out.println(description.value());
```
An annotation processor can work with RetentionPolicy.SOURCE

Q10. Will the Following Code Compile?
```
@Target({ ElementType.FIELD, ElementType.TYPE, ElementType.FIELD })
public @interface TestAnnotation {
    int[] value() default {};
}
```
No. It's a compile-time error if the same enum constant appears more than once in an @Target annotation.

Removing the duplicate constant will make the code to compile successfully:
```
@Target({ ElementType.FIELD, ElementType.TYPE})
```

Q11. Is It Possible to Extend Annotations?
No. Annotations always extend java.lang.annotation.Annotation, as stated in the Java Language Specification.

If we try to use the extends clause in an annotation declaration, we'll get a compilation error:

Q12. Can one class be provided with two annotation
Yes.

### Class class and Reflection
Class class is used to describe the meta information inside a class. When a class is loaded from ClassLoader, one(and only one per classloader) Class object will be created.

Every class or object can call getClass() method or .class field to get the instance of the Class class.


Reflection is an API which is used to examine or modify the behavior of methods, classes, interfaces at runtime. Reflection gives us information about the class. This is a class manipulatior.

Combine with annotations, using reflection api can achieve lots of framework jobs. 


### Generics
Generics mean parameterized types. The idea is to allow type to be a parameter to methods, classes, and interfaces. Using Generics, it is possible to create classes that work with different data types. 

Q2. How Generics works in Java ? What is type erasure ?
Generics is implemented using Type erasure, the compiler erases all type related information during compile time and no type related information is available during runtime. for example List<String> is represented by only List at runtime. 

Q3. What Are Some Advantages of Using Generic Types?
One advantage of using generics is avoiding casts and provide type safety(compile type check), because we change the runtime exception to be a checked exception.
 
the other advantage is to avoid code duplication. Without generics, we have to copy and paste the same code but for different types. 

Q9. What Is a Wildcard Type?
A wildcard type represents an unknown type.

### Exception
Larger scope exception should put in the later place.
 
Custom unchecked exception extends RuntimeException.(RuntimeException is subclass of Exception) 

Custom checked exception extends exception. 
 
All excepiton are serializable, This is because the root class for all exceptions, Throwable implements the Serializable interface. All exceptions by default are serializable and that's a language design decision because the authors wanted ***exceptions to be capable of being sent across the wire without any special configuration***.
 
### mkdir()
mkdir() method is a part of File class. The mkdir() function is used to create a new directory denoted by the abstract pathname. 
 
### lambda 
contain parameter and method body, and can return any type.
 
### Method reference
Method reference is used refer method of functional interface. It is nothing but compact way of lambda expression. You can simply replace lambda expression with method reference.
```
Syntax:
class::methodname
 
object::methodname
```
 
### Imperative programming vs Declarative programming
Imperative Programming: In this, programs specify how it is to be done. 
Declarative Programming: In this, programs specify what is to be done. 

### Functional interface (means it represent functionality)
have single abstract method. 
 
It is not madatory but recommended to use @FunctionalInterface annotation to avoid the addition of extra methods accidentally.
 
consumer: consume a value and return a void
 
Supplier: supply a value
 
Function: map a value to different value
 
predicate: test a condition
 
### Stream API
Stream is a declarative programming (instructor) approach to iterate, use to process collection of objects. Most of the methods are defined on Java .util.stream

To perform a computation, stream operations are composed into a stream pipeline. A stream pipeline consists of a source (which might be an array, a collection, a generator function, an I/O channel, etc), zero or more intermediate operations (which transform a stream into another stream, such as filter(Predicate)), and a terminal operation (which produces a result or side-effect, such as count() or forEach(Consumer)). Streams are lazy; computation on the source data is only performed when the terminal operation is initiated, and source elements are consumed only as needed.

#### What is the parallel Stream? How can you get a parallel stream from a List? (answer) 
A parallel stream can parallel execute stream processing tasks. For example, if you have a parallel stream of 1 million orders and you are looking for orders worth more than 1 million, then you can use a filter to do that.

Unlike sequential Stream, the parallel Stream can launch multiple threads to search for those orders on the different parts of the Stream and then combine the result.

#### What is the difference between intermediate and terminal operations on Stream? (answer)
The intermediate Stream operation returns another Stream, intermediate stream have to combined with terminal operation. 
1. Map
2. Filter
3. Sorted
 
On the other hand, the terminal operation produces a result.

Once a terminal method like forEach() or collect() is called, you cannot call any other method of Stream or reuse the Stream.
 
#### What do you mean by saying Stream is lazy? (answer)
we mean that most of the methods are defined on Java .util.stream.Stream class is lazy i.e. they will not work by just including them on the Stream pipeline.

They only work when you call a terminal method on the Stream and finish as soon as they find the data they are looking for rather than scanning through the whole set of data.
 
### Optional
Use optional to avoid NullPointerException. By using optional, we can specify alternate values to return. That way we can know if the container object may or may not contain non-null value.
```
Optional<object> optional1 = Optional.empty()
if(optional1.isPresent()){
   sout("it is empty")
 }
```
### S.O.L.I.D. Principles
Single responsibility principle: 
A class should only have a single responsibility, that is, only changes to one part of the software's specification should be able to affect the specification of the class.

Open–closed principle"
"Software entities ... should be open for extension, but closed for modification."

Liskov substitution principle:
"Objects in a program should be replaceable with instances of their subtypes without altering the correctness of that program." See also design by contract.

Interface segregation principle:
"Many client-specific interfaces are better than one general-purpose interface."

Dependency inversion principle:
One should "depend upon abstractions, [not] concretions."

### JVM monitor 
Java Mission Control is the recommended one by Oracle. 

### Other Java
.class filename is not compulsory to be the same as .java
 ```
 /*
 multiple comment 
 */
 ```
 
tenary operation --->used with return OR assignment 

JavaP:The javap tool is used to get the information of any class or interface. The javap command (also known as the Java Disassembler) covert bytecode to java code only with structure

POJO class: no extends, no implement, no annotations.
 
s.cancat(s2) = s1+s2
 
s1.toUpperCase()
 
TDD ---> Test drive developmen
 
### A singleton class means only one object can be created from the class.
 
### Factory is a creational design pattern, i.e., related to object creation.

Factory pattern hides the creation process of objects from being exposed to the caller. Caller of Factory doesn't know how the object gets created. This will make the code loosely coupled.
 
### Builder pattern is used to simplify the process of building a complex object.
#### Differences between factory and builder
Factory is to hide the creation of the object from the client. Client doesn't know how the objects are created. Just ask for it and use it.

Builder is to simplify the creation of the obejct if there are too many attributes to set. Client knows exactly what to set.

 ### Q1:Process Vs Thread
A process is the execution of a program.

Thread is part of a process. A process can have multiple threads, all executing at the same time. 

The typical difference is that threads (of the same process) share memory space whileas processes are mostly isolated, they have their own memory space.

#### Q2: What is a thread pool?
A thread pool manages the pool of worker threads, it contains a BlockingQueue that keeps tasks waiting to get executed.
 
### BlockingQueue: 
 a java Queue that support operations that wait for the queue to become non-empty when removing an element. Doesn’t accept null vales. Thread-safe.
### PriorityBlockingQueue 
 one alternative implementation if the thread-safe implementation is needed.
 
#### types :
1.	single thread pool
2.	Fixed thread pool(: A thread pool with a fixed number of threads. 
3.	Cached THread pool (A thread pool that creates as many threads it needs to execute the task in parrallel. )
4.	Scheduled Thread Pool : A thread pool made to schedule future task. 
5.	Single Thread Scheduled Pool : A thread pool with only one thread to schedule future task. 

#### How to define it in the internally
They are many thread and a BlockingQueue in the thread pool, the thread pool have all the Tasks. When the threads are idle, it will pick up the tasks from the blocking queue

#### Why do we use thread pool, does it make the performance better
A thread pool increase performance by reducing the number of threads needed and managing their lifecycle. Essentially, threads are kept in the thread pool until they're needed, after which they execute the task and return the pool to be reused later.

#### How to create space internally thread pool 内部如何开辟空间, what the disadvantages.
Create Executor Pool using ExecutorService and pass a set of tasks to it. Executor will automatically adjust the pool size according to the bounds set by Core Pool size. By using the executor, need to implement the Runnable objects and send them to the executor to execute.

#### Memory leekage.
A Memory Leak is a situation when there are objects present in the heap that are no longer used, but the garbage collector is unable to remove them from memory and, thus they are unnecessarily maintained.

#### Q3: During a thread's lifetime, what states can it have?
 New(haven't call start()), Runnable(it is executing in JVM), waiting(wait for notify()), time_waiting(wait for specific time)/Blocked(wait for monitor lock) and Terminated.

#### Q4: What is a race condition? (definition + explanation + solution)
A race condition occurs when multiple concurrent threads race to be the first to run. If the winner was not the one that was supposed to run first, the code may exhibit unexpected behavior. The problem can be resolved with synchronization.

#### Q5: What is synchronization?
Synchronization forces threads to run one at a time to prevent a race condition or multiple threads trying to perform the same task.

#### Q6: synchronized block?
only a single thread will be allowed to run the code block until it completes.

A lock machanism to make code to be executed just in one thread at the same time.

#### Q7. What is context switching
Context switching is where the current state of a thread or process is stored so the execution of that thread can be resumed at a later time. This enables a single CPU to manage multiple threads or processes.

#### Q8: what the thread scheduler is and its relationship to thread priority?
The thread scheduler is what allocates CPU time to threads and determines the order in which threads execute.

#### Q9: What is time slicing?
Time slicing is the process used by the thread scheduler to divide CPU time between the available active threads.

#### Q10: Why might you describe thread behavior as unpredictable? (Reason + elaborate + aftermath)
Because thread scheduling is determined by the CPU, different CPUs may give priority to different threads. This means there is a chance two CPUs will not run your threads in the same order, creating unpredictability in your code execution.

#### Q11：Explain the busy spin technique and why you might use it.
usy spin is where you pause a thread by making it run an empty loop for a certain period. Unlike other methods like wait() or sleep(), a busy spin doesn't give up CPU control and therefore preserves CPU cache.

#### Q12. busy spin technique and why you might use it.
Busy spin is where you pause a thread by making it run an empty loop for a certain period. Unlike other methods like wait() or sleep(), a busy spin doesn't give up CPU control and therefore preserves CPU cache.

#### Q13. thread starvation
Threads are blocked indefinately waiting to enter a synchronized bloc. Thread starvation is when there is insufficient CPU capacity to execute a thread. This can happen with low-priority threads, or threads that are demoted in favor of other threads.

#### Q14: Can you start a thread twice?
nce a thread has been executed, it is considered dead. You cannot restart a dead thread.

#### Q15: Can you describe a deadlock situation?
A deadlock situation is where multiple threads are waiting on each other to release CPU resources so they can run.

#### Q16: What happens when a livelock occurs?
A livelock is similar to a deadlock situation, except with a livelock, the state of the threads change without ever making progress. For example, if all the threads are caught in infinite loops.

#### Q17: the difference between the wait() and sleep()
The wait() method pauses a thread and waits until there are notify() or notifyAll() method calls from other threads. The sleep() method pauses for a given period, allowing other threads to run, after which it resumes execution.

#### Q18: daemon thread
A daemon thread is a low-priority thread. It may provide background services or support to the other threads, e.g. GC

#### Q19: Why must you override the run() method in your thread class?
If we don't overridden the run() method, the thread will not do anything.

#### Q20:  How might you achieve thread safety?
You can achieve thread safety through several techniques, including synchronization, using the Volatile keyword or using atomic wrapper classes.

#### Q21: What is the difference between synchronous and asynchronous programming?
Synchronous programming is when a single thread is assigned a single task. Asynchronous programming is when a single task is shared between multiple threads.

### Atomic 
use case of volatile: flags(boolean)
atomicInteger: counter
AtomicInteger: caches
 
compound operator means combined assignment operat

Atomic operations are performed in a single unit of task without interference from other operations. '

AtomicInteger

### java.lang.ThreadLocal class provides thread-local variables where each thread accesses its own, independent copy of the variable.

### How to create a thread
runnable interface, extends Thread, Thread pool, callable(pros, can throw exceptions, can return generics)

### runnable 
cons: 
1. return void
2. it can not catch exception

### program vs process vs thread
| program | process |
|---------| ---------|
|static code| excution of program |
|hard drive| OS will assign memory for each process |
|classloader load it to JVM so it will become process| |

### message queue implement comsumer and producer
Synchronized keyword mark the following block to be atomic, 

private static Object monitor_lock = new Object(); to be the lock

Synchronized method works same as sychronized(lock)

lock is a object monitor 

main memory / thread memory

 yield() provides a mechanism to inform the “scheduler” that the current thread is willing to relinquish its current use of processor but it'd like to be scheduled back soon as possible.

The “scheduler” is free to adhere or ignore this information and in fact, has varying behavior depending upon the operating system.


### AtomicInteger
problem with volatile: override the other result, use synchronized(reduce the performance), we could use atomicInteger instead, 

The primary use of AtomicInteger is when you are in a multithreaded context and you need to perform thread safe operations on an integer without using synchronized. Java classes like AtomicInteger or AtomicBoolean internally use CAS operations to support multi-threading.

1. step one: In the RAM, instantiate an AtomicInteger with value equals to five.
2. Step two: copy the value of the AtomicInteger from Ram to both the threads.
3. Step three: compare and swap then write back to the RAM

#### CAS
In a CAS operation, the processor provides a separate instruction that can update the value of a register only if the provided value is equal to the current value.

CAS operation can be used as an alternate to synchronization.

Let say thread T1 can update a value by passing its current value and the new value to be updated to the CAS operation.

In case another thread T2 has updated the current value of previous thread, the previous thread T1's current value is not equal to the current value of T2.

Hence the update operation fails.

In this case, thread T1 will read the current value again and try to update it.

This is an example of optimistic locking.

### ABA problem
The AtomicStampedReference is designed to solve the A-B-A problem. The A-B-A problem is when a reference is changed from pointing to A, then to B and then back to A.

When using compare-and-swap operations to change a reference atomically, and making sure that only one thread can change the reference from an old reference to a new, detecting the A-B-A situation is impossible.

use atomicStamp to check the verison.

CAS concept: compare and swap

concurrent parkage

### What are the types of I / O streams?
ByteStream(8 bits) and CharacterStream(16 bits).

We can simplify the stream code with try with resources.
 
### When to use Character Stream over Byte Stream? 
characters are stored using Unicode conventions. Character stream is useful when we want to process text files. These text files can be processed character by character. A character size is typically 16 bits.

#### When to use Byte Stream over Character Stream? 
A byte stream is suitable for processing raw data like binary files.

#### The IO is really expensive to use so how can we reduce the number of interaction between software and hardware
load all of them ot memory at one time, use buffer

#### flush()
Flushes the output stream and forces any buffered output bytes to be written out.

#### IO and serialization
Serialization uses ObjectInputStream/ObjectOutputStream

#### transfer API 
TransferTo() belong to InputStream

