
## Comparator Interface

**Using comparator interface- Comparator interface is used to order the objects of a user-defined class. This interface is present in java.util package and contains 2 methods compare(Object obj1, Object obj2) and equals(Object element). Using a comparator, we can sort the elements based on data members. For instance, it may be on roll no, name, age, or anything else.**

### Method use in the Comparator Interface 
 - public int compare(Object obj1, Object obj2):

 **Comparator is a predifind interface available in java which is use to implement Custamize sorting.**

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

      // Using Lambda 
// Ascending 
      Collection.sor(r , (01 , 02)-> 01-02) // Negative hai to swipe nahi krenge 
      
      // Descending 
      // positive hai to swipe 
       Collection.sor(r , (01 , 02)-> 02-01)

       }
   }
```````

### Compareto Method 
``````java
class Student {
 
    // Attributes of a student
    int rollno;
    String name, address;
 
    // Constructor
    public Student(int rollno, String name, String address)
    {
 
        // This keyword refers to current instance itself
        this.rollno = rollno;
        this.name = name;
        this.address = address;
    }
 
    // Method of Student class
    // To print student details in main()
    public String toString()
    {
 
        // Returning attributes of Student
        return this.rollno + " " + this.name + " "
            + this.address;
    }
}
 
// Class 2
// Helper class implementing Comparator interface
class Sortbyroll implements Comparator<Student> {
 
    // Method
    // Sorting in ascending order of roll number
    public int compare(Student a, Student b)
    {
 
        return a.rollno - b.rollno;
    }
}
 
// Class 3
// Helper class implementing Comparator interface
class Sortbyname implements Comparator<Student> {
 
    // Method
    // Sorting in ascending order of name
    public int compare(Student a, Student b)
    {
 
        return a.name.compareTo(b.name);
    }
}
 
// Class 4
// Main class
class GFG {
 
    // Main driver method
    public static void main(String[] args)
    {
 
        // Creating an empty ArrayList of Student type
        ArrayList<Student> ar = new ArrayList<Student>();
 
        // Adding entries in above List
        // using add() method
        ar.add(new Student(111, "Mayank", "london"));
        ar.add(new Student(131, "Anshul", "nyc"));
        ar.add(new Student(121, "Solanki", "jaipur"));
        ar.add(new Student(101, "Aggarwal", "Hongkong"));
 
        // Display message on console for better readability
        System.out.println("Unsorted");
 
        // Iterating over entries to print them
        for (int i = 0; i < ar.size(); i++)
            System.out.println(ar.get(i));
 
        // Sorting student entries by roll number
        Collections.sort(ar, new Sortbyroll());


        //Using Lambda 

        Collection.sort(ar , (a , b) -> a.name.compareTo(b.name));

         Collection.sort(ar , (a , b) -> a.rollno - b.rollno);


 
        // Display message on console for better readability
        System.out.println("\nSorted by rollno");
 
        // Again iterating over entries to print them
        for (int i = 0; i < ar.size(); i++)
            System.out.println(ar.get(i));
 
        // Sorting student entries by name
        Collections.sort(ar, new Sortbyname());
 
        // Display message on console for better readability
        System.out.println("\nSorted by name");
 
        // // Again iterating over entries to print them
        for (int i = 0; i < ar.size(); i++)
            System.out.println(ar.get(i));
    }
}
Output
Unsorted
111 Mayank london
131 Anshul nyc
121 Solanki jaipur
101 Aggarwal Hongkong

Sorted by rollno
101 Aggarwal Hongkong
111 Mayank london
121 Solanki jaipur
131 Anshul nyc

Sorted by name
101 Aggarwal Hongkong
131 Anshul nyc
111 Mayank london
121 Solanki jaipur
```````

##  Comparable Interface 
The Comparable interface contains the method compareTo to decide the order of the elements.


``````
class Pair implements Comparable<Pair> {
    String x;
    int y;
 
    public Pair(String x, int y)
    {
        this.x = x;
        this.y = y;
    }
 
    public String toString()
    {
        return "(" + x + "," + y + ")";
    }
 
    @Override public int compareTo(Pair a)
    {
        // if the string are not equal
        if (this.x.compareTo(a.x) != 0) {
            return this.x.compareTo(a.x);
        }
        else {
            // we compare int values
            // if the strings are equal
            return this.y - a.y;
        }
    }
}
 
public class GFG {
    public static void main(String[] args)
    {
 
        int n = 4;
        Pair arr[] = new Pair[n];
 
        arr[0] = new Pair("abc", 3);
        arr[1] = new Pair("a", 4);
        arr[2] = new Pair("bc", 5);
        arr[3] = new Pair("a", 2);
 
        // Sorting the array
        Arrays.sort(arr);
 
        // printing the
        // Pair array
        print(arr);
    }
 
    public static void print(Pair[] arr)
    {
        for (int i = 0; i < arr.length; i++) {
            System.out.println(arr[i]);
        }
    }
}
Output:

Before Sorting:
(abc, 3);
(a, 4);
(bc, 5);
(a, 2);

After Sorting:
(a,2)
(a,4)
(abc,3)
(bc,5)

``````

### Differecne B/W Comparator and Comparable 

|Comparator | Comparable |
|----------|------------|
| Compare() method we are using | CompareTo() method we are using |
|In Comparator we are using more then one sotring | In Comparable we are using only one shorting|