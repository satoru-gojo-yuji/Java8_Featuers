Lambda Expression
Stream API
Default methods in the interface
Predicate
Functional Interface
Optional
Method references
Date API
Nashorn, JavaScript Engine

Main advantages of using Java 8?
More compact code
Less boiler plate code
More readable and reusable code
More testable code
Parallel operations

Q) What are predicates? 
Predicate is a predefined Functional Interface (Having only 1 abstract method).
The only abstract method of predicate is test(T t):
public boolean test(T t);
Whenever we want to check some boolean condition then you can go for Predicates. 

Q) How to use Predicates? 
Say if you need to test if the length of the given string is greater than or equal to 5. Then in such situations where you need to test conditions, use test() method of predicate.

Q) Type parameter and return types of Predicates?
Input to predicate can be anything like 
Hence only 1 type argument is required which is input type in predicate.
Return type is not required as its always Boolean only.

Q) Advantages of Predicates?
Code Reusability

If you have same conditions being used 100 times in a prgram then you can write once and just use 100 times with checkLength.test(different string to be tested).

Conditional checks are holded by Functional interfaces.

Q) What is Predicate joining?
You can combine predicates in serial predicate

Three ways to join :
And
Or
Negate

Eg if you want to test 2 conditions:
To check length of string 
To check if length is even.

Q) What are Functions
Function is also a predefined Functional Interface (Having only 1 abstract method).

The only abstract method of Function is   apply(T t);

 R apply(T t);

Given some input perform some operation on input and then produce / return result (not necessary a boolean value).

This takes 1 input and returns one output. 
In predicate we used to take 1 input and return type is always boolean. 
In function return type is not fixed hence we declare both input type and return type.

Q) What is Functional chaining

We can combine / chain multiple functions together with andThen .

There are two ways to combine functions:
 f1.andThen(f2).apply(Input);  - first f1 then f2
f1.compose(f2).apply(Input)  - first f2 then f1


Multiple functions can be chained together like :
f1.andThen(f2).andThen(f3).andThen(f4).apply(Inputs);


Consumer :  It will consume Item. Consumers never return anything (never supply), they just consume.

Consumer Chaining :
We can combine / chain multiple consumers together with andThen .

There is only one ways to combine consumers:
 c1.andThen(c2).apply(Input);  - first c1 then c2

No compose() in consumer.

Multiple consumers can be chained together like :
c1.andThen(c2).andThen(c3).andThen(c4).apply(Inputs);

Supplier :
It will just supply required objects and will not take any input
Its always going to supply never consume / take any input.

EG : always supply me current date.
No chaining as no input is given to this. Only it gives u output.


Advantages:
Write once, use anywhere.

Code Reusability

BiCinsumer Bisupplier :
 What if we need 2 arguments for operation?

Then we need Bi XYZ Functional Interfaces.


There is no input in supplier so no 1 or 2 Input arguments needed. Hence no BiSupplier.

Q) If we want to operate on 3 arguments then triPredicate? 

There are no TriPredicate or TriFunction etc.

No QuadPredicate No QuadFunction.

Java 8 has inbuilt Functional interfaces that can take only 1 or 2 arguments no more.

*********************************************************************************************

Stream :
If we want to process bulk objects of collection then go for streams concept.
Way to operate on collection in java 8 is Stream.
Its a special iterator class that allows processing collections of objects in a functional manner.

Eg : fetch all objects from collection of list whose value is greater than 15

Why streams were introduced in java 8 if we already had java.io.stream?

Java io streams is a sequence of characters or binary data which is used to be written to a file or to read data from a file.
While streams java 1.8 is no where related to files, its related to collection object.
Java io streams related to file whereas java 8 streams are related to collection object.
Hence if we need to perform some operations on collection there we should go for streams.

To represent group of collection as single entity then we should use collection concept.

If we want to perform operation on bulk objects in collection then we should go for Streams.

We can get stream object by :

Stream s = collectionObject.stream();
Once we get stream object we can process the object of collection.
Processing of stream consists of 2 steps/ stages
Configuration of stream
Processing that configuration
Configuration can be done by 
Map 
Filter

Stream s = collectionObject.stream().filter(i 🡪 i % 2 ==0);

What if we don’t want to filter out.
We rather want to create new object against each existing stream object based on some function.

EG in given stream create new object by squaring  its value

If we want to fetch / filter objects from collection like eg : filter only even numbers from array list collection the use Filter for configuration of stream.

 If we want to perform some operation on each objects of the collection then create another mapped object with different value(after operation is performed ) for each object of that collection, then use map.

In filter, because of filtering, number of objects in filtered list is less than original list While in Map  same number of objects are there in both new and original list created.


Collect - 
If we want to collect elements of stream after filtering or mapping and add them to the required collection then use collect method.

Count - 
If we want to count how many elements are there in collection that satisfy given condition then use collect method.

sorted - 
If we want to sort elements inside a stream use this sorted() method.
We can sort based on default natural sorting order 
If we want to sort using customized sorting order then use comparator.

Comparator 
If we want to sort using customized sorting order then use comparator.

Min Max-
Min(Comparator)  will return the minimum value based on the defined comparator
Max(Comparator)  will return the maximum value based on the defined comparator

Foreach
forEach() is a method . 
All methods that we saw till now returned something, like min max value, sorted collection, etc
This method does not return anything. 
Rather This method takes lambda expression as argument and apply that lambda expression to each element present in that stream.

toArray- 

of() - 
Stream concept is not applicable just for the collections it’s also applicable for “ANY GROUP OF VALUE”.
Even for arrays you can use stream.
Stream . Of() this method can take any group of values and convert them to stream so that multiple stream operations can be applied to it.

Parallel Stream

Java Parallel Streams came into picture after java 1.8.

Its meant to utilize multiple cores of processor.

Till Now our java code has 1 stream of processing where it executes sequentially.

But when you use parallel streams, we divide code into multiple streams that executes parallely , on separate cores and final result is the outcome of individual cores outcomes combined.

Sequential VS Parallel Streams.