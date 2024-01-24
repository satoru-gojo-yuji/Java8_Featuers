-> In last session we discussed about below concepts

i) What is Stream API?

ii) What are the advantages of using Stream API

iii) Characterstics of Stream API

iv) What type of operations we can perform using Stream API
		- Intermediate Operations
		- Terminal Operations

v) Stream Creation
		i) of( ) method
		ii) stream ( ) method		

vi) Filter operation using Streams ==> filter(Predicate p)

vii) Mapping operation using Streams ==> map(Function f)



----------------use case for filtering data---------------------------------------

public class Mobiles{
 
     public List<Mobiles> getMobiles(MobileFilter mf){

        List<Mobiles> Mobiles = dao.getMobiles();

	Stream stream = mobiles.stream();

	if(!"".equals(mf.getBrand)){
	    stream = stream.filter(m -> m.getBrand().equals(mf.getBrand());
	}

	if(!"".equals(mf.getRam(){
	    stream  = stream.filter(m -> m.getRam().equals(mf.getRam());
        }

	return stream.collect(Collectors.toList());
     }
}

---------------------------------------------------------------------------------

public class NamesLength {

	public static void main(String[] args) {
		List<String> list = new ArrayList<>();

		list.add("Anushka");
		list.add("Trisha");
		list.add("Nayanatara");
		list.add("Deepika Padukone");
		list.add("Pooja Hegde");
		list.add("Anupama Parameswaran");
		list.add("Amisha Patel");

		Stream<String> stream = list.stream();

		//Stream<String> tfStream = stream.map(name -> name.toUpperCase() + "::" + name.length());
		IntStream tfStream = stream.mapToInt(name -> name.length());
		tfStream.forEach(System.out::println);

	}
}
---------------------------------------------------------------------------------
public class FilteringMappingDemo {

	public static void main(String[] args) {
		List<String> list = new ArrayList<>();

		list.add("Anushka");
		list.add("Trisha");
		list.add("Nayanatara");
		list.add("Deepika Padukone");
		list.add("Pooja Hegde");
		list.add("Anupama Parameswaran");
		list.add("Amisha Patel");

		Stream<String> stream = list.stream();
		
		//print heroine name with length whose name is starting with A
		stream.filter(name -> name.startsWith("A"))
			  .map(name -> name +"::"+name.length())
			  .forEach(System.out::println);

    // Intstream t =stream.mapToInt(name-> name.length() );
        t.forEach(System.out::printIn);
	}
}
--------------------------------------------------------------------------------
public class Person {

	private String name;
	private String job;
	private Long phno;

	public Person(String name, String job, Long phno) {
		this.name = name;
		this.job = job;
		this.phno = phno;
	}

	//setters & getters

}
----------------------------------------------------------------------------------
public class MarriagePortal {

	public static void main(String[] args) {
		Person p1 = new Person("Raju", "Software", 6301921083l);
		Person p2 = new Person("Gopi", "Chef", 789767899l);
		Person p3 = new Person("Mahesh", "PhotoGrapher", 668621083l);
		Person p4 = new Person("Sunil", "Driver", 47575721083l);
		Person p5 = new Person("David", "Teacher", 5678921083l);
		Person p6 = new Person("Ashok", "Software", 630192178l);
		
		//Give me person name with number who is doing Software job
		
		List<Person> persons = Arrays.asList(p1, p2, p3, p4, p5, p6);
		
		persons.stream()
			   .filter(person -> person.getJob().equals("Software"))
			   .map(person -> person.getName()+"::"+person.getPhno())
			   .forEach(System.out::println);
	}
}

----------------------------------------------------------------------------------------------------------
-> When we have Collection inside another collection then to flaten that stream we will use flatMap( ) method.
----------------------------------------------------------------------------------------------------------
public class FlatMapDemo {

	public static void main(String[] args) {

		List<String> javacourses = Arrays.asList("Core Java", "Adv Java", "SBMS", "JRTP");

		List<String> uicourses = Arrays.asList("HTML5", "CSS3", "Angular", "React JS");

		List<String> cloudcourses = Arrays.asList("DevOps", "AWS", "Azure", "GCP");
		
		List<List<String>> ashokitcourses = Arrays.asList(javacourses, uicourses, cloudcourses);
		
		Stream<List<String>> stream1 = ashokitcourses.stream();
		
		Stream<String> courses = stream1.flatMap(s -> s.stream());
		
		courses.forEach(System.out::println);
		
	}
}
	
---------------------------------------------------------------------------------------------------------------
