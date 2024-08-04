## Method Reference & Construter Reference 

- **Method references as a name suggest this is used to refer form one method to another method**.
- **Method references are similler to object refrences**. 

EX:  Consumer is a functional interface which will take input and will perform operation on that input but it will not return anything. consumer contain accept() method.


``````java

Consumer<String> c = (s) -> sout("Hello");
s.accept("hi");


// The above code can be written like below using static method reference 

Consumer<String> c = (s) -> System.out::println;
s.accept("hi");

```````````

**EX : Function is a funtional interface which will take the input and which return output. Function contain apply(). 

``````java
Function<Person , Integer > r = p -> p.getage();
Integer t = r.apply(perobj);

-----------------------------------------
// The above code can be written like below using instance method reference

Function<Person , Integer > r = p -> p::getage();
Integer t = r.apply(perobj);

````````

```````java
- Method reference example 

class Test
{

    public static void m2()
    {
        sout("this is m2 method");
    }

    public static void main(String[] args)
    {
       // without method reference 
  //Myinterface r =()-> sout(" hello m1 method");
    Myinterface m1 = Test::m2;
  m1.m1();
    }
}
interface Myinterface
{
    public void m1();
}
````````
- By using mehtod reference we can use re use existing logic instread of writting lambda.

- Method references are alternative of lambda.

```````java 

public class sample 
 {
   main method 
    
  SampleInterface si = ()->new Sample();
   SampleInterface si = Sample::new;
   sout(si.hashcode());
 }

 interface SampleInterface
 {
  smple get();
 }
 
```````
https://javaconceptoftheday.com/java-8-method-references/

Lambda Expressions
A lambda expression is an anonymous function that can be used to create an instance of a functional interface (an interface with a single abstract method). Lambda expressions are used for defining a method without giving it a name, which can then be passed around as if it were an object and executed later.

Syntax:
java
Copy code
(parameters) -> expression
or

java
Copy code
(parameters) -> { statements; }
Example:
java
Copy code
// Functional interface
interface MyFunctionalInterface {
    void myMethod();
}

// Using lambda expression
MyFunctionalInterface lambda = () -> System.out.println("Hello, World!");
lambda.myMethod(); // Output: Hello, World!
Method References
A method reference is a shorthand notation of a lambda expression to call a method. It can be used to refer to methods or constructors without executing them. Method references are more concise and can improve readability.

Types of Method References:
Static Method Reference: ClassName::staticMethodName
Instance Method Reference of a Particular Object: instance::instanceMethodName
Instance Method Reference of an Arbitrary Object of a Particular Type: ClassName::instanceMethodName
Constructor Reference: ClassName::new
Example:
java
Copy code
// Using static method reference
MyFunctionalInterface methodRef = System.out::println;
methodRef.myMethod("Hello, World!"); // Output: Hello, World!
Comparison
Readability and Conciseness:

Lambda Expressions: More flexible but can be verbose for simple method calls.
Method References: More concise and readable when referring to existing methods.
Use Cases:

Lambda Expressions: Useful when you need to provide complex logic directly within the expression.
Method References: Ideal for referring to already defined methods without adding extra logic.
Syntax:

Lambda Expressions: Require parameter lists and body definitions.
Method References: Use :: notation to directly reference methods or constructors.
Example Comparison
Lambda Expression:

java
Copy code
List<String> list = Arrays.asList("a", "b", "c");
list.forEach(s -> System.out.println(s));
Method Reference:

java
Copy code
List<String> list = Arrays.asList("a", "b", "c");
list.forEach(System.out::println);
In this example, both versions achieve the same result, but the method reference is more concise and easier to read.

In summary, use lambda expressions when you need to write custom logic or when a method reference is not applicable. Use method references when you are simply referring to an existing method, as they are more concise and improve code readability.










