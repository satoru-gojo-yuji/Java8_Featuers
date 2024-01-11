## Function  & BiFunction


``````java
public ticket book(Passenger pass){
    // Logic
    returen ticketobj;
    }

EX 
  interface Functiona<T, R>
  {
    R.apply(T t);
  }
   > T represent input/parameter object type.
   > R represent returning object type/output.


 EX:
  public static void main(String[] args)
    {
        Function<String , String> t = (r) -> r.toUpperCase();
        System.out.println(t.apply("Agdfrvf"));
    }  
``````
- As we can see the above book() method taking passenger obj as input and returning ticket obj as output.
- To work this kind of requirement we can use Function interface.
- function inter contains only one abstract method apply().
- Function take only one input and return output

Note: In realtime most of our requirements will match with functinal interface only because our methods will take input will operation and then return result. 

### BiFunction 

- BiFunction take two input and return output 

```````java
public static void main(String[] args) {


      BiFunction<Integer, Integer, Integer> r = (i, n) -> (i * n);
      System.out.println(r.apply(3,4));
  }
```````````

EX: Taking loginform object as a input and returning String as output 
 
 public string Login(Loginform input)
 {
    // check login credentials with db
    return status ; 
 }


 | Predicate | Supplier | Cunsummer | Function |
 |-----------|----------|-----------|------------|
 |It takes single input| It will not take input| It takes single input|It takes single input|
 | It return boolean value| It return object(T)| It will not return anything| It return object(R)|
 | Boolean test()| T get()| void accept(input)| R apply(T t)|
 |For two input we have Bipredicate| No concept of Bisupplier|For two input we have BiConsumer|For two input we have BiFunction|


