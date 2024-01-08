## Predefine Functional Interfaces are.
- Pradicate
- Function
- Consumer
- Supplier

**The above functional interfaces are provided in java.util.function package.**


### Predicate 

- It is used to perform some conditional check and returen true or false.
- Predicate having the test() method which is used to invok the lambda expression.

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

// With Pradicate 
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




