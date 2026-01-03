# OOPs in Apex

## What does Object Oriented means ?
In relation to programming language,object oriented means that the code focuses on describing objects.Object can be anything that has unique characterstics,such as a person, people, flower
etc. Before truly understand about the object oriented means I need to understand about two things
Classes and Objects.

## Class in Apex :
A class is a blueprint.Objects are based on classes.A class defines a set of charaterstics and behaviours that are comman to all objects of that class.
Think about a student,it has charaterstics such as name,age,email,phone no and behaviour such as color, height, anger etc.
- Charaterstics are variables/properties.
- Behaviour are methods.

<img width="344" height="262" alt="image" src="https://github.com/user-attachments/assets/6c11d76f-2061-48bc-966a-2483037c38df" />

An access modifier is a keyword in a class or method declaration. The access modifier determines what other Apex code can see and use the class or method. Although there are other access modifiers, publicCopy is the most common. Public classes are available to all other Apex classes within your org.

## Methods in Class: 
Methods are defined within a class. A method describes the behaviors inherited by objects of that class. A class can have one or more methods. The Flower class has three methods (behaviors): growCopy, pollinateCopy, and wiltCopy.

A method is declared (created) like this:

<img width="816" height="267" alt="image" src="https://github.com/user-attachments/assets/bac47855-14b5-4dcc-99db-3548d34684fa" />

Example:
```
public class flower{
  public static void wilt(Integer numberOfPetals){    //method 1
      system.debug(numberOfPetals);
  }

  public static void testCall(){               //method 2
      wilt(4);
  }
}

flower.testCall();          //indirect call
flower.wilt(4);             //direct call
```

## Return Type
The return type is a specific data type, such as Boolean, String, or Account, or it can be void (nothing), like this:
```
public static void wilt(Integer numberOfPetals){
    system.debug(numberOfPetals);
}
```
When the method return type is voidCopy, the method does not return a value. To return a value, replace voidCopy with a different return type.
For example, here, the wiltCopy method expects a returnCopy (response) value that's an integer.
<img width="616" height="178" alt="image" src="https://github.com/user-attachments/assets/7c282991-82d0-433b-b6e8-c9721ce43237" />

```
public static Integer wilt(Integer numberOfPetals){
    if(numberOfPetals >= 1){
        numberOfPetals--;
    }
    return numberOfPetals;       //return value is comming here. 
}
```
---
## Object in Apex:
An object is an instance of a class that contains actual values and can access the properties and methods defined in the class.(Object class ka ek real instance hota hai jo class ki properties aur methods ko use karta hai.)

## Constructor method:
A constructor is a special method of a class that is automatically called when an object of the class is created.
It is used to initialize the object with initial values.
```
public class Flower {
    String color;

    // Constructor
    public Flower() {
        color = 'Red';
    }
}

Flower f = new Flower();
System.debug(f.color); // Red
```
Parameterized constructor :
```
public class Flower {
    String color;

    public Flower(String c) {
        color = c;
    }
}
Flower f1 = new Flower('Red');
Flower f2 = new Flower('Yellow');

```
## Q1. Agar properties ke saath hi default value set kar dein, to constructor kyu chahiye?
Agar sab objects ke liye same default value chahiye ho, to constructor optional hota hai.
Constructor tab use hota hai jab object ko dynamic values deni ho, calculation ya validation karni ho.

## Q2. Constructor static method ke saath kyu use nahi hota?
Constructor object creation ke time call hota hai.
Static methods class level ke hote hain aur object create nahi karte.
Isliye constructor sirf objects ke saath hota hai, static methods ke saath nahi.

## Static vs Instance (Non-Static) Variables & Methods — Apex OOPs
Static = class ke saath juda hua
Instance (non-static) = object ke saath juda hua

## Q1. What is Instance variable ?
Instance variable wo hota hai jo har object ke liye alag-alag hota hai.
```
public class Flower {
    String color;   // instance variable
}

Flower f1 = new Flower();
Flower f2 = new Flower();

f1.color = 'Red';
f2.color = 'Yellow';

```
## Q2. What is Static variable ?
Static variable poori class ke liye ek hi hota hai. Sab objects usi ek value ko share karte hain.
```
public class Flower {
    static Integer count = 0;
}
Flower f1 = new Flower();
Flower f2 = new Flower();

Flower.count++;
System.debug(Flower.count); // 1

Flower.count++;
System.debug(Flower.count); // 2

//ye count object ka nahi class ka hai remember
```
## In case of method:
## Instance method - 
```
public class Flower {
    String color;

    public void showColor() {       //non-static method
        System.debug(color);
    }
}
Flower f1 = new Flower();   //obj 1
f1.color = 'Red';
f1.showColor();
Flower f2 = new Flower();   //obj 2
f2.color = 'Red';
f2.showColor();
```

## Static method - 
```
public class Flower {
    public static void greet() {    //static method
        System.debug('Hello');
    }
}
Flower.greet();      //no need of object
```

## Q3. Why Static Methods are heavily used in Apex?
Salesforce me static methods isliye zyada use hote hain kyunki unhe bina object banaye directly call kiya ja sakta hai.Aur Salesforce me mostly kaam class-level pe hota hai, object-level pe nahi.
...ye question baad main or detail main samjhege abhi ke liye itna enough hai...

---

# Encapsulation














