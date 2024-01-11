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


