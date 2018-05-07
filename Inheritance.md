# Inheritance / extension

## C#
* C# and .NET support single inheritance only. However, inheritance is transitive, which allows you to define an inheritance hierarchy for a set of types.  
```
public class A 
{
   private int value = 10;

   public class B : A
   {
       public int GetValue()
       {
           return this.value;
       }     
   }
}
```

* Extension methods enable you to "add" methods to existing types without creating a new derived type, recompiling, or otherwise modifying the original type. Extension methods are a special kind of static method, but they are called as if they were instance methods on the extended type. For client code written in C#, F# and Visual Basic, there is no apparent difference between calling an extension method and the methods that are actually defined in a type.
