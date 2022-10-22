# Python-Object-Oriented-Programming-book
My notes of Python Object Oriented Programming book by Steven F. Lott and Dusty Phillips

This book teaches us how to build robust and maintainable Object Oriented Python applications. 

## Table of Contents

- [Chapter 1 - Object Oriented Design](#chapter1)
- [Chapter 2 - Objects in Python](#chapter2)

<a name = chapter1>
<h1>Chapter 1 - Object Oriented Design</h1>
</a>

This chapter introduces the core concepts underlying object-oriented design. This provides a road map through the ideas of state and behavior, attributes and methods, and how objects are grouped into classes. This chapter also gives a brief introduction to encapsulation, inheritance, and composition.

### What does Object Oriented mean?
*Objects* in software development means a collection of **data** and **behaviors** associated with them. And *Oriented* in english dictionary means *directed towards*. So, combiningly Object-Oriented Programming means writing code directed towards modeling objects.

Before writing OOP code there are two more steps. **Object Oriented Analysis** and **Object Oriented Design** that if done can make Object Oriented Programming much easier.

### What is Object Oriented Analysis (OOA)?
- It is the process of looking at a problem, system, or task (that somebody wants to turn into aworking software application) and identifying the objects and interactions between those objects. 
- It is all about *what needs to be done*.
- The output of the analysis stage is a description of the system, often in the form of requirements.

### What is Object Oriented Design (OOD)?
- It is the process of converting the output of the OOA stage (i.e, description of the system, which are often in form of requirements) into an implementation specification.
- In this stage we, name the objects, define the behaviors, and formally specify which objects can activate specific behaviors on other objects.
- The design stage is all about transforming *what should be done?* into *how it should be done?*
- The output of this stage is, turning the requirements defined during object-oriented analysis into a set of **classes** and **interfaces** that could be implemented in some Object Oriented Programming language (in our case Python).

### Finally Object Oriented Programming, what is it?
- It is the process of converting a design that came out from OOD stage,  into a working program.

### Objects and Classes
**Class**: In object oriented modeling, Class is the blueprint for object(s). A Class has set of *attributes* and *methods*. The attribute defines the properties of the object of that class and methods are the behaviors or actions that we can perform on that object.

>For example: an Orange is an object of Orange class which has attributes such as colour and weight. and method such as *make juice* which defines an action we can perform on the Orange type object.

**Object**: Object on the other hand is an instance of the class. 

>For example: You might have three oranges on table. Each of these oranges is distinct object, but all three have attributes and behaviors associated with one class i.e, the general class of orange (the blueprint).

##### OBJECTS ARE INSTANCES OF CLASSES THAT CAN BE ASSOCIATED WITH EACH OTHER.
Let's take two objects each of different classes, object *orange* from Orange class and object *basket* from Basket class. Object of Orange class can be put in Object of Basket class. This relation between two objects is called **association**.


##### DATA DESCRIBES THE STATE OF OBJECT.
Data represents the individual characteristics of a certain object. Any specific object can have different data values for the given characteristics. 

>For example: The three oranges on our table could each weigh a different amount. The orange class could have a weight to represent that data. All instances of the orange class have weight attribute, but each orange has a different value for this attribute. Attributes don't have to be unique, though; any two oranges may weigh the same amount.

**Atrributes** are referred to as members or properties. We can also call an attribute **instance variable**. Since, they are variables for each instance of a class.

##### BEHAVIORS ARE ACTIONS.
**Behaviors** are actions that can occur on an object. The behaviors that can be performed on a specific class of object are expressed as the **methods** of the class.
- methods are like functions in structured programming, but they have access to the attributes.
- methods can also accept parameters and return values.
- The actual object instances that are passed into a method during a specific invocation are usually referred to as **arguments**.