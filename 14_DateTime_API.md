-> In last session we discussed about Stream api.

-> Stream api is used to process the data.
-----------------------------------------------------------------------------------
Today's session : Date api changes in java 1.8 version
----------------------------------------------------------------------------------

-> In java we have java.util.Date class to work with date related functionality in our application.

		Date date  = new Date();

-> When we create object for Date class it will give both date and time (current date & time).

-> If we want to get only date without time or only time without date then we have to write our own logic using Date class object.

-> To overcome this problem, in java 1.8 v changes happend for Date API.

-> In Java 1.8v new classes provided to work with date related functionality

		java.time.LocalDate (It will deal with only date)
		java.time.LocalTime (It will deal with only time)
		java.time.LocalDateTime (It will deal with both date & time)

-> The above classes got introduced in java.time package.
-----------------------------------------------------------------------------------
public class Demo1 {

	public static void main(String[] args) {

		// Getting Current Date
		LocalDate now = LocalDate.now();
		System.out.println(now);

		// Getting specific date using of method
		LocalDate date = LocalDate.of(2020, 05, 20);
		System.out.println(date);

		date = LocalDate.of(2021, Month.MAY, 20);
		System.out.println(date);

		// Converting String to Date using Parse
		date = LocalDate.parse("2015-02-26");
		System.out.println(date);

		// Adding 4 days to given date
		date = date.plusDays(4);
		System.out.println(date);

		// Adding 4 months to given date
		date = date.plusMonths(4);
		System.out.println(date);

		// Check date is before given date
		boolean isBefore = LocalDate.parse("2020-03-12").isBefore(LocalDate.parse("2018-06-14"));
		System.out.println(isBefore);
		
		// Check date is after given date
		boolean isAfter = LocalDate.parse("2020-03-12").isAfter(LocalDate.parse("2018-06-14"));
		System.out.println(isAfter);
	}
}
-----------------------------------------------------------------------------------
public class Demo2 {

	public static void main(String[] args) {
		// Getting current Time
		LocalTime time = LocalTime.now();
		System.out.println(time);

		// Getting Specific Time using of method
		time = LocalTime.of(11, 20, 03);
		System.out.println(time);

		// Convert String value to Date using parse method
		time = LocalTime.parse("08:30:20");
		System.out.println(time);
		
		//Adding 4 seconds to given time
		time = time.plusSeconds(4);
		System.out.println(time);
		
		//Adding minutes to given time
		time = time.plusMinutes(10);
		System.out.println(time);
		
		//Adding hour to given time
		time = time.plusHours(2);
		System.out.println(time);
	}
}
----------------------------------------------------------------------------------
public class Demo3 {

	public static void main(String[] args) {
		LocalDateTime ldt = LocalDateTime.now();
		System.out.println(ldt);
	}
}
-----------------------------------------------------------------------------------	
public class Demo4 {

	public static void main(String[] args) {
		ZoneId of = ZoneId.of("America/Marigot");
		System.out.println("Zone ID :: " + of);

		// Fetching all zone ids
		/*
		 * Set<String> availableZoneIds = ZoneId.getAvailableZoneIds(); for (String
		 * zoneId : availableZoneIds) { System.out.println(zoneId); }
		 */

		ZonedDateTime now = ZonedDateTime.now();
		System.out.println(now);

		System.out.println("Year ::" + now.getYear());
		System.out.println("Month :: " + now.getMonthValue());
		System.out.println("Day :: " + now.getDayOfMonth());
	}
}
---------------------------------------------------------------------------------
public class Demo5 {

	public static void main(String[] args) {
		Period period = Period.ofDays(5);
		System.out.println(period.getDays());

		period = Period.ofMonths(3);
		System.out.println(period.getMonths());

		period = Period.ofYears(2);
		System.out.println(period.getYears());

		// Find Difference between 2 dates
		Period p = Period.between(LocalDate.parse("1991-05-20"), LocalDate.now());
		System.out.println(p);
	}
}
-----------------------------------------------------------------------------------
public class Demo6 {

	public static void main(String[] args) {
		Duration between = Duration.between(LocalTime.parse("12:14"), LocalTime.parse("13:15"));
		System.out.println(between);
	}
}
-----------------------------------------------------------------------------------
-> Period class is used to check difference between 2 dates

-> Duration class is used to check difference between 2 times.
-----------------------------------------------------------------------------------













