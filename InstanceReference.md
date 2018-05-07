# Instance reference name in data type (class) 

## Java
* In Java we use the 'this' keyword to refer to the current instance of the class.


## C#
* C# uses the 'this' keyword for the instance reference name in the class. 
```
public Employee(string name, string alias)
{
    // Use this to qualify the fields, name and alias:
    this.name = name;
    this.alias = alias;
}
```
