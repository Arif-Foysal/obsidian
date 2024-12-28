#Java 

>[!Contents]
>- [[vector in c++]]

The `ArrayList` class is a resizable [array](https://www.w3schools.com/java/java_arrays.asp), which can be found in the `java.util` package.
# Creating an Arraylist
```java
import java.util.ArrayList; // import the ArrayList class

ArrayList<String> cars = new ArrayList<String>(); // Create an ArrayList object
```

# Adding Itemso

## Appending last

```java
import java.util.ArrayList;

public class Main {
  public static void main(String[] args) {
    ArrayList<String> cars = new ArrayList<String>();
    cars.add("Volvo");
    cars.add("BMW");
    cars.add("Ford");
    cars.add("Mazda");
    System.out.println(cars);
  }
}
```

## Adding in n index
```java
import java.util.ArrayList;
public class Main {
  public static void main(String[] args) {
    ArrayList<String> cars = new ArrayList<String>();  
	cars.add("Volvo");  
	cars.add("BMW");  
	cars.add("Audi");  
	cars.add("Ferrari");  
	cars.add("Nissan");

	cars.add(1,"Yamaha");//adding in index 1
	System.out.println(cars);
	
  }
}
```

### Shortcut: Adding in front of the Array List
```java
import java.util.ArrayList;
public class Main {
  public static void main(String[] args) {
    ArrayList<String> cars = new ArrayList<String>();  
	cars.add("Volvo");  
	cars.add("BMW");  
	cars.add("Audi");  
	cars.add("Ferrari");  
	cars.add("Nissan");

	cars.addFirst("Yamaha");//adding in front
	System.out.println(cars);
  }
}
```




# Access an Item

```java
cars.get(0);
```

# Modifying an item

```java
cars.set(0, "Opel");
```

# Removing an item

```java
cars.remove(0);
```

To remove all the items from an `Arraylist`, use the `clear()` method:
```java
cars.clear();
```

## ArrayList Size

To find out how many elements an ArrayList have, use the `size` method:
```java
cars.size();
```

# Looping through an ArrayList
Loop through the elements of an `ArrayList` with a `for` loop, and use the `size()` method to specify how many times the loop should run:
```java
public class Main {
  public static void main(String[] args) {
    ArrayList<String> cars = new ArrayList<String>();
    cars.add("Volvo");
    cars.add("BMW");
    cars.add("Ford");
    cars.add("Mazda");
    for (int i = 0; i < cars.size(); i++) {
      System.out.println(cars.get(i));
    }
  }
}
```

You can also loop through an `ArrayList` with the **for-each** loop:
- [ ] Link to java for each loop
```java
public class Main {
  public static void main(String[] args) {
    ArrayList<String> cars = new ArrayList<String>();
    cars.add("Volvo");
    cars.add("BMW");
    cars.add("Ford");
    cars.add("Mazda");
    for (String i : cars) {
      System.out.println(i);
    }
  }
}
```

## Sort an ArrayList

Another useful class in the `java.util` package is the `Collections` class, which include the `sort()`method for sorting lists alphabetically or numerically:
```java
import java.util.ArrayList;
import java.util.Collections;  // Import the Collections class

public class Main {
  public static void main(String[] args) {
    ArrayList<String> cars = new ArrayList<String>();
    cars.add("Volvo");
    cars.add("BMW");
    cars.add("Ford");
    cars.add("Mazda");
    Collections.sort(cars);  // Sort cars
    for (String i : cars) {
      System.out.println(i);
    }
  }
}
```

Sort an ArrayList of Integers:
```java
import java.util.ArrayList;
import java.util.Collections;  // Import the Collections class

public class Main {
  public static void main(String[] args) {
    ArrayList<Integer> myNumbers = new ArrayList<Integer>();
    myNumbers.add(33);
    myNumbers.add(15);
    myNumbers.add(20);
    myNumbers.add(34);
    myNumbers.add(8);
    myNumbers.add(12);

    Collections.sort(myNumbers);  // Sort myNumbers

    for (int i : myNumbers) {
      System.out.println(i);
    }
  }
}
```

