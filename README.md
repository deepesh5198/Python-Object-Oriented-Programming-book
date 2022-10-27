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
- In order to tell python that a folder is a package, simply place an empty **__init__.py** file in the folder.

Suppose we have modules related to ecommerce, such as products, database etc. We can store them in a folder named "ecommerce" and place an empty **__init__.py** file in it to make it a package.

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

Remember the __init__.py file that defines a directory as a package? This file can contain any variable or class declarations we like, and they will be available as part of the package. In our example, if the ecommerce/__init__.py file contained the following line:
```python
    # the __init__.py file in ecommerce
    from .database import db
```
We could then access the `db` attribute from "main.py" or any other file using the following import:
```python
    from ecommerce import db
```
