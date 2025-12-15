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










