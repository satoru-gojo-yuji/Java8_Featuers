## Steam API 

- The addition of the stream api was one of the major freature added to java 8.
- Stream API is used to process the data.

Note : Stream api is not for stroing the data. It is meant for only processing the data. 

Note : In java, we will use the collection to store the data. we will use Steam to process the data.

IMP points for Stream:
- A stream is not a data structure.
- Stream is used to perform bunch of operations on the data.
- Stream will take the data from a collection or array.
- Stream will perform opetation on the data but it will not change the original data struture. 

Stream Creation
= 

Stream can be created from different element sources.
- Using of() method we can create strem.
- Using stram() method also we can create steam.

Approach 1 

   Stream<Integer> s = Steam.of(1,2,3,4);

Approach 2

```````java
list<String> s = new Arraylist<>();

list.add("anusa");
list.add("anuiu");
list.add("anuty");
list.add("anusg");
list.add("anu");
list.add("anurt");

Stream<String> s = s.stream();

`````````

By using stream we can perform below operations on the data
- Intermediate operation
- Terminal operation 

Intermediate ope. methods will not produce any results. they usally accept functional interface as parameters and always returns new stream. some examples for intermediate ope. are filter() and map() methods.

Terminal ope. method will produce some results 
count() , collect() etc.

Stream with filtering 

- Stream interface  having filter() methods.
- filter() method will take predicate as input

-Predicate is a function interface which will take input and returns boolean value
- Predicate interface contains test() as abstract method. this method is used to execute lambda.
```````java
public class Demo {

    public static void main(String[] args)
    {
        Stream<Integer> a = Stream.of(4,5,6,7,8,83) ;
        a.forEach(System.out::println);

        // using lambda
        a.forEach(i -> sout(i)); 
    }

}



public class Person {

	private String name;
	private Integer age;
	private String job;

	public Person(String name, Integer age, String job) {
		this.name = name;
		this.age = age;
		this.job = job;
	}

	//setters, getters & toString()
-----------------------------------------------------------------------------------
package in.ashokit.beans;

import java.util.Arrays;
import java.util.List;

public class PersonsFilters {

	public static void main(String[] args) {
		Person p1 = new Person("Raju", 28, "Software");
		Person p2 = new Person("Mahesh", 29, "Driver");
		Person p3 = new Person("Ashok", 30, "Teacher");
		Person p4 = new Person("Sunil", 27, "Mechanic");
		Person p5 = new Person("Bharat", 30, "Chef");

		List<Person> persons = Arrays.asList(p1, p2, p3, p4, p5);
		
					persons.stream()
					       .filter(p -> p.getAge() > 21 && p.getAge() < 30 && p.getJob().equals("Software"))
  						   .forEach(System.out::println);
	}
}
``````````

Mapping Operations In Streams
----------------------------------------------------------------------------------
-> Mapping operations are belongs to Intermediate operations

-> Mapping operations are those operations that transform the elements of a stream and return a new stream with transformed elements.

----------------------------------------------------------------------------------
public class NamesMapping {

	public static void main(String[] args) {
		List<String> list = new ArrayList<>();

		list.add("Anushka");
		list.add("TriSha");
		list.add("Nayanatara");
		list.add("Deepika Padukone");
		list.add("Pooja Hegde");
		list.add("Anupama Parameswaran");
		list.add("Amisha Patel");

		Stream<String> stream = list.stream();

		stream.map(name -> name.toUpperCase()).forEach(System.out::println);

	}
}

 


   



