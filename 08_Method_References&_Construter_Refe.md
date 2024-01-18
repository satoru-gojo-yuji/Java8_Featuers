## Method Reference & Construter Reference 

- **Method references as a name suggest this is used to refer form one method to another method**.
- **Method references are similler to object refrences**. 

EX : Consumer is a functional interface which will take input and will perform operation on that input but it will not return anything. consumer contain accept() method.


``````java
Consumer<String> c = (s) -> sout("Hello");
s.accept("hi");
```````




