## Predefine Functional Interfaces are.
- Pradicate
- Function
- Consumer
- Supplier

**The above functional interfaces are provided in java.util.function package.**


### Predicate 

- Predicate is a predefind functional interface.
- It is used to perform some conditional check and returen true or false.
- Predicate having the **test()** method which is used to invok the lambda expression.
- If we have a lambda which check reterun ture or false then we can invoke that lambda usign predicate functional interface.

**Ex.  Check weather given no. greater then 20 or not.**

``````java
// Logic without Lambda 

public boolean test(int number)
{
    if ( number > 20)
    {
        return ture ; 
    }else 
    {
         return false ; 
    }
}

// With lambda 
(number) -> number > 20 ;

// With Predicate 
Predicate<Integer> predicate = (number) -> number > 20 ; 
sout(predicate.test(29));
```````

EX: 2

``````java
public class PredicateDemo2 {

    public static void  main(String args[])
    {

        String[] names = {"Kajal", "Abhisek", "Nantara", "Tanishka"};

        Predicate<String> tr = (name) -> name.startsWith("A");

        for(String namew : names)
        {
            if(tr.test(namew))
            {
                System.out.println(namew);
            }
        }
    }
}


EX 3

public class PPerson {

    String name ;
    int age ;

    PPerson(String name , int age)
    {
        this.age = age;
        this.name = name ;
    }

    public String getName()
    {
        return  name;
    }

    public void setName(String name)
    {
        this.name = name;
    }

    public Integer getage()
    {
        return  age ;
    }

    public  void setAge(int age)
    {
        this.age = age ;
    }

    @Override
    public String toString() {
        return  "name"+name+ "age" +age+  " ";
    }
}

public class PPmain {

    public static void main(String args[])
    {
        PPerson p1 = new PPerson("Raja", 5) ;
        PPerson p2 = new PPerson("Ra", 18) ;
        PPerson p3 = new PPerson("ja", 20) ;
        PPerson p4 = new PPerson("aja", 56) ;
        PPerson p5 = new PPerson("aaja", 58) ;


       List<PPerson>  t = Arrays.asList(p1,p2,p3,p4,p5);    // Convert object into arrylist

        Predicate<PPerson> persona = (P) -> P.getage() >= 18 ;

        for(PPerson p : t)
        {
             boolean s = persona.test(p);
             if(s)
                 System.out.println(p.getName());
        }


    }
}
```````

### Pedicate Joining 

- To combine multiple predicate we will use Predicate Joining.
- We have below methods in Predicate
     1 test() = it is a abstract method
     2 negate() = if you want to perform revers operation then we can use negate
     3 or() = If you want to satisfied only one condition then we can use or 
     4 and() = If you want to satisfied both condition then we can use and 

Only test method is abstract remaing all are default methods 

*Requirement : Write a program to identify who is eligible for marriage 

Condition  :  Person age should be >=20 and <=64  


```````java
public class PPmain {

    public static void main(String args[])
    {
        PPerson p1 = new PPerson("Raja", 22) ;
        PPerson p2 = new PPerson("Ra", 18) ;
        PPerson p3 = new PPerson("ja", 20) ;
        PPerson p4 = new PPerson("aja", 56) ;
        PPerson p5 = new PPerson("aaja", 58) ;


       List<PPerson>  t = Arrays.asList(p1,p2,p3,p4,p5);    // Convert object into arrylist

        Predicate<PPerson> persona1 = (P) -> P.getage() >= 21 ;
         Predicate<PPerson> persona2 = (P) -> P.getage() <>= 64 ;

        for(PPerson p : t)
        {
            Predicate<PPerson> persona3 = persona1.and(persona2);
             boolean s = persona.test(p);
             if(s)
                 System.out.println(p.getName());
        }


    }
}

EX : Find the even no..
public class Evenno {

    public static void main(String[] args)
    {
        Predicate<Integer> r = p-> p % 2 == 0 ;
        System.out.println(r.test(54));

    }
     Predicate<Integer> e =i-> i % 2 == 0 ;
         boolean status = isEven(e,10);
        System.out.println(status);


    }


    public static boolean isEven(Predicate<Integer> p , Integer i)
    {
        return p.test(i);
    }

     public static boolean isEven(Predicate<Integer> p , Integer i)
    {
        return p.negate().test(i);
    }
}
```````
###  BiPredicate 

- If you want to supply two parameters as input for lambda and return the result then we can use Bipredicate for this. 
- BiPredicate is functiona interface which contains a abstract method test().
- BiPredicate takes two parameters and returns boolean value.


``````java
 public static void main(String[] args)
    {
        BiPredicate<Integer, Integer> t =(i , y) -> i+y >= 100 ;
        System.out.println(t.test(50 ,60));
    }









