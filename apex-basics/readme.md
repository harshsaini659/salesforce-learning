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
- List: A List is an ordered collection that allows duplicate values and is accessed using index.

## How do you declare a List in Apex?
```
List<Integer> numbers;

```
`List = collection type`
`Integer = datatype`
`numbers = variable name`










