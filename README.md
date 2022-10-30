# Python-Object-Oriented-Programming-book
My notes of Python Object Oriented Programming book by Steven F. Lott and Dusty Phillips

This book teaches us how to build robust and maintainable Object Oriented Python applications. 

## Table of Contents

- [Chapter 1 - Object Oriented Design](#chapter1)
- [Chapter 2 - Objects in Python](#chapter2)
- [Chapter 3 - When Objects are Alike](#chapter3)
- [Chapter 4 - Expecting the Unexpected](#chapter4)

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

##### HIDING DETAILS AND CREATING THE PUBLIC INTERFACE
The key purpose of modeling an object in object-oriented design is to determine what the public interface of that object will be. 

The **interface** is the collection of attributes and methods that other objects can access to interact with that object. Other objects do not need, and in some languages are not allowed, to access the internal workings of the object.

**Encapsulation**: The process of hiding the implementation of an object is suitably called information hiding and is also known as encapsulation.

>A common real-world example is the television. Our interface to the television is the remote control. Each button on the remote control represents a method that can be called on the television object. When we, as the calling object, access these methods. When we press volume buttons to adjust volume on TV, we do not care what electronic signals are being sent to adjust the volume, or whether the sound is destined for speakers or headphones etc.

#### Abstraction
Abstraction in object oriented modelling means dealing with the level of detail that is most appropriate to a given task. It is the process of extracting a public interface from the inner details.

>For Example: A car's driver needs to interact with the steering, accelerator, and brakes. The workings of the motor, drive train, and brake subsystem don't matter to the driver. A mechanic, on the other hand, works at a different level of abstraction, tuning the engine and bleeding the brakes.

The figure below shows the two abstraction levels for car:
![Alt text](./images/abstraction.jpeg?web=raw "abstraction_levels")

It is possible to make an abstraction class that does not implement any methods at all. Such a class would simply tell us what the class should do, but provides absolutely no advice on how to do it. These purely abstract classes are called **interfaces**.


### Relationships
There are three types of relationships in object oriented modelling. The level of abstractions are defined by these relationships.
- Composition
- Aggregation
- Inheritance

### Composition
Composition is the act of collecting several objects together to create a new one. 
> For Example: A car is composed of an engine, transmission, starter, headlights, and windshield, among numerous other parts. The engine, in turn, is composed of pistons, a crank shaft, and valves etc.

The above example, composition is good way to provide level of abstraction. The *Car* object can provide the interface required by the driver, and the *Engine* object can provide the interface for the mechanic.

### Aggregation
Aggregation is almost exactly like composition. The difference is that aggregate objects can exist independently.

To know the difference between Aggregation and Composition see this example:
>Example: In a chess game, it would be impossible for a position to be associated with a different chess board, so we say the board is **composed** of positions. But the pieces, which might exist *independently* of the chess set, are said to be in an **aggregate** relationship with that set.

Another way to differentiate between aggregation and composition is to think about the lifespan of the object:
- If the composite (outside) object controls when the related (inside) objects are created and destroyed, composition is most suitable.

- If the related object is created independently of the composite object, or can outlast that object, an aggregate relationship makes more sense.

### Inheritance
Inheritance is sort of like a family tree. My name is Deepesh. My grandfather's last name was Yadav, and my father inherited that name. I inherited it from him. 
Similarly, In object-oriented programming, instead of inheriting features and behaviors from a person, one class can inherit attributes and methods from another class.

>For example, there are 32 chess pieces in a chess set, but there are only six different types of pieces (pawns, rooks, bishops, knights, king, and queen), each of which behaves differently when it is moved. All of these classes of piece have properties, such as color and the chess set they are part of, they also have unique shapes, and different moves.

The figure below depicts how the six types of pieces can inherit from a Piece class:
![Alt text](./images/inheritance.jpeg?web=raw "inheritance")

The hollow arrows indicate that the individual classes of pieces inherit from the **Piece** class. All the child classes automatically have a **chess_set** and **color** attribute inherited from the base class **Piece**. Each piece provides a different **shape** property and a different **move** method to move the piece to a new position.

### Multiple Inheritance
A simple example to understand **Multiple Inheritance**, When strangers tell a proud mother that her son has *his father's eyes*, she will typically respond along the lines of, *yes, but he got my nose*. This is multiple inheritance, *where a child inherits different features from both of his parents.*

Similarly, in object oriented programming, multiple inheritance allows a **subclass** to inherit functionality and attributes from **multiple parent classes**. 

#### But...
Multiple Inheritance can be a tricky business, there is no harm in using it, if the two parent classes the subclass is inheriting functionality and attributes from are **distinct**. But if the parent classes are not distinct, i.e., if both of the parent classes have same **method(s)** or **attribute(s)**, then the subclass will get confuse which method to inherit from which parent class or which attribute to inherit from which parent class.

<a name = "chapter2">
<h1>Chapter 2 - Objects in Python</h1>
</a>
 
 In this chapter we will learn:
 - Type Hints
 - Creating Python Classes
 - Instantiating Objects
 - Organizing Classes into Packages and Modules

### Type Hints
Type hints is a feature of Python that allows you to explicitly declare the data type of a variable when declaring it. 

#### How to write Type Hints and Type check?
Writing type hints is a very simple task. See the code below for example:

```python
    def odd(n : int) -> bool:
        return n%2 != 0

    def main():
        print(odd(2))

    if __name__ == "__main__":
        main()
```

In the above code, "n : int" is a type hint and the "-> bool" is also a type hint. It explicitly declares that (n) is *"int"* type and the return type of the *odd* function is *"bool"* type.

Thats it, this is how type hints are written.


#### Type checking using ***mypy***
Type checking is the process of checking type of variables in program with the associated type hints if given. This helps a lot when we are debugging our program. Now, let's see how type checking is done.

For this let's take the following erroneous code:

```python
    # erroneous_code.py
    def odd(n : int) -> bool:
        return n%2 != 0

    def main():
        print(odd("Hello World"))

    if __name__ == "__main__":
        main()
```
The code is same as above, but with one little change, in the odd function we are passing a *str* type that is "Hello World" its going to show an error. But with the type hints, we can simply just look at the code and tell, the odd function takes **int** type input and returns a **bool** type.

But even if we are not able to find what's wrong with the program. We can use the ***mypy*** library to check the type hints, the ***mypy*** tool helps in checking the type hints for consistancy.

For that, we need to install ***mypy*** library. Just simply write this code in command prompt.
```
    pip install mypy
```

NOTE: Be sure to activate your virtual environment before installing this library.

After installing the mypy library, simply write the following code in command prompt terminal.

```
    $ mypy --strict your/path/to/erroneous_code.py
```

The output of the above code is as follows:
```
    (approach_ml) C:\Users\OOP>mypy --strict erroneous_code.py
    erroneous_code.py:4: error: Function is missing a return type annotation
    erroneous_code.py:4: note: Use "-> None" if function does not return a value
    erroneous_code.py:5: error: Argument 1 to "odd" has incompatible type "str"; expected "int"
    erroneous_code.py:9: error: Call to untyped function "main" in typed context
    Found 3 errors in 1 file (checked 1 source file)
```

Here are the two problems:
- At line 4: The main() function doesn't have a return type; mypy suggests including "-> None" to make the absence of a return value perfectly explicit.
- More important is line 5: the code will try to evaluate the odd() function using a str value. This doesn't match the type hint for "odd()" and indicates another possible error.

### Creating Python Classes
Creating classes in python is very easy. For example see the code below:

```python
    class MyFirstClass:
        pass
```
- The class definition starts with the `class` keyword.
- The name of the class is written in CamelCase i.e., the first letter of each word in the class name should be capital. For example: MyFirstClass, the M, F and C are capital.

#### Instantiating objects of class
```python
    # define a class
    class MyFirstClass:
        pass

    # instantiate objects of class
    object1 = MyFirstClass()
    object2 = MyFirstClass()
```
The above code creates two instances of `MyFirstClass`, if we print these two objects we can see the memory addresses of these.

```python
    # define a class
    class MyFirstClass:
        pass

    # instantiate objects of class
    object1 = MyFirstClass()
    object2 = MyFirstClass()

    # print objects
    print(object1)
    print(object2)
```

Output:
```
    <__main__.MyFirstClass object at 0xb7b7faec>
    <__main__.MyFirstClass object at 0xb7b7fbac>

```
The above output confirms that the objects were instantiated successfully.

#### EACH OBJECT OF THE SAME CLASS ARE DISTINCT
The objects created from the same class are distinct objects. To confirm this see the code below:
```python
    # python objects are distinct
    # define a class
    class MyFirstClass:
        pass

    # instantiate objects of class
    object1 = MyFirstClass()
    object2 = MyFirstClass()

    # check if the objects are same
    return object1 is object2 
```

Output:
```
    False
```
The output is False which means the objects instantiated from same class or different class are never same ,i.e., they are distinct.

### Adding Attributes
See the code below:
```python
    # define a Point class
    class Point:
        pass

    # instantiate two objects of class
    p1 = Point()
    p2 = Point()

    # add attributes
    p1.x = 5
    p1.y = 4
    p2.x = 3
    p2.y = 6
    print(p1.x, p1.y, sep=",") 
    print(p2.x, p2.y, sep=",") 

```
In above code we used the `.` operator to give two attributes `x` and `y` to each object, like this, `<object>.<attribute> = <value>`.

The output of the above code is as follows:
```
    5,4
    3,6
```

### Adding Methods to the Class
A **method** as discussed earlier is a behavior that is applies on the object of the class. Let's define a "reset()" method in our `Point` class which will reset the coordinates of the point.

```python
    # define a Point class
    class Point:
        # define a reset method
        def reset(self):
            # reset coordinates to 0
            self.x = 0
            self.y = 0

    # instantiate two objects of class
    p1 = Point()
    p2 = Point()

    # add attributes
    p1.x = 5
    p1.y = 4
    p2.x = 3
    p2.y = 6
    print(p1.x, p1.y, sep=",") 
    print(p2.x, p2.y, sep=",")
    print("--------")
    # call reset method on 
    # p1 object
    p1.reset()
    print(p1.x, p1.y, sep=",") 
    print(p2.x, p2.y, sep=",")

```
Output of the above code is as follows:
```
    5,4
    3,6
    --------
    0,0
    3,6
```
As we can see, the `reset()` method successfully reset the coordinates of Point object `p1`.

### What is ***self***?
- One difference between a simple function and a method is, methods have one required argument. This argument is conventionally named `self`.
- The `self` argument to a method is a reference to the object that the method is being invoked on.
- The object is an instance of a class, and `self` is sometimes called the **instance variable**.
- We can access attributes and methods of an object via this instance variable `self`.

### Adding More Arguments
To learn how to pass multiple arguments to a method, Let's add a new method to our `Point` class that will allows us to move a point to an arbitrary position, not just to the origin. We can also include a method that accepts another `Point` object as input and returns the distance between them:

```python
    class Point:
    
    # move method to move point
    # to a given position
    def move(self, x: float, y: float) -> None:
        self.x = x
        self.y = y

    def reset(self) -> None:
        self.move(0, 0)

    def calculate_distance(self, point2: "Point") -> float:
        # calculate euclidean distance between points
        return ((self.x - point2.x)**2 + (self.y - point2.y)**2)**0.5

    point1 = Point()
    point2 = Point()
    
    # initialize coordinates
    # of point1 at origin
    # point1.x == 0, point2.y == 0
    point1.reset()

    # move point2 to 
    # given position
    point2.move(x = 5, y = 0)
    
    # calculate distance of
    # point2 from point1
    print(point1.calculate_distance(point2))
```
Output of the above program is as follows:
```
    5.0
```
### Initializing Objects
Most object-oriented programming languages have the concept of a constructor, a special method that creates and initializes the object when it is created. 

Python is a little different; it has a constructor and an initializer. The constructor method, `__new__()` and the initializer method, `__init__()`.

Though, the `__new__()` method is rarely used, so lets talk about `__init__()`

Let's add an initialization function on our `Point` class that requires the user to supply `x` and `y` coordinates when the Point object is instantiated:

```python
    class Point:
        # the initializer method
        def __init__(self, x: float, y: float) -> None:
            self.move(x, y)

        # move method to move point
        # to a given position
        def move(self, x: float, y: float) -> None:
            self.x = x
            self.y = y

        def reset(self) -> None:
            self.move(0, 0)

        def calculate_distance(self, point2: "Point") -> float:
            # calculate euclidean distance between points
            return ((self.x - point2.x)**2 + (self.y - point2.y)**2)**0.5

        point1 = Point(3,4)
        print(point1.x, point1.y)
```
You can see, since we used the `__init__()` method, we passed the arguments while instantiating object. And we are forced to pass this arguments, otherwise the program throws a `not enough arguments` error

To avoid this requirement of manually passing the arguments, we can give the parameters in `__init__()` method some default values. such as:

```python
    class Point:
        # the initializer method
        def __init__(self, x: float = 0, y: float = 0) -> None:
            self.move(x, y)
```

### Writing Docstrings
When carrying out object-oriented programming, it is important to write API documentation that clearly summarizes what each object and method does.

This is done with the help of **docstrings**,
```python
    # example for docstrings
    class Point:
        """ 
        Represents a point in 2-d geometric coordinates
        """
        # the initializer method
        def __init__(self, x: float = 0, y: float = 0) -> None:
            """ 
            A method to initialize the position of a new point
            x and y coordinates are specified, if they are not, then
            point defauts to origin
            
            :param x: float x-coordinate
            :param y: float y-coordinate
            """
            self.move(x, y)
        def move(self, x: float, y: float) -> None:
            """
            Move the point to a new location in 2-d space.
            :param x: float x-coordinate
            :param y: float y-coordinate
            """
            self.x = x
            self.y = y

```
In above code, the lines of texts written in `"""` (triple quotes), is docstring.
- Make sure to write docstrings following PEP8 style guide, (the line length should not exceed more than 80 words in a single line)

- Hence, they are written in `"""` triple quotes because docstrings can span multiple lines.

### Modules and Packages
**Module** in python is nothing but a python file, any pyhton file can be called a module. We can load the class from one module to use in the other module.

- A modules name is the name of python file without ".py" suffix.
- a file named `model.py` is a module named `model`
- the `import` statement is used for importing modules or specific classes or functions from module.

Let's understand it with the following example:

This python file will act as a module for the other python file
```py
    # printhello.py
    class PrintHello:
        def print_hello_world(self):
            print("Hello World")
```

The other python file
```py
    # myprogram.py

    # importing the printhello module
    import printhello

    # accessing the class of printhello module
    # and instatiating the object of PrintHello class
    obj = printhello.PrintHello()

    # calling print_hello_world method
    # on obj
    obj.print_hello_world()
```

Output:
```
    "Hello World"
```
In the above example, we accessed the `PrintHello` class using the `printhello.<something>` notation.

We can also alternatively write the above code as follows:
The other python file
```py
    # myprogram.py

    # importing the printhello module
    from printhello import PrintHello

    # accessing the class of printhello module
    # and instatiating the object of PrintHello class
    obj = PrintHello()

    # calling print_hello_world method
    # on obj
    obj.print_hello_world()
```
In the above code we used `from...import` syntax. And it will also give the same output.

#### Creating alias to avoid confusion
Suppose, we have two modules that have a class with same name, but both have different attributes and methods. And we want to use both for different purpose in our program. In that case using **alias** can avoid confusion.

For example:
```python
    # importing PrintHello classes from
    # two different modules
    from greetings import PrintHello as PH
    from printhello import PrintHello

    # initiating object of PrintHello
    # from greetings module
    greet = PH()

    # initiating object of PrintHello
    # from printhello module
    hello = PrintHello()
```

We can also import more than one classes or methods from same module as follows:
```python
    from sklearn.metrics import accuracy_score, f1_score, precision_score
```

### Organizing Modules
As a project grows into a collection of more and more modules, we may find that we want to add another level of abstraction, some kind of nested hierarchy on our modules' levels.

We can store our modules (nothing but python files) in folders, these folders are called **packages**. 
- A package is a collection of modules. 
- The name of the package is the name of the folder
- In order to tell python that a folder is a package, simply place an empty `__init__.py` file in the folder.

Suppose we have modules related to ecommerce, such as products, database etc. We can store them in a folder named "ecommerce" and place an empty `__init__.py` file in it to make it a package.

Now we can do the following:
```py
    # main.py 
    # importing Products class from product module from ecommerce package
    from ecommerce.products import Products
```
Note: the ecommerce package is located in the same work space where our main.py is. Hence, the above code will work.

### Packages as a whole
We can import code that appears to come directly from a package, as opposed to a module inside a package. As we'll see, there's a module involved, but it has a special name, so it's hidden.

In this example, we have an ecommerce package containing two module files named "database.py" and "products.py". The database module contains a `db` variable that is accessed from a lot of places. Wouldn't it be convenient if this could be imported as `from ecommerce import db` instead of `from ecommerce.database import db`?

Remember the `__init__.py` file that defines a directory as a package? This file can contain any variable or class declarations we like, and they will be available as part of the package. In our example, if the `ecommerce/__init__.py` file contained the following line:
```python
    # the __init__.py file in ecommerce
    from .database import db
```
We could then access the `db` attribute from "main.py" or any other file using the following import:
```python
    # main.py
    from ecommerce import db
```
### Who can access my data?
Most OOP language have a concept of access control, which is related to abstraction. Some attributes and methods on an object are marked as *private* meaning only that object can access them, others are marked as *protected* which means only that class and any subclasses have access. The rest are public, meaning any other object is allowed to access them.

Python doesn't do this, in python, all methods and attributes are publically available. If we want to suggest a method should not be used publically, we can put a note in doctring of that method indicating that the method is for internal use only.

- To make an attribute or method private, conventionally we can prefx the attribute with an underscore "_". Which indicates the attribute or method is private. But nothing stops you from using it.

- To make an attribute or method strongly private, to indicate that outside objects don't access a property or method: simply prefix it with a double underscores "__". This will perform **name mangling** on an attribute or method.

**Name mangling** means that the method can still be called by outside objects if they really want to do so, but it requires extra work and is a strong indicator that you demand that your attribute remains **private**.

<a name = chapter3>
<h1> Chapter 3 - When Objects are Alike</h1>
</a>

In this chapter we will learn about:
- Basic Inheritance
- Inheriting from built-in types
- Multiple Inheritance
- Polymnorphism and duck typing

In python, all classes are sbu-classes of the special built-in class named `object`. If we don't explicitly inherit from a different class, our classes will automatically inheri from `object`.

The below two codes are same:
```python
    class MySubClass(object):
        pass
```
and
```python
    class MySubClass:
        pass
```
Now, the `object` in the parentheses after class name, is called the **superclass** or **parent class**. Superclass, or a parent class is a class that are being inherited from. In the above code `MySubClass` is the **subclass** that inherits from the `object` class. A sublclass is said to be *derived from* its parent class.

**Inheritance** is used to add functionality to an existing class.

Let's see inheritance in action with the help of following program:
```python
    class Contact:
        # define a global list of Contact object
        all_contacts: List["Contact"] = []

        def __init__(self, name: str, email: str ) -> None:
            self.name = name
            self.email = email

            # append the Contact object to the
            # all_contacts list
            Contact.all_contacts.append(self)

        def __repr__(self) -> str:
            """
            This special method returns a string
            """
            return (
                f"{self.__class__.__name__},("
                f"{self.name!r},{self.email!r}"
                f")"
            )
```
The above written code is a contact manager program that tracks the names and email addresses of several people. The `Contact` class is responsible for maintaining a global list of all contacts ever seen in a class variable, and for initializing the name and address for an individual contact.

The `all_contacts` list is a **class variable** because it is part of class definition and is shared by all instances of this class.

Let's see the output of the above written program:
```
    >>> c1 = Contact(name = "Adam", email= "adam911@example.com") 
    >>> c2 = Contact(name = "Tom", email = "thomas@example.com")  
    >>> Contact.all_contacts
    [Contact('Adam','adam911@example.com'), Contact('Tom','thomas@example.com')]
```
We got the expected output, a list with all contacts (objects of `Contact` class). 

Now let's understand the inheritance with the following code:
```python
    class Supplier(Contact):
    def order(self, order: "Order") -> None:
        print("If this were real we would send"
              f"'{order}' order to '{self.name}'"
            )
```
we created a Supplier class that acts like our `Contact` class, but has an additional order method that accepts a yet-to-be-defined `Order` object.

If we run the program, we get following output:
```
    >>> c = Contact("Somebody", "somebody@example.net")
    >>> s = Supplier("Supplier", "supplier@example.net")
    >>> print(c.name, c.email, s.name, s.email)
    Somebody somebody@example.net Supplier supplier@example.net
    >>> from pprint import pprint
    >>> pprint(c.all_contacts)
    [Contact('Dusty', 'dusty@example.com'),
    Contact('Steve', 'steve@itmaybeahack.com'),
    Contact('Somebody', 'somebody@example.net'),
    Supplier('Supplier', 'supplier@example.net')]
    >>> s.order("I need pliers")
    If this were a real system we would send 'I need pliers' order to 'Supplier' 
```
Our `Supplier` class can do everything a contact can do (including adding itself to the list of `Contact.all_contacts`) and all the special things it needs to handle as a supplier. This is inheritance.

Also, note that `Contact.all_contacts` has collected every instance of the `Contact` class as well as the subclass, `Supplier`.

### Inheriting From Built-in types
Let's add a search functionality to our Contact class by using the built-in `list`
```python
    class ContactList(list["Contact"]):
        #Notice: in parentheses we have list["Contact"]
        #We are inheriting from built-in list class      

        def search(self, name:str) -> list["Contact"]:
            matching_contacts: list["Contact"] = []
            for contact in self:
                if name in contact.name:
                    matching_contacts.append(contact)

            return matching_contacts
    
    class Contact:
        """ The Contact class is responsible for
            maintaining a global list of all contacts ever seen in a class variable,
            and for initializing the name and address for an individual contact
            """
        all_contacts = ContactList()            #this is a class variable
                                                #this is shared by all instances of this class
        
        def __init__(self, name:str, email:str ) -> None:
            self.name = name
            self.email = email
            Contact.all_contacts.append(self)
            
        def __repr__(self) -> str:
            return (
                f"{self.__class__.__name__}("
                f"{self.name!r},{self.email!r}"
                f")"
                )
```

In the above code, we added a new class `ContactList` which inherits from `list` built-in type, we wrote `list["Contact"]` to tell the *mypy* that the list is only of `Contact` type instances. We extended the built-in list by adding a `search()` method which takes the `name` as input and returns the list of contacts with that name.

Also, notice, we changed our `all_contacts` definition by replacing the `[]` which is built-in list type with our newly defined extended version of list `ContactList`.

Output:
```
    >>> c1 = Contact("John A", "johna@example.net")
    >>> c2 = Contact("John B", "johnb@sloop.net")
    >>> c3 = Contact("Jenna C", "cutty@sark.io")
    >>> [c.name for c in Contact.all_contacts.search('John')]
    ['John A', 'John B']
```

Similarly, we can extend most built-in types by inheriting from them. For another example, let's extend the functionality of `dict` for to return the longest key in the dict.
```python
    from __future__ import annotations

    #this module is for prtinting list in pep8 manner
    from pprint import pprint

    #typing module is for Type Hints
    from typing import Optional, Union

    # In this program we will create a new class
    # LongNameDict() which will Inherit built-in Dict class and add
    # new functionality to it to fetch the longest key
    class LongNameDict(dict[str, Union[str, int]]):
        def longest_key(self) -> Optional[str]:
            """In effect, max(self, key = len), but less obscure"""
            
            longest = None
            
            for key in self:
                if longest is None or len(key) > len(longest):
                    longest = key
                    
            return longest
        

    articles_read = LongNameDict()
    articles_read['monster'] = 42
    articles_read['bicycle'] = 6
    articles_read['cat'] = 7
    articles_read['YEEEEEEEEEET!'] = 90

    #this will print the longest key from articles_read dict
    print(articles_read.longest_key())

```
The above code will give the following output:
```
    'YEEEEEEEEEET!'
```
The output is `'YEEEEEEEEEET!'` because its the longest key in our dictionary.

Also, notice that the hint for the class narrowed the generic `dict` to a more specific `dict[str, Union[str, int]]` which tells, the keys are of type `str` and the values can be of type `str` or `int`.

The result will be a `str` , or possibly `None` . That's why the return type of the `longest_key` method is described as `Optional[str]`.

### Overiding and Super
We saw, how inheritance can be used to *add* new behaviors, now let's see how we can use it to *change* the behavior of the parent class. 

Our `Contact` class only allows us to keep only names and email addresses, what if we want to add a phone number for our close friends, there is no such functionality in our `Contact` class so lets add it.

We can do this by setting a `phone` attribute on the contact after it is constructed. But to make this variable available on intialization we need to override our `__init__()` method.

Let's see the code below for better understanding:
```python
    #This program implements the use of "super()" method 
    from pprint import pprint

    class Contact:
        all_contacts = []
        
        def __init__(self, name:str, email:str) -> None:
            self.name = name
            self.email = email
            Contact.all_contacts.append(self)
            
        def __repr__(self) -> str:
            return (
                f"{self.__class__.__name__}("
                f"{self.name!r},{self.email!r}"
                f")"
                )
            
    #We want to add Phone number to the contact details for our Friends

    class Friends(Contact):
        """this class inherits the Contact class
        and also changes its Behavior
        
        *this class does not use super() hence we had to
        write the code twice for attributes*
        
        """
        
        def __init__(self, name:str, email:str, phone:str) -> None:
            self.name = name
            self.email = email
            self.phone = phone
    
    c1 = Contact(name="Dustin", email="dustiniscool@gmail.com")
    f1 = Friends(name="Steve", email="steveharington@gmail.com", phone="5534-4422")
    print(Contact.all_contacts)
    
```
In the above code, we defined a new class `Friends` which is inheriting from our `Contact` class, we are changing behavior of `__init__()` method to accept another attribute `phone`. Let's see the output of this:

```
    [Contact('Dustin','dustiniscool@gmail.com')]
```
Notice, that object of `Friends` was not added to `all_contacts`, it is because, the  `__init__()` of `Friends` class does not have a `Contact.all_contact.append(self)`.

Now, lets see how using `super()` method solves this issue:
```python
    class Friends(Contact):
            """this class inherits the Contact class
            and also changes its Behavior
            
            *this class uses super() hence we did not need
            to write the code twice for attributes*
            
            """
            
            def __init__(self, name:str, email:str, phone:str) -> None:

                # we are using super() method
                # to use the __init__ method of Superclass "Contact"
                super().__init__(name, email)
                self.phone = phone
                
                #NOTICE: we haven't still touched the __repr__ method of 
                # our parent class hence THERE WILL BE CONCEQUENCES
                # **phone number wont be displayed**
                
        c1 = Contact(name="Dustin", email="dustiniscool@gmail.com")
        f1 = Friends(name="Dustin's Friend", email="dustinismyfriend@gmail.com", phone="5555-7898")
        print(Contact.all_contacts)
```
Output:
```
    [Contact('Dustin','dustiniscool@gmail.com'), Friends("Dustin's Friend",'dustinismyfriend@gmail.com')]
```
We get this output. Now, we can see the object of `Friends` class in our `all_contacts` list. It worked because, we used the `super()` method, which inherited the `__init__()` method of Contact class which has `Contact.all_contact.append(self)`.

But still, the output doesn't seem write, seems like something is missing...Oh yeah! The phone number is still not visible. Well that is because, we did not change the behavior of the `__repr__()` method which is responsible for displaying our contact list. 

Let's change the behavior of `__repr__()` method so it can show us the contact number of our friends:
```python 
    class Friends(Contact):
        """this class inherits the Contact class
        and also changes its Behavior
        
        *this class uses super() hence we did not need
        to write the code twice for attributes*
        
        """
        
        def __init__(self, name:str, email:str, phone:str) -> None:
            super().__init__(name, email)
            self.phone = phone
            
        def __repr__(self) ->str:
            # here we are changing the behavior of
            # __repr__ method of Contact class
            # to make it print phone number
            return super().__repr__() + (f", {self.phone!r}")
            
    c1 = Contact(name="Dustin", email="dustismyfriend@gmail.com")
    f1 = Friends(name="Steve", email="dustinismyfriend@gmail.com", phone="6969-42069")

    print(Contact.all_contacts)
```
Now, let's check the output:

```
    [Contact('Dustin','dustiniscool@gmail.com'), Friends('Steve','dustinismyfriend@gmail.com'), '6969-42069']
```
Finally, we have the expected output. We just changed the behavior of the `__repr__()` method of superclass that is `Contact` to concatenate the phone number to the output of `__repr__()` mehod of superclass.

<a name = chapter4>
<h1> Chapter 4 - Expecting the Unexpected</h1>
</a>

This chapter is about python exceptions and how to handle them.
**Exceptions** are special error objects raised when a normal response is impossible. We will learn the following things in this chapter:
- How to cause an exception to occur
- How to recover when an exception has occurred (Handling Exception)
- How to handle different exception types in different ways (Ways to handle)
- Cleaning up when an exception has occurred (`finally` syntax)
- Creating new types of exceptions.
- Using the exception syntax for flow control (makes things easier)

### How to cause an exception to occur?
There are various types of exceptions, such as:
- **SyntaxError**: When we write wrong syntax.
- **TypeError**: Concatenating **int** type to a **list** type.
- **IndexError**: When **list** runs out of index.
- **ZeroDivisionError**: Division by zero.
- **AttributeError**: When an doesn't have the given attribute.

You can get all of these exceptions by running these functions, one-by-one:
```py
    # Types of Exceptions:

    # SyntaxError
    def syntaxError():
        print "2"
        # pass

    # ZeroDivisionError
    def zeroDivision():
        print(2/0)

    # IndexError
    def indexError():
        arr = [1,2,3,4,5]
        print(arr[5])

    # TypeError
    def typeError():
        arr = [1,2]
        print(arr + 3)

    # AttributeError
    def attributeError():
        my_string = "Hello Abrenion!"
        print(my_string.reverse())
```

### Raising Exceptions
- We raise exceptions when we want to inform the client or user of our program about what they should do and what they shouldn't.
- We raise exceptions with the help of `raise` keyword and an exception object like
```py
    raise TypeError("Wrong type only int type is allowed")
```
Let's understand this by an example of a list that only accepts odd integers value:
```python
    # Creating a list that only accepts odd integers
    from typing import List
    # we are inheriting from the List class
    # and changing it to only accept
    # odd integers
    class OddList(List["int"]):
        def append(self, value: int) -> None:
            if not isinstance(value, int):
                raise TypeError("Only int type can be appended")

            if value %2==0:
                raise TypeError("Only odd integers can be appended")

            super().append(value)

    odd_list = OddList()
    odd_list.append(5)
    odd_list.append(8)
```
#### Effects of Exception

Code after the exception is not executed.
```py
    # Effect of an Exception
    # The remaining program doesn't execute after Exception is caught.
    from typing import NoReturn

    def never_return() -> NoReturn:
        print(" I am going to raise an Exception")

        raise Exception("Oops! I am an exception, I got raised.")
        print(" We are code after the exception occured :(")
        print(" We cannot be executed :'(")

    never_return()
```

### Handling Exceptions
Here, we will learn how to recover from an exception, if it occurs. For handling exceptions, just simply wrap the code that is prone to exception in a `try...except` clause.

See this example:
```py
    # The try...except clause, handles the exception if caught
    from typing import NoReturn, Union

    def never_return() -> NoReturn:
        print("I am going to raise an Exception")

        raise Exception("Oops! I am an exception, I got raised.")
        print(" We are code after the exception occured :(")
        print(" We cannot be executed :'(")

    def exception_handler():
        try:
            print("We are in try block")
            print("We try this code, if exception is caught! 'except' will handle it")
            never_return()

        except Exception as ex:
            print(f"I caught an exception: {ex!r}")
        print("I am executed because, exception was handled")
```
Output of the above code will be:
```
    We are in try block
    We try this code, if exception is caught! 'except' will handle it
    I am going to raise an Exception
    I caught an exception: Exception('Oops! I am an exception, I got raised.')
    I am executed because, exception was handled
```
Explanation: we get in try block, we try some code which is prone to exception the `never_return()` function, which raises an exception. The `except` block catches the exception and tell's what was the exception. And the program continues to execute because the exception was handled.

### Handling Multiple Exceptions
We can handle multiple exceptions at once too. See the following example:
```py
    # Handling Multiple Exceptions
    def funny_division(divisor: int) -> Union[str, float]:
    try:
    if divisor == 13:
        raise ValueError("13 is an unlucky number")
        return 100 / divisor
    except (ZeroDivisionError, TypeError):
        return "Enter a number other than zero"
```
To handle the multiple exceptions, we write the name of exception classes after the `except` keyword in parantheses like `except (ZeroDivisionError, TypeError)`. But in this code we are handling both ZeroDivisionError & TypeError exceptions in same way.

#### Handling each exceptions differently
```py
    def funniest_division(divisor: int) -> Union[str, float]:
        try:
            if divider == 13:
                raise ValueError("13 is an unlucky number")
                return 100 / divider
            except ZeroDivisionError:
                return "Enter a number other than zero"
            except TypeError:
                return "Enter a numerical value"
            except ValueError:
                print("No, No, not 13!")
                raise
```
The above code handles each exception in different way by returning different messages.

### `finally` and `else`
- `else`: The code in `else` executed when no exception occurs.
- `finally`: The code in `finally` always executes regardless of any exception. The `finally` clause generally works along with **context manager**, for example: When we want to close the file if the exception has occured. **we must always close the file that we open**.

The following example iterates through a number of exception classes, raising an instance of each:
```py
    some_exceptions = [ValueError, TypeError, IndexError, None]
    for choice in some_exceptions:
        try:
            print(f"\nRaising {choice}")
            if choice:
                raise choice("An error")
            else:
                print("no exception raised")
        except ValueError:
            print("Caught a ValueError")
        except TypeError:
            print("Caught a TypeError")
        except Exception as e:
            print(f"Caught some other error: {e.__class__.__name__}")
        else:
            print("This code called if there is no exception")
        finally:
            print("This cleanup code is always called")
```
We get following output:
```
    Raising <class 'ValueError'>
    Caught a ValueError
    This cleanup code is always called
    Raising <class 'TypeError'>
    Caught a TypeError
    This cleanup code is always called
    Raising <class 'IndexError'>
    Caught some other error: IndexError
    This cleanup code is always called
    Raising None
    no exception raised
    This code called if there is no exception
    This cleanup code is always called
```
We can see the `finally` clause is executed in each iteration, the `else` clause was executed when there was no exception.

The `finally` is specially used for following tasks when our code has finished running (even if an exception has occurred).
- Cleaning up an open database connection
- Closing an open file
- Sending a closing handshake over the network

### The Exception Hierarchy
- "Most exceptions are subclasses of `Exception` class, but not all."
- The `Exception` class is itself a subclass of the `BaseException` class. 

There are two built-in exception classes, the `SystemExit` and `KeyboardInterrupt`, that derive directly from `BaseException` class, all other are derived from `Eception` class which itself is derived from `BaseException` class. 

The below diagram makes everything clear.
![Alt text](./images/exception_hierarchy.jpeg?web=raw "exception hierarchy")

### Defining Our Own Exceptions
#### Why do I need to define my own exception?
Utility of custom exceptions truly comes to light when creating a framework, library, or API that is intended for access by other programmers. In that case, be careful to ensure your code is raising exceptions that make sense to the client programmer. Here are some criteria:
- They should clearly describe what went on. The `KeyError` exception, for example, provides the key that could not be found.
- The client programmer should easily see how to fix the error (if it reflects a bug in their code) or handle the exception (if it's a situation they need to be made aware of).
- The handling should be distinct from other exceptions. If the handling is the same as an existing exception, reusing the existing exception is best.

#### When defining execptionns keep following things in mind:
- Know when you want to define your own exception.
- Do not define an exception if it's going to handle exactly like the built-in exceptions. For Example: there is no point in defining an exception that's handled exactly like `ValueError` when can simply use `ValueError`.
- Do not use `BaseException` class for creating your own exceptions.
- Also do not use bare `except` (except without "exception class" is by default `BaseException`).
- Use `Exception` class instead.

#### Why can I not derive from `BaseException`directly?
Because, special classes like `SystemExit` and `KeyboardInterrupt` are derived directly from `BaseException` class. The `SystemExit` exception is raised whenever the program exits naturally, typically because we called the sys.exit() function somewhere in our code (for example, when the user selected an exit menu item, clicked the Close button on a window. This exception is designed to allow us to clean up code before the program ultimately exits.

And we do not want to catch this exception, it can shut down your running program even before finishing. Hence, it is adviced to use the `Exception` class which has no such subclasses.

#### Why can I not use bare `except`?
When we use the `except:` clause without specifying any type of exception, it will catch all subclasses of `BaseException`; which is to say, it will catch all exceptions, including the two special ones. Since, we almost always want these to get special treatment, it is unwise to use the `except:` statement without arguments. If you want to catch all exceptions (other than `SystemExit` and `KeyboardInterrupt` ), always explicitly catch Exception. 

### Example for creating own exception
```py
    # Creating own exceptions is very trivial
    # just make sure to use Exception as super class
    # do not use BaseException class, you know why!

    class InvalidWithdrawal(ValueError):
        # New exception class that is inherited from
        # ValueError exception class
        pass

    raise InvalidWithdrawal("You don't have 50 Rs. in your account!")
```
This will give the following output:
```
    Traceback (most recent call last):
    File "<input>", line 1, in <module>
    InvalidWithdrawal: You don't have 50 Rs. in your account!
```

- We can pass an arbitrary number of arguments into the exception.
- Often a string message is used as an argument.
- Any object that might be useful in later exception handler can be stored.
- The `__init__` method of `Exception` class is designed to accept any arguments.
- The `__init__` method of `Exception` can store the arguments as a tuple in an attribute named `args`. This makes exceptions easier to define without needing to override the `__init__()` method.

#### Making our `InvalidWithdrawal` exception better
Here's a an updated version of the above exception whose initializer accepts the current balance and the amount the user wants to withdraw:

```py
    from decimal import Decimal
    class InvalidWithdrawal(ValueError):
        def __init__(self, balance: Decimal, amount: Decimal) -> None:
            super().__init__(f"account doesn't have {amount} Rs.") 
            self.amount = amount 
            self.balance = balance 
        
        def overage(self) -> Decimal:
            return self.amount - self.balance
```
This will give following output:
```
    >>> raise InvalidWithdrawal(Decimal('25.00'), Decimal('50.00'))
    Traceback (most recent call last):
    ...
    InvalidWithdrawal: account doesn't have 50.00 Rs.
```
And we can handle this exception as follows:

```python
    try: 
        balance = Decimal('25.00')
        raise InvalidWithdrawal(balance, Decimal('50.00'))

    except InvalidWithdrawal as ex: 
        print("I'm sorry, but your withdrawal is "\
                "more than your balance by "\
                f"{ex.overage()} Rs.") 
```

### Using Exception Handling for Flow Control
One of the most cool application of exception handling is flow control. We can use exception handling like `if...else...`.

The code below shows how they are identical:
```py
    def divide_with_exception(dividend: int, divisor: int) -> None:
        try:
            print(f"{dividend / divisor=}")
        except ZeroDivisionError:
            print("You can't divide by zero")

    def divide_with_if(dividend: int, divisor: int) -> None:
        if divisor == 0:
            print("You can't divide by zero")
        else:
            print(f"{dividend / divisor=}")
```
In the above code, we defined two functions, one that uses Exception Handling and the other which uses if...else... clauses. The output of both function is gonna be same.

In this example, the test for a valid division is relatively simple-looking (`divisor == 0`). In some cases, it can be rather complex. In some cases, it may involve computing intermediate results. In the worst cases, the test for "will this work?" involves using a number of other methods of a class to –in effect – dry-run the operation to see if there would be an error along the way.

**"It's Easier to Ask Forgiveness Than Permission"**
This is the principle on which flow controling with "Exception Handling" works. The point of it is to execute the code and then deal with anything that goes wrong.
>It is wise to use exceptions for exceptional circumstances, even if those circumstances are only a little bit exceptional.

### Consider this Example
Imagine an inventory application for a company that sells widgets and gadgets. When a customer makes a purchase, the item can either be available, in which case the item is removed from inventory and the number of items left is returned, or it might be out of stock. Now, being out of stock is a perfectly normal thing to happen in an inventory application. It is certainly not an exceptional circumstance. But what do we return if it's out of stock? A string saying "out of stock"? A negative number? In both cases, the calling method would have to check whether the return value is a positive integer or
something else, to determine if it is out of stock. That seems a bit messy, especially if we forget to do it somewhere in our code.

Instead, we can raise an OutOfStock exception and use the try statement to direct program flow control. Make sense?
