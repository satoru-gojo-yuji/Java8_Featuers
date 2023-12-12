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
``````


