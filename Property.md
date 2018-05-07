# Properties



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
