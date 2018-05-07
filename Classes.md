# Classes

## Java classes
* A class is nothing but a blueprint or a template for creating different objects which defines its properties and behaviors. Java class objects exhibit the properties and behaviors defined by its class. A class can contain fields and methods to describe the behavior of an object.
* Every class has a constructor. Each time a new object is created, at least one constructor will be invoked.
* A class can have more than one constructor.
* There is no direct equivalent of a destructor in java.
* For classes that need to explicitly tidy up, the convention is to define a close method and use finalize only for sanity checking

## C# 
* Use class keyword to define a class.
```
public  class  Customer  
{  
// Fields, properties, methods and events go here...  
}
```
* The new keyword is used to create a new instance.
```
Customer object1 = new Customer();
```
* Constructing/initializing:
```
   // Constructor that takes no arguments.
    public Person()
    {
        name = "unknown";
    }

    // Constructor that takes one argument.
    public Person(string nm)
    {
        name = nm;
    }
```
* C# also implements destructing/de-initializing.  Finalizers are used to destruct instances of classes.  Finalizers cannot be defined in structs, are only used with classes, a class can only have one finalizer, finalizers cannot be inherited or overloaded, finalizers cannot be called (they are invoked automatically), and a finalizer does not take modifiers or have parameters.

For example, the following is a declaration of a finalizer for the Car class.
```
class Car
{
    ~Car()  // destructor
    {
        // cleanup statements...
    }
}
```
