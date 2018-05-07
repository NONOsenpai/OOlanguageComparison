# Properties

## Java
### Setters and Getters
```java
public class Student {
    private String name;

    public String getName() {
        return name;
    }

    
    public void setName(String newName) {
        name = newName;
    }
}
```
### Backing Variables
```java
private Integer age;

public void setAge(int age){
   this.age = age;
}

public void getAge(){
   return this.age;
}
```
### Computed Properties
```java
public class Cabbage {
    final String typeOfFood = "cabbage";
    String typeOfCabbage;
    double weight;
    private String fullTypeName;
    
    public Cabbage(double weight, String typeOfCabbage){
        this.weight = weight;
        this.typeOfCabbage = typeOfCabbage;
        fullTypeName = getFullTypeName();
    }
    
    public String getFullTypeName(){
        return typeOfCabbage + " " + typeOfFood;
    }
    public void setFullTypeName(String typeOfCabbage){
        this.typeOfCabbage = typeOfCabbage;
        fullTypeName = getFullTypeName();
    }
}

public class Strawberry {
    final String typeOfFood = "strawberry";
    String typeOfStrawberry;
    double weight;
    private String fullTypeName;
    
    public Strawberry(double weight, String typeOfStrawberry, String fullTypeName){
        this.weight = weight;
        this.typeOfStrawberry = typeOfStrawberry;
        this.fullTypeName = fullTypeName;
    }
    
    public String getFullTypeName(){
        return fullTypeName;
    }
    public void setFullTypeName(String typeOfStrawberry){
        this.typeOfStrawberry = typeOfStrawberry;
        fullTypeName = typeOfStrawberry + " " + typeOfFood;
    }
}

public static void main(String[] args) {
    String cName = "january king";
    String sFName = "strawberry";
    String sTName = "fragaria vesca";
    String sFTName = sFName + " " + sTName;
    Cabbage cabbage = new Cabbage(2, "january king");
    Strawberry strawb = new Strawberry(0.1, sTName, sFTName);


    System.out.println("Cabbage computed properties: get:");
    System.out.println("\tCabbage: food type: " + cabbage.typeOfFood);
    System.out.println("\tCabbage: cababge type: " + cabbage.typeOfCabbage);
    System.out.println("\tCabbage: full type: " + cabbage.getFullTypeName());
    System.out.println("Cabbage computed properties: set:");
    System.out.println("\tCabbage: food type: " + cabbage.typeOfFood);
    cabbage.setFullTypeName("bok choy");
    System.out.println("\tCabbage: cababge type: " + cabbage.typeOfCabbage);
    System.out.println("\tCabbage: full type: " + cabbage.getFullTypeName());
    // computed properties are private properties
    //      that are 'set' and 'gotten'('get')
    //      through methods
    // this is a means of protecting the roperty
    //      itself, so no direct access is
    //      allowed (aka. cabbage.fullTypeName)


    System.out.println("\nStrawberry computed properties: set in constructor:");
    System.out.println("\tStrawberry: food type: " + strawb.typeOfFood);
    System.out.println("\tStrawberry: Strawberry type: " + strawb.typeOfStrawberry);
    System.out.println("\tStrawberry: full type: " + strawb.getFullTypeName());
    System.out.println("Strawberry computed properties: set:");
    System.out.println("\tStrawberry: food type: " + strawb.typeOfFood);
    strawb.setFullTypeName("fragaria x ananassa");
    System.out.println("\tStrawberry: Strawberry type: " + strawb.typeOfStrawberry);
    System.out.println("\tStrawberry: full type: " + strawb.getFullTypeName());
    // note: in this case, it's probably better to 
    //      set and get through the functions alone
    //      instead of the constructor
}
```

## C#
### Getters and setters

Properties enable a class to expose a public way of getting and setting values, while hiding implementation or verification code.  A get property accessor is used to return the property value, and a set accessor is used to assign a new value. These accessors can have different access levels.

The value keyword is used to define the value being assigned by the set accessor:
```
private string _s;

public string YourProperty
{
get { return _s; }
set { _s = value; }
}
```
Properties that do not implement a set accessor are read only:
```
public string YourProperty
{
get { return "somestring..."; }
}
```
For simple properties that require no custom accessor code, you can use auto-implemented properties.  Getters and Setters are built in to auto-implemented properties in C.
```
public class ClassName
{
    public string YourProperty { get; set; }
}
 ```
### Backing variables
C# has backing variables built in/ hidden, but they can be managed manually if needed.

Pre .NET 3.5:
```
private string _something; 
public string Something 
{ 
	get { 
		return _something; 
		} 
	set { 
		_something = value; 
		} 
}
```
Or more recent: ```public string Something { get; set; }```

### Computed properties
C# allows computed properties. An example:
```
class TimePeriod
{
   private double seconds;

   public double Hours
   {
       get { return seconds / 3600; }
       set { 
          if (value < 0 || value > 24)
             throw new ArgumentOutOfRangeException(
                   $"{nameof(value)} must be between 0 and 24.");

          seconds = value * 3600; 
       }
   }
}
```
