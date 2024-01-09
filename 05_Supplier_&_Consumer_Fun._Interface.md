## Supplier
- Supplier is an interface that does not take any arguments but it produce the value when the get() function called.
- Supplier are useful when our lambda is not taking any input but it is providing some output.
- It is predifined functional interface.
- It contains only one abstract method i.e get().

``````java
EX: 

 public static void main(String[] args)
    {
        Supplier<Date> dt = () -> new Date();
        System.out.println(dt.get());

    }

EX: 2

 public static void main(String[] args)
    {
        Supplier<String> r =() -> {
            String otp =" ";
            for(int i=1 ; i<=6 ; i++)
            {
                otp = otp +(int) (Math.random()*10);
            }
            return  otp;
        };
        System.out.println(r.get());
    }

## Consumer
- It is a predifined functional interface
- It contain only one abstract method accept()
- Consumer take input but it will not returen anything.
- Consumer can be used in a scenario where our lambda should take input and perform operation based on the input but no need to return nothing.


```````java
EX:
 public static void main(String[] args)
    {
        Consumer<String> s =(name) -> System.out.println("Hello");
        s.accept("Abhi");

        Consumer<Integer> s1 =(name1) -> System.out.println(name1*name1);
        s1.accept(20);
    }

### Biconsumer 
 - If you want to supply two inputs for lambda then we use Biconsumer.
 - BiConsumer take two input but it will not returen anything.

 ``````java
 public static void main(String[] args)
    {
        BiConsumer<Integer, Integer> r1 = (i , r ) -> {
            System.out.println("Hello");
            System.out.println("HI");

    };
        r1.accept(19,20);
    }
