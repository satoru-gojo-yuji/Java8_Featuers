Today's session : Java-8 Interview Questions
-------------------------------------------------------------------------------------------------------------

1) What are the new features added in Java 8 ?

Ans

Lambda Expressions
Functional Interfaces
Method References
Default Methods
Static Methods
Stream API
Date Time API
Optional
StringJoiner
SplIterator

2) From Java 8 onwards java is OOP language or Functional Programming Language?

Ans

Java supports both Object Oriented Features & Functional Programming Features

3) What are the advantages of Java-8?

Ans

More Readable & Concise code
Less Boiler Plate Code
Parallel Processing
Functional Programming


4) What is MetaSpace ?

Ans

-> Earlier in JVM we have PermGen space to store .class files. Now in java 8 version they removed PermGen space and provided MetaSpace to store .class files.

-> Heap space is used to store the objects

-> MetaSpace is used to store the classes

-> PermGen space is fixed where as MetaSpace can be resized dynamically.

5) What is SAM in java 8?

Ans

-> SAM stands for Single Abstract Method Interface

-> SAM interfaces are also called as Functional Interfaces

-> The interface which contains only one abstract method is called as Functional Interface.

-> We will use @FunctionalInterface to represent our interface as Functional Interface.

6) Can FunctionalInterface extend/Inherit another Interface?

Ans

A functional interface can extend another interface if it doesn't contain abstract method. Becuase it voilates Functional Interface rules.

7) What is Default method in interface?

Ans

-> The method which contains body with default keyword in interface is called as Deafult method.

-> Default methods introduced in java 1.8 version.

-> Default methods introduced to provide backward compatibility

-> We can override default methods in interfaces


8) What is statik method in interface?

Ans

-> The method which contains body with static keyword is called as static method.

-> Static methods introduced in java 1.8 version

-> Static methods we can't overriden

9) What are pre-defined Functional Interfaces available in java?

Ans

Runnable
Callable
Comparator
Comparable

Predicate
Supplier
Consumer
Function

10) What is Lambda Expression?

Ans

-> Lambda expression is an anonymous function without name, modifier and return type

-> Lambda Expressions are used to write functional programming

-> Functional Interfaces are used to invoke lambda expressions

11) Write Lambda expression to print "Hello World" ?

Ans

	( ) -> System.out.println("Hello World");



12) What is Method Reference?

Ans

-> Method Reference is used to refer a method of Functional Interface

-> It is used to refer a method without invoking it

-> Method References are alternative for Lambda expressions


	list.forEach(name -> System.out.println(name));  // with lambda

	list.forEach(System.out::println); //method reference

13) What is Optional Class in java?

Ans

-> Optional class is a container which may or may not contain value

-> Optional class is part of java.util package

-> It contains isPresent() method to check object available in container or not


14) What is Strem API?

Ans

-> Stream API introduced in java 1.8 version

-> Stream represents sequence of character/objects

-> Stream interface available in java.util.stream package

-> Stream is used only for processing the data

15) What are the main Components of a Stream?

Ans

Source (It can be a collection/Array)
Map (Function)
Filter (Predicate)
Sorted  (Comparator)

16) What are intermediate & terminal operations in Stream?

Ans

-> Intermediate operations will return Stream 

		Ex: filter ( ) , map ( ) 

-> Terminal operations will return result

		Ex: count ( )


17) What are the differences between Collections & Streams?

Ans

-> Collections are used to store the data

-> Stream is used to process the data

18) What are the changes for Date Time in Java 8?

Ans

-> java.util.Date( ) will represent both Date & Time in single object

-> Java 8 introduced below new classes

		LocalDate  (deals with only date)
		LocalTime  (deals with only time)
		LocalDateTime (deals with date & time)




























































































