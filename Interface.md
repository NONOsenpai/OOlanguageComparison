# Interfaces / protocols

## Java 
* very similar to c#
* Supports interfaces
* a class or interface can implement numberous interfaces

example interface
```java 
interface myinterface {  
...
}  
```
example class implementing an interface
```java
class MyClass implements myinterface{  
...
}  
```

## C#
* C# supports interfaces.  By using interfaces, you can include behavior from multiple sources in a class.  It is used as a workaround because C# doesn't support multiple inheritance of classes. It uses the ```interface``` keyword.
```
interface IEquatable<T>
{
    bool Equals(T obj);
}
```
