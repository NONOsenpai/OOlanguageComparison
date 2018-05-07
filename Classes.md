# Classes

## Java classes
* A class is nothing but a blueprint or a template for creating different objects which defines its properties and behaviors. Java class objects exhibit the properties and behaviors defined by its class. A class can contain fields and methods to describe the behavior of an object.
* Every class has a constructor. Each time a new object is created, at least one constructor will be invoked.
* A class can have more than one constructor.
* There is no direct equivalent of a destructor in java.
* For classes that need to explicitly tidy up, the convention is to define a close method and use finalize only for sanity checking

## Python 
* Classes in Python are created by using the 'class' keyword, the class name, and then a colon before inserting everything needed in the class.
For example:
```
class Car:
  def drive(self):
    print("This car is being driven.")
```
Creates a car class with the drive function.

To instantiate a new instance of the class, the user would create a variable and assign it to the class;:
```
x = Car()
```
This calls the '__init__()' function on the class. This function can be extended if the creator wanted the instance to do additional features, such as assign variable or run additional functions, in the instantiation period.
To de-initialize a class in Python the developer can use the close function on an object. This will delete the reference to the object. If the developer wanted to reuse the object in a pool, the developer could modify the close function to just erase the data inside. 
