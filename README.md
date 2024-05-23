# Array-Lists
```java
import java.util.ArrayList;
import java.util.stream.Collectors;
import java.util.Scanner;

public class Main {
    //shopsItems here
    public static void main(String[] args) {
        var shopsItems = new ArrayList<String>(); // same but another option is "ArrayList<String> shopsItems = new ArrayList<String>();"
        //Initializes an ArrayList, creates a new object (ArrayList) and gives a reference
       // opening scanner for user input
        var scanner = new Scanner(System.in);

        while(true){ // opening while loop et saaks mitu korda user inputi, aga peab loopi breakima, sest see lõpmatu loop muidu, seega tuleb if exit panna.
            var item = scanner.nextLine(); // here asking input
        // kui loopist väljuda, siis user kirjutab exit ja siis ta prindib kõik itemsid välja
            if(item.equals("exit")){
                break;
            }
            addItem(shopsItems, item); // selle saab lisada siis, kui on "ArrayList<String> shopsItems = new ArrayList<String>();" method lisatud, lisab itemi store
        }

        printArrayList(shopsItems); // see prindib kõik itemid üksteise alla välja

    // removing an element
        System.out.println("Enter the item you want to remove from the list:");
        var itemToRemove = scanner.nextLine(); // Asks the user for input
        shopsItems.removeIf(item -> item.equals(itemToRemove));

        printArrayList(shopsItems); // prindime uuesti listi välja

// kui tahad filtreerida välja specific asjad. nt filtreerime listist välja asjad, mis on pikemad kui 5 characters
        var filteredArrayList = new ArrayList<String>();
        for (String item: shopsItems){
            if(item.length() <= 5){
                filteredArrayList.add(item);

            }
        }
        printArrayList(filteredArrayList);
    }
     // going through elements
    public static void printArrayList(ArrayList<String> items){
        for (String item : items){ // : means going through each element, can be any other word instead of item(s). aga on items sest rida ülevamalpol kutsusime itemsiks.
            System.out.println(item);
        }
    }
// adding an item to the store
    ArrayList<String> shopsItems = new ArrayList<String>();
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
