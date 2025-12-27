  ## What is Apex and when to use Apex ?
Apex is server-side programming and strongly typed object oriented programming language which is developed by Salesforce.com.
Apex allow us to write the code that executes on the force.com platform. Apex is saved,compiled and executed on the servers of Force.com platform.
- It is use to build SaaS applications on top of salesforce CRM functionality and for writing business logic.
- Apex is used to perform a couple of business processes which are not supported by workflow, means if we write down the complex business processes which is not possible to be created with the help of point and click tools then this situation
we have to write down Apex.
- To perform complex validation over multiple objects we use Apex.
- To create webservices and email services we use Apex.
- For transactions and rollbacks we use Apex.

In other Words:
- Triggers likhne ke liye
- Complex validation ke liye
- Database operations (insert/update/delete) ke liye.
  
Example:
- Record save hone se pehle validation
- Email bhejna
- Related records update karna

## What is mean by Apex is strongly typed ?
It means ki variable ka Datatype phle define karna padta hai.
```
Integer a = 10;   // correct
a = 'test';      // error
```

## Features not supported by Apex ?
- If we want to showcase anything into the UI then we need to use point-click tools,visual force,lightning.No UI element can be shown with the help Apex Other than the error message. Apex lies on to the controller part of the MVC Architecture it doesnt lie on to the view part (UI).
- It cannot change the standard SFDC functionality but can be used to stop its execution or to add new functionality.
- It cannot be used to create a temporary files.
- It cannot create multiple threads.

---
## What is Variables in Apex ?
Variable is just a name of the memory location where Data is store.

```
Datatype variableName;
String name;
```

## What is Datatype and their type in Apex ?
A datatype defines the type of data that a variable can store.

Apex has four main types of datatypes:
- Primitive
- sObject
- Collection
- Enum

## What are primitive datatypes in Apex?
Primitive datatypes are basic datatypes used to store simple values.
- Integer
- String
- Boolean
- Decimal
- Date
- Datetime
- Id

## What is null in Apex?
Null means a variable does not have any value assigned to it.

## What is the default value of a variable in Apex?
If a variable is not initialized, Apex assigns a default value such as 0 for numbers, false for Boolean, and null for objects,null for Strings.

## Difference between static and non-static variables?
Static variables belong to the class and share a single copy, while non-static variables belong to an object.
```
public class Demo {
    static Integer count = 0;
    Integer number = 10;
}
```
## What is a final variable in Apex?
A final variable is a variable whose value cannot be changed once assigned.

---

## What are the main types of operators in Apex?
The main types of operators in Apex are:
- Arithmetic Operators (+ , - , * , /)
- Relational Operators (> < >= <= == !=)
- Logical Operators (&&, ||, !)
- Assignment Operators (a += 5; // a = a + 5;)
- Ternary Operator (String result = (a > 5) ? 'Greater' : 'Smaller';)

## Conditional Statements :
- if
- if–else
- else–if ladder
- nested if
- ternary operator

## Loops:
- for loop
- while loop
- do while loop
- for each loop

---

## What is a collection in Apex ?
A collection  is a data structure that can store multiple values of the same datatype in a single variable.
In simple words Collection allows you to handle multiple records or value together.

3 types of Collections in Apex :
1. *List*: A List is an ordered collection that allows duplicate values and is accessed by using index.

## How do you declare a List in Apex?
```
List<Integer> numbers;

```
`List = collection type`
`Integer = datatype`
`numbers = variable name`

## How do you create an empty List?
```
List<String> names = new List<String>();
```
## How do you declare and initialize a List together?
```
List<String> cities = new List<String>{'Delhi', 'Mumbai', 'Pune'};
```
## Is List dynamic in Apex?
Yes, Lists in Apex are dynamic, meaning their size can grow or shrink at runtime and can add/delete values at runtime.List does not have a fixed size.
## How do you add elements to a List?
```
List<String> names = new List<String>();
names.add('A');
names.add('B');
```
## Can we insert an element in the middle of a List?
Yes, elements can be inserted at a specific index using the `add(index, value)` method.
```
names.add(1, 'C');
```
## How do you access elements from a List?
```
String firstName = names[0]; //A
String firstName = names[1]; //C
String firstName = names[2]; //B
```
## Does List allow duplicate values?
Yes, a List allows duplicate values.
```
List<Integer> nums = new List<Integer>{1, 1, 2};
```
## How do you get the size of a List?
```
Integer size = names.size();
```
## How do you remove elements from a List?
```
names.remove(0); //Remove by index
names.remove('A'); //Remove by value
```
## How do you iterate over a List?
Using for-each loop (BEST PRACTICE):
```
for(String name : names) {
    System.debug(name);
}
```
## What is a List of sObjects?
A List of sObjects is used to store multiple Salesforce records of the same object type.
```
List<Account> accList = new List<Account>();
```
## Understand about some Important points which we may cover later in this document but right now we have to understand some terms:
- Governor Limits: It means rules which is apply on salesforce apex code. Rules are like kitni bar database call kar sakte hai, kitna CPU use kar sakte ho, kitni data memory me rakh sakte ho etc.
Or agar limit cross hui to runtime exception hoga.
- Salesforce is a shared cloud platform, many users and orgs works on a single server. Agar koi banda ek requset main system ko hang na karde to isi liye ek protection create karte hai ussi ko governor limits bolte hai.

## List Methods :
1. addAll() - The addAll() method is used to add all elements of one list into another list.
```
List<Integer> a = new List<Integer>{1, 2};
List<Integer> b = new List<Integer>{3, 4};

a.addAll(b); // a = [1,2,3,4]
```

2. contains() - The contains() method checks whether a list contains a specific value and returns a Boolean.
```
Boolean result = a.contains(2); // true
Boolean result = a.contains(5); // false
```

3. isEmpty() - The isEmpty() method checks whether a list has zero elements.
```
if(a.isEmpty()) {
    System.debug('List is empty');
}
```

4. clear() - The clear() method removes all elements from a list.
5. get() - The get() method retrieves an element at a specific index.
```
Integer val = a.get(0);
```

6. set() - The set() method replaces the value at a specific index.
```
The set() method replaces the value at a specific index.
```
## What is Index Out of Bounds Exception?
This exception occurs when you try to access an index that does not exist in the list.
```
a.get(10); //Exception
```
How to avoid 
```
if(index < a.size()) {
    a.get(index);  
}
```
## Governor limits related to Lists?
Collections consume heap memory.
Apex limits the amount of heap memory used by collections. Very large lists can cause heap size exceptions.
- (Heap deep dive later.)

## Real-world use case of List?
Lists are commonly used to:
- Store query results
- Perform bulk DML operations
- Process records in triggers


2. *Set*: A Set is a unordered collection where duplicate values are not allowed and set are unique.
Syntax:
```
Set<DataType> setName = new Set<DataType>(); // syntax 1

Set<Integer> marks = new Set<Integer>{10, 20, 30, 20};  // syntax 2
System.debug(marks);

```

## Add Values in Set:
```
Set<String> names = new Set<String>();
names.add('Amit');
names.add('Rahul');
names.add('Amit'); // duplicate

System.debug(names);  //{Amit, Rahul}
```

## addAll() in Set:
```
Set<Integer> s1 = new Set<Integer>{1,2};
Set<Integer> s2 = new Set<Integer>{3,4};

s1.addAll(s2);
System.debug(s1);   //{1,2,3,4}
```

## contains() in Set:
```
Set<String> cities = new Set<String>{'Delhi','Mumbai'};

System.debug(cities.contains('Delhi')); // true
System.debug(cities.contains('Pune'));  // false
```

## remove(),size(),clear().

## How to iterate Set ?
we can loop over a Set using a for-each loop. However, we cannot use index-based loops because Set does not maintain order.
```
Set<String> s = new Set<String>{'A','B','C'};

for(String val : s){
    System.debug(val);
}
```
## Interview Important Points (Must Remember)

- Set me duplicate values allowed nahi
- Order fix nahi hota
- Indexing possible nahi
- contains() fast hota hai
- Id, String, Integer, sObject sab store kar sakta hai
- SOQL ke saath frequently use hota hai

3. *Map*- Map is a collection of key–value pairs where each key is unique and is used to access its corresponding value.
-Key unique hoti hai
-Value duplicate ho sakti hai
-Fast data access hota hai key ke through

## Why use Map over other collections ?
-Id ke through record access
-Fast lookup
-Parent–Child data handling
-Trigger & bulk processing

Syntax:
```
Map<KeyType, ValueType> mapName = new Map<KeyType, ValueType>();
```
## Declare + Initialize 
```
Map<String, Integer> marks = new Map<String, Integer>{
    'Maths' => 90,
    'English' => 80
};
```
## How to add values in Map ?
By PUT Method:
```
Map<Integer, String> m = new Map<Integer, String>();
m.put(1, 'Amit');
m.put(2, 'Rahul');
m.put(1, 'Neha'); // overwrite
```
## Map important Methods:
1. get()
```
System.debug(marks.get('Maths')); // 90
```
2.containsKey()
```
marks.containsKey('Maths'); // true
```
3.containsValue()
```
marks.containsValue(80); // true
```
4.ketSet()
```
Set<String> keys = marks.keySet();
```
5.values()
```
List<Integer> vals = marks.values();
```
6. remove,size,clear etc..

## How to loop in Map ?
1. By keySet() loop:
```
for(String key : marks.keySet()){
    System.debug(key + ' = ' + marks.get(key));
}
```
2. By values loop:
```
for(Integer v : marks.values()){
    System.debug(v);
}
```
## Interview Important Points:
- Key hamesha unique hoti hai
- Value overwrite hoti hai duplicate key pe
- Fast lookup using key
- Direct indexing possible nahi
- Map loop directly nahi hota
























