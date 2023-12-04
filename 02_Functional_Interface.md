## Functional Interface

- **If an interface contain only one abstract method then it is called functional interface.**
- **Functional interface is used to invoke the Lambda Expression (to call the Lambda expression to use funcational interface).**
- **Functional interface can contain default and static methods also.**
- **Functioan interface rule is applicabe only for abstract methods. It should contain only one abstract method and it can contain any no. of defaul and static methods.**

- **To represent our interface as functional interface we will use @FunctionalInterface annotation**

``````java
Ex: 1 (This is valid functional intercase)
@FunctionalInterface
public interface Myinterface{
     public void m2();    // by default abstact will added
}


Ex: 2 (This is invalid because 2 abstract method is there)
@FunctionalInterface
public interface Myinterface{
     public void m2();    // by default abstact will added
     public abstract void m3();
}

Ex: 3 (This is valid functional intercase)
@FunctionalInterface
public interface Parent{
     public void m2();    // by default abstact will added
}
@FunctinalInterface
public interface child extend Parent
{

}

In the abov scenario, child interface doesn't have any abstract methods. child having access for Parent class abstract method hence child is also functional interface.

Ex: 4 (This is valid functional intercase)
@FunctionalInterface
public interface Parent{
     public void m2();    // by default abstact will added
}
@FunctinalInterface
public interface child extend Parent
{
  public void m2();
}

In the above scenario, child interface overriding the parent interface abstract method hence child is having only one abstract method.


Ex: 5 (This is Invalid functional intercase)
@FunctionalInterface
public interface Parent{
     public void m2();    // by default abstact will added
}
@FunctinalInterface
public interface child extend Parent
{
  public void m1();
}
In the above scenario, chid interface having 2 interface hence it is not functional interface

Ex: 6 (This is valid functional interface)
@FunctionalInterface
public interface Parent{
     public void m2();    // by default abstact will added
}

public interface child extend Parent
{
  public void m1();
}
In the above scenario, chid interface can contain any no. of abstract method because it is not having  @FunctionalInterface annotation

Ex: 7 (This is valid functional intercase)

public interface Parent{
     public void m2();    // by default abstact will added
}

- In the above scenario, Parent is functional interface 
- Writing @FunctionalInterface annotation is optional 
- If we writing the @FunctionalInterface, Java compiler will verifying that is valid functional interface or not

``````



## How to invoke Lambda using Functional Interface 


``````Java
// Without using Lambda
public interface myinterface{
  public void m1();
}
class child Myapp implements myinterface{
  public void m1()
  {
    sout("Hello");
  }
  public static void main(String args[])

  myinterface m = new Myapp();
  m.m1
}

// With Lambda Expression
public interface myinterface{
  public void m1();
}
class child Myapp {
 public static void main(String args[])
 {
     myinterface i= ()->sout("Hello");
     i.m1
 }
}
```````
### In Java there are 3 more interfaces is that we called as Functional interface

- Runnable
- callable 
- Actionlistener 


### Runnable interface
contains only one abstract method hence it is called functional interface.

``````java
// Normal program using runnable interface

public class Demo implements Runnable {


    @Override
    public void run() {
        for(int i=0; i<=10 ; i++)
        {
            System.out.println(i);
        }
    }

    public static void main(String args[])
    {
        Demo d =new Demo();
        Thread t = new Thread(d);
        t.start();
    }
}

// Second approach 
public class Demo2 {

    public static void mian(String args)
    {
        new Runnable(){

            @Override
            public void run() {
                System.out.println("Hello");
            }
        };
    }
}

// Thired approach using Lambda expression
public class Demo3 {
    public static void main(String args[])
    {
        Runnable r =()-> System.out.println("hello");
        r.run();
    }
}
``````
### Comparator Interface


``````java 
public class Demo1 {

    public static void main(String args[]) {
        ArrayList r = new ArrayList();
        r.add(23);
        r.add(45);
        r.add(78);
        r.add(89);
        r.add(90);

        Collections.sort(r, new Rem());
        System.out.println(r);
    }
}
   class Rem implements Comparator<Integer>
   {
  
       @Override
       public int compare(Integer o1, Integer o2) {
          if(o1 > o2)   // descending order 
           return -1;
          else if (o1 < o2)
              return 1 ;
          else
              return 0 ;
       }
   }
```````

