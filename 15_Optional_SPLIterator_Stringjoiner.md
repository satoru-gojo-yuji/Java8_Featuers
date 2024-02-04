-> In Last session, we discussed about Date api related changes happend in java 1.8 version.

			LocalDate
			LocalTime
			LocalDateTime
			Period
			Duration
-----------------------------------------------------------------------------------------------
Today's session : Optional , SplIterator and StringJoiner classes
----------------------------------------------------------------------------------------------
-> Java 8 introduced a new class Optional<T> in the java.util package.

-> The Optional is a wrapper class that stores an Object of type T.

-> According to Oracle "Java 8 Optional class works as a Container type for the value which is probably absent or null".

-> Optional class is a final class present in java.util package.

**Every Java Programmer is familiar with NullPointerException. It can crash your code. And it is very hard to avoid it without using too many null checks. So, to overcome this, Java 8 has introduced a new class Optional in java.util package. It can help in writing a neat code without using too many null checks. By using Optional, we can specify alternate values to return or alternate code to run. This makes the code more readable because the facts which were hidden are now visible to the developer.**

-----------------------------------------------------------------------------------------------
public class Employee {

	String name;
	int age;

	//setters & getters & toString()

}
---------------------------------------------------------------------------------------------
public class EmployeeService {

	private Map<Integer, Employee> empMap = new HashMap<>();

	public Employee getEmpById(Integer empId) {
		return empMap.get(empId);
	}
}
---------------------------------------------------------------------------------------------
public class Demo {

	public static void main(String[] args) {
		EmployeeService service = new EmployeeService();

		Employee emp = service.getEmpById(101);

		System.out.println(emp.getName());
	}
}
-----------------------------------------------------------------------------------------------
-> In the above program getEmpById(101) method will return null value and we are calling emp.getName() hence it will throw NullPointerException.


Note: If we perform any operation on null value, it will throw NullPointerException.

----------------------------------------------------------------------------------------------
-> To avoid these kind of NullPointerExceptions Optional class got introduced in Java 1.8 version.

---------------------------------------------------------------------------------------------

	public Optional<Employee> getEmpById(Integer empId){
		Employee emp = empMap.get(empId);
		Optional<Employee> empOptional = Optional.ofNullable(emp);
		return empOptional;
	}	
----------------------------------------------------------------------------------------------
		Optional<Employee> empById = service.getEmpById(101);
		if (empById.isPresent()) {
			Employee emp = empById.get();
			System.out.println(emp.getName());
		} else {
			System.out.println("With Given ID no record found");
		}
----------------------------------------------------------------------------------------------
StringJoiner class available in Java 1.8 version
---------------------------------------------------------------------------------------------
-> StringJoiner class got introduced in java 1.8 version

-> StringJoiner is a final class

-> StringJoiner class present in java.util package

-> StringJoiner class is used to construct sequence of characters seperated by a delimiter.

----------------------------------------------------------------------------------------------
public class StringJoinerDemo {

	public static void main(String[] args) {
		StringJoiner joiner = new StringJoiner(",");

		joiner.add("Ramu");
		joiner.add("Sita");
		joiner.add("Raja");
		joiner.add("Rani");
		
		System.out.println(joiner);
	}
}
-----------------------------------------------------------------------------------------------
-> We can add prefix and Suffix also for StringJoiner like below


public class StringJoinerDemo {

	public static void main(String[] args) {
		StringJoiner joiner = new StringJoiner(",", "{", "}");

		joiner.add("Ramu");
		joiner.add("Sita");
		joiner.add("Raja");
		joiner.add("Rani");

		System.out.println(joiner);
	}
}
---------------------------------------------------------------------------------------------
	StringJoiner joiner = new StringJoiner(delimiter);
	StringJoiner joiner = new StringJoiner(delimiter, prefix, suffix);
-----------------------------------------------------------------------------------------------
SplIterator 
-----------------------------------------------------------------------------------------------

-> SplIterator introduced in java 1.8 version

-> SplIterator can be used for traversing elements of the source.

-> SplIterator mainley used for 

			1) Splitting Source Data
			2) Processing Source Data

-----------------------------------------------------------------------------------------------
public class Demo {

	public static void main(String[] args) {
		
		List<String> cities = Arrays.asList("Hyd", "Banglore", "Pune", "Delhi");

		/*Iterator<String> iterator = cities.iterator();
		while (iterator.hasNext()) {
			System.out.println(iterator.next());
		}*/
		
		//cities.spliterator().forEachRemaining(name -> System.out.println(name));
		
		cities.spliterator().forEachRemaining(System.out::println);
	}
}
----------------------------------------------------------------------------------------------
-> In normal Iterator we have hasNext( ) and next( ) methods to traverse the data.

-> In SplIterator we have forEachRemaining(Consumer c) method to travese the data.
----------------------------------------------------------------------------------------------














