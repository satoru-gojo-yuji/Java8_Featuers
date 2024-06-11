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










