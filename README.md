Writing Our Own List Class

We are designing a class in Java that uses the generic structure to store data.

The purpose of the class is to hold a dynamic array and dynamically determine the data type. Therefore, it is necessary to create a generic class.

NOTE: THE COLLECTION CLASS WILL NOT BE USED! WE SHOULD CREATE OUR OWN LIST CLASS.

Class properties:

The default size of the array inside the class should be 10, and the number of elements in the array should double as needed.

The class should have two types of constructor methods:

MyList(): If the empty constructor is used, the initial size of the array should be 10.

MyList(int capacity): The initial value of the array should be taken from the capacity parameter.

size(): Returns the number of elements in the array.

getCapacity(): Returns the capacity value of the array.

add(T data): Used to add an element to the array of the class. If there is not enough space in the array, the size of the array should be doubled.


Example 

public class Ata { public static void main(String[] args) { MyList<Integer> liste = new MyList<>(); System.out.println("The size of list : " + liste.size()); System.out.println("Array's list Capacity : " + liste.getCapacity()); liste.add(10); liste.add(20); liste.add(30); liste.add(40); System.out.println("Number of Elements in Array: " + liste.size()); System.out.println("Array Capacity : " + liste.getCapacity()); liste.add(50); liste.add(60); liste.add(70); liste.add(80); liste.add(90); liste.add(100); liste.add(110); System.out.println("Number of Elements in Array : " + liste.size()); System.out.println("Array Capacity: " + liste.getCapacity());     }
}

Output
Array Capacity: 10 Number of Elements in the Array: 0
Array Capacity: 10
Number of Elements in the Array: 4
Array Capacity: 20
Number of Elements in the Array: 11


//Mission

get(int index): Returns the value at the given index. If an invalid index is provided, it returns null.

remove(int index): Deletes the data at the given index and shifts the remaining data to the left. If an invalid index is provided, it returns null.

set(int index, T data): Replaces the data at the given index with the new data. If an invalid index is provided, it returns null.

String toString(): A method that lists the elements in the array belonging to the class.



Örnek


public class Ata { public static void main(String[] args) { MyList<Integer> liste = new MyList<>(); liste.add(10); liste.add(20); liste.add(30); System.out.println("2.value in index: " + liste.get(2)); liste.remove(2); liste.add(40); liste.set(0, 100); System.out.println("2. value in index : " + liste.get(2));         System.out.println(liste.toString());
    }
}

Output



2. value index : 30 2. value index : 40
[100,20,40]

//


int indexOf(T data): Returns the index of the given object in the list. If the object is not in the list, it returns -1.

int lastIndexOf(T data): Returns the last index of the specified element in the list. If the object is not in the list, it returns -1.

boolean isEmpty(): Indicates whether the list is empty or not.

T[] toArray(): Converts the elements in the list into an array in the same order.

clear(): Deletes all the elements in the list, making it an empty list.

MyList<T> sublist(int start, int finish): Returns a list containing the elements within the specified index range provided as parameters.

boolean contains(T data): Checks if the given value exists in the list and returns true if it does, false otherwise.




Example 

public class Ata {
    public static void main(String[] args) {
        MyList<Integer> list = new MyList<>();
        System.out.println("List Status: " + (list.isEmpty() ? "Empty" : "Full"));
        list.add(10);
        list.add(20);
        list.add(30);
        list.add(40);
        list.add(20);
        list.add(50);
        list.add(60);
        list.add(70);

        System.out.println("List Status: " + (list.isEmpty() ? "Empty" : "Full"));

        // Returns the first index it finds
        System.out.println("Index: " + list.indexOf(20));

        // Returns -1 if not found
        System.out.println("Index: " + list.indexOf(100));

        // Returns the last index it finds
        System.out.println("Index: " + list.lastIndexOf(20));

        // Returns the list as an Object[] array
        Object[] array = list.toArray();
        System.out.println("First element of the Object array: " + array[0]);

        // Creates a sublist of the list with the same data type
        MyList<Integer> subList = list.sublist(0, 3);
        System.out.println(subList.toString());

        // Checks if a value exists in the list
        System.out.println("Value 20 in my list: " + list.contains(20));
        System.out.println("Value 120 in my list: " + list.contains(120));

        // Clears the list completely and resets it to its default size
        list.clear();
        System.out.println(list.toString());
    }
}



Output 

List Status: Empty
List Status: Full
Index: 1
Index: -1
Index: 4
First element of the Object array: 10
[10, 20, 30, 40]
Value 20 in my list: true
Value 120 in my list: false
[]
