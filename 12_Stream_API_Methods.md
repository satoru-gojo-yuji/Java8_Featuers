Today's session : Stream API methods with Examples
---------------------------------------------------------------------------------------------

Slicing Operations In Streams
------------------------------

-> **distinct ( )** -> it is used to get unique elements from the Stream

-> **limit (long maxSize) ->** it is used to get number of elements from the stream based on given size

-> **skip (long n) ->** it is used to skip elements from starting to given length and returns remaining elements.


**Intermideater operation and return type is strea**



``````java
public class FilteringMappingDemo {

	public static void main(String[] args) {
		List<String> list = new ArrayList<>();

		list.add("India");
		list.add("China");
        list.add("USA");
        list.add("UK");
        list.add("China");
        list.add("India");
		

        list.stream().distinct().forEach(System.out::println);
// out put India , China , USA , UK  

    list.stream().limit(3).forEach(r -> System.out.println(r));
//output 
//  India
// China
// USA

   list.stream().skip(3).forEach(System.out::println);
  //  output 
//   UK
// China
// India
```````
 


Note:  The above 3 methods are intermediate methods only. They perform operation and returns new stream.


Matching Operations in the streams
----------------------------------
=> Matching operations are terminal operations that are used to check if elements with certain are present in the stream or not.

=> There are mainley three matching functions available in the Stream. these are

	anyMatch ( )
	allMatch( )
	noneMatch( )


```````java

package Java_8_Features.Stream.StreamAPImethods;


import java.util.Arrays;
import java.util.List;




    class Persons {

        private String name;
        private Integer age;
        private String job;

        public Persons(String name, Integer age, String job) {
            this.name = name;
            this.age = age;
            this.job = job;
        }

        public String getname()
        {
            return name;
        }
        public void setname(String y)
        {
            this.name=y ;
        }

        public Integer getAge()
        {
            return age;
        }

        public void setAge(Integer age) {
            this.age = age;
        }
        public String getJob()
        {
            return job;
        }

        @Override
        public String toString() {
            return  "name= "+name+" , age="+age+" job="+job+" ";
        }



    }

    //setters, getters & toString()



    public class Terminalope {

        public static void main(String[] args) {

            
            Persons p1 = new Persons("Raju", 28, "Software");
            Persons p2 = new Persons("Mahesh", 29, "Driver");
            Persons p3 = new Persons("Ashok", 30, "Teacher");
            Persons p4 = new Persons("Sunil", 27, "Mechanic");
            Persons p5 = new Persons("Bharat", 30, "Chef");

            List<Persons> persons = Arrays.asList(p1, p2, p3, p4, p5);

       /*  boolean f=   persons.stream().anyMatch(P-> P.getname().equals("Ashok"));
            System.out.println("   "+f);*/   //true

           /* boolean f=   persons.stream().allMatch(P-> P.getname().equals("Ashok"));
            System.out.println("   "+f);*/  //false 

            boolean f=   persons.stream().noneMatch(P-> P.getname().equals("Ashok"));
            System.out.println("   "+f);  // false


        }
    }

`````````



Finding Operations In Streams
-------------------------------
-> In Matching operations we can check weather data present in the stream or not based on given criteria. After checking the condition it returns true or false value.

-> By using Finding Operations we can check the condition and we can get the data based on condition.

			findFirst()
			findAny( )

 ```````java

  Optional<Persons>  r =  persons.stream().filter(p -> p.getJob().equals("Sfte")).findFirst();

          if(r.isPresent())
            System.out.println("   "+r);



`````````           

Collectors In Streams
----------------------
-> Collectors operations are used to collect the from Streams

-> We are having below methods to perform Collectors operations

			Collectors.toList()
			Collectors.toSet()
			Collectors.toMap()
			Collectors.toCollection() etc..

````````java
package Java_8_Features.Stream.StreamAPImethods;

import java.util.ArrayList;
import java.util.List;

public class Collectors {

    public static void main(String[] args) {
        List<Emp> e = new ArrayList<>();
        e.add(new Emp("Mahesh", 29, "Driver"));
        e.add(new Emp("Ashok", 30, "Teacher"));
        e.add(new Emp("Sunil", 27, "Mechanic"));
        e.add(new Emp("Bharat", 30, "Driver"));

     // List<String>  t =  e.stream().map(Emp::getJob).collect(Collectors.toList());

    }
}

    class Emp {

         String name;
         Integer age;
        String job;

        public Emp(String name, Integer age, String job) {
            this.name = name;
            this.age = age;
            this.job = job;
        }
        public String getname()
        {
            return name;
        }
        public void setname(String y)
        {
            this.name=y ;
        }

        public Integer getAge()
        {
            return age;
        }

        public void setAge(Integer age) {
            this.age = age;
        }
        public String getJob()
        {
            return job;
        }

        @Override
        public String toString() {
            return  "name= "+name+" , age="+age+" job="+job+" ";
        }
    }

```````````


