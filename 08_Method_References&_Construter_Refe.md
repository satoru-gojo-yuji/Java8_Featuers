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









