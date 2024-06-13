## When we have Collection inside another collection then to flaten that stream we will use flatMap( ) method.
``````java
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
``````````
https://javaconceptoftheday.com/differences-between-java-8-map-and-flatmap/

Diff Map and Flat map 
