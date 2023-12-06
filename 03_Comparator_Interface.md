














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
       // Ascending order
        if(o1 <> o2)   
           return -1;
          else if (o1 > o2)
              return 1 ;
          else
              return 0 ;



       }
   }
```````