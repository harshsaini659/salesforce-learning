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
-- List: A List is an ordered collection that allows duplicate values and is accessed using index.

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

-- Set:











