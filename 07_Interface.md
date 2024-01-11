## Interface 

- Interface is a contract which contains specification.
- Interface should contian only abstract method ( this is true upto 1.7 version)
- The method which does not contains body is called as abstract method.
 
 EX :  public  void m1(); 

 - From java 8 onwards we can write concrete methods also in interface.
 - The method which contain body is called as concrete methods.

 EX : public Interger sum(Interger a , Interger b)
      return a+b ;

Note : Interface concreate methods should be "defult" or "Static" methods. 


- abstract methods available in the interface are by default public and abstract no need to write public and abstract.

Ex :  void clean() = public abstract clean();

``````java
public interface Vehicle {

    void cleanV();

    public default void roll()
    {
        System.out.println("Hello");
    }


public class Sansore implements Vehicle{


    @Override
    public void cleanV() {
        System.out.println("Sansore");
    }
}
````````

- As per the java rule, when we are implementing interface, we have to implement all the abstract method available in the interface.

### **If we have to overriden methdo then we can go for defult method**

### **If we don't have to overriden then we can go for static method** 
We can not override the static method. 


