In Last Session We discussed about below operations in Streams


1) Slicing Operations ( distinct() , limit ()  & skip () )

2) Matching Operation ( anyMatch(), allMatch() & noneMatch() )

3) Finding Operations ( findFirst (), findAny () )

4) Collectors Operations ( toList( ), toSet( ) & toMap ( ) )
---------------------------------------------------------------------------------------------
Today's session : Stream API Methods
---------------------------------------------------------------------------------------------

1) getting Min salary emp from collection

2) getting Max salary emp from Collection

3) Getting Avg Salary of the employee

4) Group By



````````java

-----------------------------------------------------------------------------------------------
public class Employee {

	String name;
	int age;
	int salary;

	public Employee(String name, int age, int salary) {
		this.name = name;
		this.age = age;
		this.salary = salary;
	}

	//setters & getters
	//toString() method
}
-----------------------------------------------------------------------------------------------
public class EmpMinMaxAvgDemo {

	public static void main(String[] args) {
		List<Employee> list = new ArrayList<>();
		list.add(new Employee("Ram", 23, 20000));
		list.add(new Employee("Ashok", 25, 60000));
		list.add(new Employee("Suresh", 33, 25000));
		list.add(new Employee("Charan", 26, 40000));

		Double avgSalary = list.stream().collect(Collectors.averagingInt(emp -> emp.getSalary()));
		System.out.println("Emp Avg Salary :: " + avgSalary);

		Optional<Employee> minEmpSalary = list.stream()
				.collect(Collectors.minBy(Comparator.comparing(Employee::getSalary)));
		System.out.println("Minimum Salary Emp:: " + minEmpSalary.get());

		Optional<Employee> maxEmpSalary = list.stream()
				.collect(Collectors.maxBy(Comparator.comparing(Employee::getSalary)));
		System.out.println("Maximum Salary Emp:: " + maxEmpSalary.get());

	}
}
----------------------------------------------------------------------------------------------
`````````
`````````java
public class User {

	String name;
	int salary;
	String country;

	public User(String name, int salary, String country) {
		this.name = name;
		this.salary = salary;
		this.country = country;
	}

	//setters & getters

}
-------------------------------------------------------------------------------------------------------
public class GroupByDemo {

	public static void main(String[] args) {

		List<User> users = new ArrayList<>();

		users.add(new User("Ram", 10000, "India"));
		users.add(new User("Anil", 20000, "Canada"));
		users.add(new User("Sunil", 30000, "India"));
		users.add(new User("Orlen", 40000, "Japan"));
		users.add(new User("Cathie", 50000, "UK"));
		users.add(new User("Ching Chong", 10000, "China"));
		
		Map<String, List<User>> collect = 
						users.stream().collect(Collectors.groupingBy(User::getCountry));
		System.out.println(collect);
	}
}
```````````

---------------------------------------------------------------------------------------------------------------
Parallel Streams
---------------------------------------------------------------------------------------------------------------
-> Streams is one of the major change added in java 1.8 version

-> Generally Streams will execute in Sequential manner

-> We can use parallel streams also to execute program faster by utilizing system resources efficiently.

-> Parallel Streams introduced to improve performance of the program.


---------------------------------------------------------------------------------------------------------------
```````java
public class ParallelStreamDemo {

	public static void main(String[] args) {

		System.out.println("************* Serial Stream **************************");
		Stream<Integer> stream1 = Stream.of(1, 2, 3, 4, 5, 6, 7, 8, 9, 10);
		stream1.forEach(num -> System.out.println(num + " :: " + Thread.currentThread().getName()));

		System.out.println("********** Parallel Stream ****************");
		Stream<Integer> stream2 = Stream.of(1, 2, 3, 4, 5, 6, 7, 8, 9, 10);
		stream2.parallel().forEach(num -> System.out.println(num + " :: " + Thread.currentThread().getName()));
	}
}
--------------------------------------------------------------------------------------------------------------

```````````


















