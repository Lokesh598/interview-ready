Link - https://rathod-ajay.medium.com/hsbc-java-interview-experience-with-q-a-for-0-5-years-of-experience-4b519db896a4
    
    Are you preparing for a job interview as a Java developer?

    Find my book Guide To Clear Java Developer Interview here Gumroad (PDFFormat) and Amazon (Kindle eBook).

    Guide To Clear Spring-Boot Microservice Interview here Gumroad (PDFFormat) and Amazon (Kindle eBook).

    Download the sample copy here: Guide To Clear Java Developer Interview[Free Sample Copy]

    Guide To Clear Spring-Boot Microservice Interview[Free Sample Copy]

There is always same pattern followed when accessing the Junior developers in an interview, they always try to ask basic concepts and deeper understanding of it.

This article will have these Topics mainly.

    OOPS & Core Java
    Access modifiers in java
    String
    Serialization
    Collection
    Try Catch
    Hibernate
    spring
    sql
    coding

For every junior oops, String, access modifier and collection are basic topics necessary to know.

    OOPS & Core Java

Tell me about OOPS concept in java/What are the four basic OOPs principle?

The four principles of Object-Oriented Programming (OOP) are:

Encapsulation: This refers to the practice of hiding the internal workings of an object and exposing only the necessary functionality. The data and behaviour of an object are encapsulated within the object, and can only be accessed through well-defined interfaces.

Inheritance: Inheritance allows objects to inherit properties and behaviours from other objects. Inheritance allows for the creation of hierarchical relationships between classes, with parent classes passing down their characteristics to their child classes.

Polymorphism: Polymorphism refers to the ability of objects to take on many forms, and is achieved through the use of inheritance, overloading and overriding methods, and interfaces. Polymorphism allows for greater flexibility and reuse of code.

Abstraction: Abstraction refers to the process of identifying common patterns and extracting essential features of objects, creating classes from these patterns. Abstraction allows for the creation of higher-level concepts that can be used in multiple contexts, and can simplify complex systems.
How do you achieve encapsulation?

Encapsulation is achieved in Java through the use of access modifiers and getter and setter methods.

Access modifiers control the visibility of variables and methods in a class. There are three access modifiers in Java: public, private, and protected.

Public: Public variables and methods can be accessed from anywhere in the program.

Private: Private variables and methods can only be accessed within the same class.

Protected: Protected variables and methods can be accessed within the same class, and by subclasses and classes in the same package.

By default, if you don’t specify an access modifier, the variable or method is considered to have “package” or “default” access, which means it can be accessed within the same package.

Here’s an example of how to use access modifiers to achieve encapsulation:

public class Person {
private String name;
private int age;
public String getName() {
return name;
}
public void setName(String name) {
this.name = name;
}
public int getAge() {
return age;
}
public void setAge(int age) {
if (age < 0) {
throw new IllegalArgumentException("Age cannot be negative");
}
this.age = age;
}
}

In this example, the Person class has two private variables, name and age. These variables are not directly accessible from outside the class, which means that other classes cannot modify or access them directly.

To allow other classes to access these variables, we provide public getter and setter methods for name and age. The getter methods allow other classes to retrieve the values of these variables, while the setter methods allow other classes to modify their values.

Note that we can also add validation logic to the setter methods to ensure that the values being set are valid. In this example, the setAge method throws an exception if the age is negative.

By using access modifiers and getter and setter methods, we can achieve encapsulation in Java. This allows us to protect the data and behavior of our objects and prevent other objects from accessing or modifying them directly, which makes our code more robust and maintainable.
What is abstraction now how it is different from encapsulation?

Abstraction:

· Focus: What the object does, hiding implementation details.

· Goal: Simplifying complex systems by exposing only essential features.

· Mechanisms: Abstract classes, interfaces, functions.

Encapsulation:

· Focus: How the object’s data and behavior are bundled together.

· Goal: Protecting data integrity and controlling access.

· Mechanisms: Access modifiers (public, private, protected), getters and setters.

Key Differences:

· Scope: Abstraction operates at a higher level, focusing on the overall design and interface. Encapsulation works at the object level, managing internal data and implementation.

· Purpose: Abstraction aims to simplify complexity and promote reusability. Encapsulation aims to protect data and manage dependencies.

· Implementation: Abstraction is often achieved through abstract classes or interfaces. Encapsulation is typically implemented using access modifiers and methods to control access to data.
Difference between Abstraction and polymorphism?

Scenario- If you ask someone what is Abstraction, he will tell that it’s an OOP concept which focuses on relevant information by hiding unnecessary detail, and when you ask about Encapsulation, many will tell that it’s another OOP concept which hides data from outside world. The definitions are not wrong as both Abstraction and Encapsulation does hide something, but the key difference is on intent.

Key Points:

Abstraction hides details at the design level, while Encapsulation hides details at the implementation level.

Eg. For example, when you first describe an object, you talk in more abstract term e.g. a Vehicle which can move, you don’t tell how Vehicle will move, whether it will move by using tires or it will fly or it will sell. It just moves. This is called Abstraction. We are talking about a most essential thing, which is moving, rather than focusing on details like moving in plane, sky, or water.

There are also the different levels of Abstraction and it’s good practice that classes should interact with other classes with the same level of abstraction or higher level of abstraction. As you increase the level of Abstraction, things start getting simpler and simpler because you leave out details.

On the other hand, Encapsulation is all about implementation. Its sole purpose is to hide internal working of objects from outside world so that you can change it later without impacting outside clients.

For example, we have a HashMap which allows you to store the object using put() method and retrieve the object using the get() method. How HashMap implements this method (see here) is an internal detail of HashMap, the client only cares that put stores the object and get return it back, they are not concerned whether HashMap is using an array, how it is resolving the collision, whether it is using linked list or binary tree to store object landing on same bucket etc.

1) The most important difference between Abstraction and Encapsulation is that Abstraction solves the problem at design level while Encapsulation solves it implementation level.

2) Abstraction is about hiding unwanted details while giving out most essential details, while Encapsulation means hiding the code and data into a single unit e.g. class or method to protect inner working of an object from outside world. In other words, Abstraction means extracting common details or generalizing things.

3) Abstraction lets you focus on what the object does instead of how it does, while Encapsulation means hiding the internal details of how an object works. When you keep internal working details private, you can change it later with a better method. The Head First Object Oriented Analysis and Design has some excellent examples of these OOP concepts, I suggest you read that book at least once to revisit OOP fundamentals.

4) Abstraction focus on outer lookout e.g. moving of vehicle while Encapsulation focuses on internal working or inner lookout e.g. how exactly the vehicle moves.

5) In Java, Abstraction is supported using interface and abstract class while Encapsulation is supported using access modifiers e.g. public, private and protected.
What is polymorphism?

Polymorphism in Java is a concept by which we can perform a single action in different ways.

Polymorphism defined as “same code” giving “different behaviour”
What is interface in Java?

    It is the blueprint of the class
    Interface in Java can only contains declaration. You can not declare any concrete methods inside interface
    Java interface can extend multiple interface also Java class can implement multiple interfaces, Which means interface can provide more Polymorphism support than abstract class
    but by using interface it can be part of multiple type hierarchies.
    a class can be Runnable and Displayable at same time
    In order to implement interface in Java, until your class is abstract, you need to provide implementation of all methods, which is very painful

What is abstract class?

    A class which is declared with the abstract keyword is known as an abstract class in Java.
    abstract class may contain both abstract and concrete methods, which makes abstract class an ideal place to provide common or default functionality

By extending abstract class, a class can only participate in one Type hierarchy
Abstract class vs Interface in Java?

1) First and the major difference between abstract class and an interface is that an abstract class is a class while the interface is an interface, means by extending the abstract class you can not extend another class because Java does not support multiple inheritances but you can implement multiple inheritance in Java.

2) The second difference between interface and abstract class in Java is that you can not create a non-abstract method in an interface, every method in an interface is by default abstract, but you can create a non-abstract method in abstract class. Even a class which doesn’t contain any abstract method can be made abstract by using the abstract keyword.
3) interface is better suited for Type declaration and abstract class is more suited for code reuse and evolution perspective.
4)abstract class are slightly faster than interface because interface involves a search before calling any overridden method in Java.
5) when you add a new method in existing interface it breaks all its implementation and you need to provide an implementation in all clients which is not good. By using an abstract class you can provide a default implementation for a new method in the superclass without breaking existing clients.
When to use interface and abstract class in Java?
Difference between Abstract Class vs Interface in Java
When to use abstract class and interface in Java or object oriented design is a critical question. In order to make…

javarevisited.blogspot.com

    Access modifiers in java

Different types of access modifiers?

There are four types of access modifiers in Java:

public: The public access modifier is the most permissive access level, and it allows access to a class, method, or variable from any other class, regardless of whether they are in the same package or not.

protected: The protected access modifier allows access to a class, method, or variable from within the same package, as well as from any subclass, even if they are in a different package.

default (no modifier): If no access modifier is specified, then the class, method, or variable has package-level access. This means that it can be accessed from within the same package, but not from outside the package.

private: The private access modifier is the most restrictive access level, and it allows access to a class, method, or variable only from within the same class. It cannot be accessed from any other class, even if they are in the same package.

Here is an example of how access modifiers can be used:

public class MyClass {
public int publicVar;
protected int protectedVar;
int defaultVar;
private int privateVar;
public void publicMethod() {
}
protected void protectedMethod() {
}
void defaultMethod() {
}
private void privateMethod() {
}
}

What is the difference between private and protected access modifiers?

The main difference between private and protected access modifiers in Java is that private members are only accessible within the same class, while protected members are accessible within the same class and its subclasses, as well as within the same package.

Here are some more differences between private and protected:

Visibility: Private members are only visible within the same class, while protected members are visible within the same class and its subclasses, as well as within the same package.

Access: Private members cannot be accessed outside the class, while protected members can be accessed by subclasses and other classes in the same package.

Inheritance: Private members are not inherited by subclasses, while protected members are inherited by subclasses.

Overriding: Private members cannot be overridden in subclasses, while protected members can be overridden in subclasses.

Here is an example to illustrate the difference between private and protected access modifiers:

public class MyClass {
private int privateVar;
protected int protectedVar;
public void myMethod() {
privateVar = 1; // OK, can be accessed within the same class
protectedVar = 2; // OK, can be accessed within the same class
}
}
public class MySubclass extends MyClass {
public void mySubMethod() {
// privateVar = 3; // Error, cannot be accessed in subclass
protectedVar = 4; // OK, can be accessed in subclass
}
}
public class MyOtherClass {
public void myOtherMethod() {
MyClass obj = new MyClass();
// obj.privateVar = 5; // Error, cannot be accessed outside //the class
// obj.protectedVar = 6; // Error, cannot be accessed //outside the package or subclass
}
}

In this example, we have a class MyClass with a private variable privateVar and a protected variable protectedVar. The myMethod() method of MyClass can access both variables. We also have a subclass MySubclass of MyClass, which can access the protectedVar variable, but not the privateVar variable. Finally, we have another class MyOtherClass, which cannot access either variable, because they are not visible outside the class or its package.

    String

If string is not immutable then what challenge a developer can face?

If strings were mutable in Python, developers could face several challenges:

    Unexpected behavior: Mutating a string after it has been assigned to a variable could lead to unexpected behavior in different parts of the codebase. Imagine a situation where a function receives a string as input, modifies it, and then returns it. If the original string is also modified elsewhere in the code, it would be difficult to track the source of the changes and reason about the overall state of the string.
    Memory management issues: Mutable strings could introduce memory management complexities. If multiple variables point to the same mutable string object, changes made through one variable would be reflected in all the others. This could lead to confusion and memory leaks if not handled carefully.
    Concurrency problems: In concurrent programming scenarios, where multiple threads or processes access and potentially modify the same string, concurrency issues could arise. It would be difficult to ensure data consistency and avoid race conditions without proper synchronization mechanisms.
    Debugging difficulties: Debugging issues related to mutable strings would likely be more challenging. Tracing the origin of string modifications and the potential side effects across different parts of the codebase would require careful analysis.

Difference between String a = “ajay” and string a2= new String(“Ajay”)?

The key difference between the two string assignments lies in how they are stored in memory:

String a = "ajay":

    This creates a string literal "ajay". String literals are stored in the String pool, a special memory area in Java.
    The String pool ensures that only one copy of the same string literal exists in memory, even if it's assigned to multiple variables.
    This approach is memory-efficient and improves performance.

String a2 = new String("Ajay"):

    This creates a new String object using the new keyword and the String constructor.
    A new object is allocated in the heap memory, containing the characters "Ajay".
    This creates a separate copy of the string even if it has the same characters as a string literal in the pool.
    While it allows modifying the string content later, it consumes more memory compared to string literals.

    Serialization

What is transient Keyword and why serialization requires,on which parameter we do serialization?

Transient Keyword:

    The transient keyword is a variable modifier used in Java specifically during serialization.
    When applied to a field, it instructs the JVM to exclude that field’s value from being saved when the object is serialized.
    This means the field’s value is not persisted in the serialized form of the object.

Why Serialization Requires It:

Serialization is the process of converting an object’s state into a byte stream for storage or transmission. While useful, it’s not always desirable to serialize every single piece of data within an object. Here’s why the transient keyword is important:

    Excluding Sensitive Information: Certain fields might contain sensitive information like passwords or temporary data that shouldn’t be stored permanently. Using transient prevents these values from being serialized, safeguarding sensitive data.
    Avoiding Redundant Data: Some fields might be calculable from other serialized fields. For example, a person’s age can be derived from their date of birth. Serializing the age when it can be calculated later is redundant and wastes storage space.
    Non-Serializable References: If a field holds a reference to a non-serializable object, serializing it would lead to errors. Marking the field as transient avoids such issues.

Serialization and Parameter:

Serialization itself doesn’t directly involve parameters. It’s an object-level process where the entire state of a serializable object is converted into a byte stream. However, the transient keyword is applied to individual fields within the object, acting as a parameter on the field level.

By marking specific fields as transient, you control which parts of the object's state are serialized, ensuring sensitive data remains secure, redundant data is avoided, and compatibility issues with non-serializable references are prevented.
If i implement class A implements serializable will i get any error for it?

No, you will not get an error solely for implementing the Serializable interface in your class A. However, there are a few things to keep in mind:

Successful Serialization:

    Implementing Serializable only signifies that your class can be serialized. It doesn't guarantee successful serialization.
    For successful serialization, the following conditions need to be met:
    All fields of the class A must be either serializable themselves or have a custom serialization mechanism defined.
    The class should have a no-argument constructor to allow deserialization.

Potential Errors:

    If any field in class A is not serializable (e.g., custom objects without their own serialization implementation), you’ll encounter a NotSerializableException during serialization.
    If the class A doesn’t have a no-argument constructor, you might face issues during deserialization, potentially leading to an InvalidClassException.

What is the use of serialversionUID in and if my class doesn’t implement it?

The serialVersionUID is a long constant used in Java serialization to ensure compatibility between the serialized data and the class used for deserialization. Here's a breakdown of its usage and what happens if your class doesn't implement it:

Purpose of serialVersionUID:

    It acts as a unique identifier for the serialized form of a class.
    During deserialization, the JVM compares the serialVersionUID stored in the serialized data with the serialVersionUID of the class being used for deserialization.
    If they match, it indicates compatibility between the serialized data and the class, allowing successful deserialization.

What happens if your class doesn’t implement it:

    If you don’t explicitly define serialVersionUID in your Serializable class, the JVM calculates a default value based on various aspects of the class, like field names, types, and access modifiers.
    This default calculation can be sensitive to changes in the class structure, even seemingly minor ones.
    If the class structure changes in a later version, the default serialVersionUID might also change, leading to incompatibility during deserialization and potentially throwing an InvalidClassException.

Consequences:

    Deserialization failure can cause unexpected errors and program crashes.
    Maintaining compatibility across different versions of a class becomes difficult.

Best Practice:

    It’s strongly recommended to explicitly define serialVersionUID as a private static final long variable in your Serializable class.
    This ensures consistent compatibility and avoids potential issues during deserialization, especially in scenarios where serialized data might be shared across different versions of the class.

Here are some additional points to consider:

    You can use the serialver tool included in the JDK to generate a serialVersionUID for your class.
    If you make changes to the class structure that might affect compatibility, you should update the serialVersionUID accordingly.
    By explicitly defining serialVersionUID, you gain control over compatibility and prevent unexpected deserialization errors.

    Collection:HashSet

How hashset works internally and what is the main functionality of hashset,why we use hashset,how hashsets add method works?

Before going into internal implementation of HashSet in Java it is important to know two points about HashSet.

    HashSet in Java only stores unique values i.e. no duplicates are allowed.
    HashSet works on the concept of hashing just like HashMap in Java but its working differs from the HashMap in the following way-
    In HashMap a (Key, Value) pair is added and the hash function is calculated using key.
    Where as in the HashSet hash function is calculated using the value itself. Note that in HashSet we have add(E e) method which takes just the element to be added as parameter.
    Also you may have guessed by now, since hash function is calculated using value that is why only unique values are stored in the HashSet. If you try to store the same element again, the calculated hash function would be same, thus the element will be overwritten.
    Now coming back to internal implementation of HashSet in Java the most important point is HashSet class implementation uses HashMap to store it’s objects.

Within the HashSet there are many constructors one without any parameter and several more with initial capacity or load factor but each one of these constructor creates a HashMap. Since HashSet internally uses HashMap so knowing how HashMap works internally in Java will help you to understand how HashSet works internally in Java.

HashSet Constructor snippets

In the HashSet class in Java you can see that constructors of the class do create a HashMap.

/**
* Constructs a new, empty set; the backing <tt>HashMap</tt> instance has
* default initial capacity (16) and load factor (0.75).
*/
public HashSet() {
 map = new HashMap<>();
}
public HashSet(int initialCapacity, float loadFactor) {
 map = new HashMap<>(initialCapacity, loadFactor);
}
And the map, which is used for storing values, is defined as

private transient HashMap<E,Object> map;
In the constructor, if you have noticed, there are parameters named initial capacity and load factor. For HashSet, default initial capacity is 16, that is an array (or bucket) of length 16 would be created and default load factor is 0.75. Where load factor is a measure of how full the hash table is allowed to get before its capacity is automatically increased.
How elements are added in HashSet?

I stated in the point 2 above that HashSet calculates the hash function using value itself and there is no (Key, Value) pair in HashSet and then came the statement that HashSet internally uses HashMap to store objects. These two statements may sound contradictory as HashMap stores (key, value) pair so let’s see how these these two contradictory statements hold true.

Actually from add method of HashSet class put() method of HashMap is called where the value, which has to be added in the Set, becomes Key and a constant object “PRESENT” is used as value.

That’s how PRESENT is defined in HashSet implementation -

// Dummy value to associate with an Object in the backing Map
private static final Object PRESENT = new Object();
And that's how add method is implemented in HashSet class -
public boolean add(E e) {
 return map.put(e, PRESENT)==null;
}
So you can see with in the internal implementation of the HashSet it’s a (key, value) pair which is actually getting added. It’s just that the actual value (which is added to the HashSet) becomes the key and a dummy value “PRESENT” is added as value when storing it in the backing HashMap.

One thing to note here is, in HashMap value may be duplicate but Key should be unique. That’s how HashSet makes sure that only unique values are stored in it, since the value which is to be stored in the HashSet becomes the key while storing it in HashMap.
How element is removed from a HashSet in Java?

When we need to remove an element from the HashSet, internally again remove method of HashSet calls remove(Object key) method of the HashMap.

That is how it is implemented in HashSet class.

public boolean remove(Object o) {
 return map.remove(o)==PRESENT;
}
Here note that remove(Object key) method of the HashMap returns the Value associated with the key. Whereas the remove(Object o) method of the HashSet returns Boolean value. Also we know that for every value added in HashSet, internally when it is added to the associated HashMap, value becomes Key and the value is always an object called PRESENT. Therefore the value that is returned from the remove(Object key) method of the HashMap is always PRESENT thus the condition map.remove(o)==PRESENT.

How elements are retrieved from HashSet in Java?

In HashSet there is no get method as provided in Map or List. In HashSet iterator is there which will iterate through the values of the Set. Internally it will call the keyset of the HashMap, as values are stored as keys in the HashMap so what we’ll get is the values stored in the HashSet.

That’s how iterator is internally implemented in the HashSet in Java.

/**
* Returns an iterator over the elements in this set. The elements
* are returned in no particular order.
*
* @return an Iterator over the elements in this set
* @see ConcurrentModificationException
*/
public Iterator<E> iterator() {
 return map.keySet().iterator();
}
Points to note:

Unlike HashMap where hash function is calculated using key HashSet uses the value itself to calculate the hash function.
Since hash function is calculated using value that is why only unique values are stored in the HashSet.
HashSet internally uses HashMap to store its elements.
When element is added to HashSet using add(E e) method internally HashSet calls put() method of the HashMap where the value passed in the add method becomes key in the put() method. A dummy value “PRESENT” is passed as value in the put() method.anation-

    Collection: HashMap

How hashmap works internally ?what are the changes has been done in Java 8 in hashmap?How HashMap Internally Works in Java?

There are four things you should know about HashMap before going into internal working of HashMap in Java-
HashMap works on the principal of hashing.

    Map.Entry interface — This interface gives a map entry (key-value pair). HashMap in Java stores both key and value object, in bucket, as an object of Node class which implements this nested interface Map.Entry.
    hashCode() — HashMap provides put(key, value) for storing and get(key) method for retrieving values from HashMap. When put() method is used to store (Key, Value) pair, HashMap implementation calls hashcode on Key object to calculate a hash that is used to find a bucket where Entry object will be stored.
    When get() method is used to retrieve value, again key object (passed with the get() method) is used to calculate a hash which is then used to find a bucket where that particular key is stored.
    equals() — equals() method is used to compare objects for equality. In case of HashMap key object is used for comparison, also using equals() method Map knows how to handle hashing collision (hashing collision means more than one key having the same hash value, thus assigned to the same bucket). In that case objects are stored in a linked list, refer figure for more clarity.
    Where hashCode() method helps in finding the bucket where that key is stored, equals() method helps in finding the right key as there may be more than one key-value pair stored in a single bucket.
    Bucket term used here is actually an index of array, that array is called table in HashMap implementation. Thus table[0] is referred as bucket0, table[1] as bucket1 and so on.

How elements are stored internally in Java HashMap?

HashMap class in Java uses an array called table of type Node to store the elements which is defined in the HahsMap class as-
transient Node[] table;
Node is defined as a static class with in a Hashmap.
static class Node implements

Map.Entry {
 final int hash;
 final K key;
 V value;
 Node next;
 ..
 .. 
}

As you can see for each element four things are stored in the following fields-
-hash- For storing Hashcode calculated using the key.
-key- For holding key of the element.
-value- For storing value of the element.
-next- To store reference to the next node when a bucket has more than one element and a linkedlist is formed with in a bucket to store elements.
Following code shows how Node(key-value pair) objects are stored internally in table array of the HashMap class.
How important it is to have a proper hash code and equals method can be seen through the help of the following program:

public class HashMapTest {
 public static void main(String[] args) {
 Map <Key, String> cityMap = new HashMap<Key, String>();
 cityMap.put(new Key(1, "NY"),"New York City" );
 cityMap.put(new Key(2, "ND"), "New Delhi");
 cityMap.put(new Key(3, "NW"), "Newark");
 cityMap.put(new Key(4, "NP"), "Newport");
 System.out.println("size before iteration " + cityMap.size());
 Iterator <Key> itr = cityMap.keySet().iterator();
 while (itr.hasNext()){
 System.out.println(cityMap.get(itr.next())); 
 }
 System.out.println("size after iteration " + cityMap.size()); 
 }
 
}
// This class' object is used as key
// in the HashMap
class Key{
 int index;
 String Name;
 Key(int index, String Name){
 this.index = index;
 this.Name = Name;
 }
 
 @Override
 // A very bad implementation of hashcode
 // done here for illustrative purpose only 
 public int hashCode(){
 return 5;
 }
 
 @Override
 // A very bad implementation of equals
 // done here for illustrative purpose only 
 public boolean equals(Object obj){
 return true;
 }
 
}

Output:
size before iteration 1
Newport
size after iteration 1
Refer Overriding hashCode() and equals() method in Java to know more about hashCode() and equals() method

Understanding the Code
Lets get through the code to see what is happening, this will also help in understanding how put() method of HashMap works internally.
Notice that I am inserting 4 values in the HashMap, still in the output it says size is 1 and iterating the map gives me the last inserted entry. Why is that?
Answer lies in, how hashCode() and equals() method are implemented for the key Class. Have a look at the hashCode() method of the class Key which always returns “5” and the equals() method which is always returning “true”.
When a value is put into HashMap it calculates a hash using key object and for that it uses the hashCode() method of the key object class (or its parent class).

Based on the calculated hash value HashMap implementation decides which bucket should store the particular Entry object.
In my code the hashCode() method of the key class always returns “5”. This effectively means, calculated hash value, is same for all the entries inserted in the HashMap.

Thus all the entries are stored in the same bucket.
Second thing, a HashMap implementation does use equals() method to see if the key is equal to any of the already inserted keys (Recall that there may be more than one entry in the same bucket).

Note that, with in a bucket key-value pair entries (Entry objects) are stored in a linked-list (Refer figure for more clarity). In case hash is same, but equals() returns false (which essentially means more than one key having the same hash or hash collision) Entry objects are stored, with in the same bucket, in a linked-list.

In my code, I am always returning true for equals() method so the HashMap implementation “thinks” that the keys are equal and overwrites the value. So, in a way using hashCode() and equals() I have “tricked” HashMap implementation to think that all the keys (even though different) are same, thus overwriting the values.

In a nutshell there are three steps in the internal implementation of HashMap put() method-
Using hashCode() method, hash value will be calculated. In which bucket particular entry will be stored is ascertained using that hash.

equals() method is used to find if such a key already exists in that bucket, if not found then a new node is created with the map entry and stored within the same bucket. A linked-list is used to store those nodes.
If equals() method returns true, it means that the key already exists in the bucket. In that case, the new value will overwrite the old value for the matched key.
How HashMap get() method works internally?

    As we already know how Entry objects are stored in a bucket and what happens in the case of Hash Collision it is easy to understand what happens when key object is passed in the get() method of the HashMap to retrieve a value.
    Using the key (passed in the get() method) again hash value will be calculated to determine the bucket where that Entry object is stored, in case there are more than one Entry object with in the same bucket (stored as a linked-list) equals() method will be used to find out the correct key. As soon as the matching key is found get() method will return the value object stored in the Entry object.
    In case of null Key
    HashMap in Java also allows null as key, though there can only be one null key in HashMap. While storing the Entry object HashMap implementation checks if the key is null, in case key is null, it always map to bucket 0, as hash is not calculated for null keys.

HashMap changes in Java 8

    Though HashMap implementation in Java provides constant time performance O(1) for get() and put() methods but that is in the ideal case when the Hash function distributes the objects evenly among the buckets.
    But the performance may worsen in the case hashCode() used is not proper and there are lots of hash collisions. As we know now that in case of hash collision entry objects are stored as a node in a linked-list and equals() method is used to compare keys. That comparison to find the correct key with in a linked-list is a linear operation so in a worst case scenario the complexity becomes O(n).
    To address this issue in Java 8 hash elements use balanced trees instead of linked lists after a certain threshold is reached. Which means HashMap starts with storing Entry objects in linked list but after the number of items in a hash becomes larger than a certain threshold, the hash will change from using a linked list to a balanced tree, this will improve the worst case performance from O(n) to O(log n).

    Try catch finally related question

What is finalize method?

Finalize method:

    A method inherited from the Object class, called just before an object is garbage collected.
    Used for cleanup activities like releasing resources (files, network connections).

Where to write finalize in your application?

Where to write finalize:

    Override the finalize() method in your class if you need specific cleanup tasks.

What is the flow of webservices?

Web service flow:

    Client sends a request (e.g., HTTP) to the web service.
    Web service processes the request and generates a response.
    Response is sent back to the client.

What is the entry point of webservices?

Web service entry point:

    Depends on the web service technology (e.g., Java: servlet, JAX-WS endpoint).
    Generally defined in configuration files or annotations.

    Topic:Hibernate

What is Hibernate

Its an ORM that is able to map java objects to a variety of diffrent relational database ,allows us to configuration and to use and connect to database and to specify which is our java object should be mapped to relational tables
It does job of creating SQL that is able to save update delete and query data from the databse
It presents us the data to us as java objects that we can use and manipulate and then save back to database
What is the use of Hibernate why should we use it and why we should not use sql?

    -Hibernate is persisting technology that is based on the idea of object relational mapping or ORM.
    ORM is a framework that enable you to map the world of objects found in object oriented language like java to row in relational tables found in relational database like MYSQL.
    Why we need Hibernate because, without an ORM we have to translate this object into a few different SQL statements that will insert/update the data into the tables,but to do that we have to write java code to create sql its not that hard but its tedious and pretty easy to get wrong ,thats when the ORM comes in.
    using orm we can declare certain java class should be mapped to relational table and let the ORM deal with it, map objects to tables

    Spring

Difference in setting the value in constructor vs setting the value in getter and setter,both are doing the same thing

If you want to have an immutable class use constructor otherwise use setters.

You should use the constructor approach, when you want to create a new instance of the object, with the values already populated(a ready to use object with value populated). This way you need not explicitly sit and call the setter methods for each field in the object to populate them.

You set the value using a setter approach, when you want to change the value of a field, after the object has been created.

MyObject obj1 = new MyObject("setSomeStringInMyObject"); // Constructor approach
// Yippy, I can just use my obj1, as the values are already populated
// But even after this I can change the value
obj1.setSomeString("IWantANewValue"); // Value changed using setter, if required.
..
MyObject obj2 = new MyObject();
obj2.setSomeString("setSomeStringNow"); // Setter approach
// values weren't populated - I had to do that. Sad :(




if you want to create immutable objects, you cannot use setter-methods approach. I won’t say everything has to be initialised in the constructor because different approaches exist, like lazy-evaluation which can be used even with immutable objects.

    Topic: SQL Query

Scenario — we have one table which has name and salary,
write a query which gives me two persons highest salary earner can you tell me the query

Table
Employee
Employee ID Salary
3 200
4 800
7 450

1.
select DISTINCT(salary) from employee order by salary desc limit 1,1
Note:
limit 0,1 - Top max salary limit 1,1 - Second max salary limit 2,1 - Third max salary limit 3,1 - Fourth max salary
2.We can do that like this
SELECT Salary FROM
(SELECT DISTINCT Salary FROM Employee ORDER BY Salary desc)
WHERE ROWNUM <= 2;
3.select (SELECT MAX(Salary) FROM Employee) maxsalary, (SELECT MAX(Salary) FROM Employee WHERE Salary NOT IN (SELECT MAX(Salary) FROM Employee )) as [2nd_max_salary]
Topic: Collection
ArrayLIst

    Coding Problems

Write a program to check the minimum number of occurence of a character in a given string?

public class MinimumNumberOccrenceofString {
public static void main(String[] args) {
// TODO Auto-generated method stub
String str = "ajay";
char c ='a';
System.out.println(count(str,c));
}
private static int count(String str, char c) {
int result =0 ;
for(int i=0;i<str.length(); i++) {
//checking charector in string
if(str.charAt(i)==c) {
result++;
}
}
return result;
}
}

I’m happy to assist further! If you have any questions, feedback, or specific topics you’d like me to address, please don’t hesitate to ask.
