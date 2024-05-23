# Array-Lists
```java
import java.util.ArrayList;
import java.util.stream.Collectors;
import java.util.Scanner;

public class Main {
    //shopsItems here
    public static void main(String[] args) {
        var shopsItems = new ArrayList<String>();
        //Initializes an ArrayList, creates a new object and gives a reference
        var scanner = new Scanner(System.in);
        while(true){
            var item = scanner.nextLine();
            if(item.equals("exit")){
                break;
            }
            addItem(shopsItems, item);
        }


        printArrayList(shopsItems);
    }

    public static void printArrayList(ArrayList<String> items){
        for (String item : items){
            System.out.println(item);
        }
    }

    public static void addItem(ArrayList<String> items, String item){
        items.add(item);
        System.out.println(item + " has been added to the store.");
    }
}

//Initialize ArrayList
// Create an element in the arrayList
// Remove an element
// Get the elements
```
```java
import java.util.ArrayList;
import java.util.stream.Collectors;
import java.util.Scanner;

public class Main {
    public static void main(String[] args) {
        var shopsItems = new ArrayList<String>();
        shopsItems.add("Glass table");        
        shopsItems.add("Wooden table");
        shopsItems.add("Round table");
        shopsItems.add("Doors");
        shopsItems.add("Trapdoor");
        shopsItems.add("Couch");
        shopsItems.add("Bed");
        shopsItems.add("Sofa");

        var filteredShopsItems = new ArrayList<String>();
        for(var item: shopsItems){
            if(item.contains("table")){ // otsib üles kõik tooted mis sisaldavad table sõna
                filteredShopsItems.add(item);
            }
        }
        System.out.println(filteredShopsItems);
    }
}
```
```java
// sama nagu eelmine kood

import java.util.ArrayList;
import java.util.stream.Collectors;
import java.util.Scanner;

public class Main {
    public static void main(String[] args) {
        var shopsItems = new ArrayList<String>();
        shopsItems.add("Glass table");        
        shopsItems.add("Wooden table");
        shopsItems.add("Round table");
        shopsItems.add("Trapdoor");
        shopsItems.add("Couch");
        shopsItems.add("Bed");
        shopsItems.add("Sofa");

        var filteredShopsItems = shopsItems
            .stream()
            .filter(item -> item.contains("table"))
            .collect(Collectors.toList());

        System.out.print(filteredShopsItems);
    }
}
```
```java

import java.util.ArrayList;
import java.util.stream.Collectors;
import java.util.Scanner;

public class Main {
    public static void main(String[] args) {
        var shopsItems = new ArrayList<String>();
        shopsItems.add("Glass table");        
        shopsItems.add("Wooden table");
        shopsItems.add("Round table");
        shopsItems.add("Trapdoor");
        shopsItems.add("Couch");
        shopsItems.add("Bed");
        shopsItems.add("Sofa");

// this code do not work, just some examples here:
        var filteredShopsItems = shopsItems
            .stream()
            .skip(3) // esimesed 3 kaovad ära e tabled
            .limit(2) // võtab 2 esimest peale skipi e trapdoor ja couch
            .collect(Collectors.toList())
            .filter(item -> item.toLowerCase().contains("table")) //acts like a search field. If item exits, it will be added to the new list. (we also added the function to make it lower case);
            .forEach(x -> System.out.println("TEST " + x));

        System.out.print(filteredShopsItems);
    }
}
```
```java

```
```java

```
```java
