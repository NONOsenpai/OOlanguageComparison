# Interfaces / protocols
 
## C#
* C# supports interfaces.  By using interfaces, you can include behavior from multiple sources in a class.  It is used as a workaround because C# doesn't support multiple inheritance of classes. It uses the ```interface``` keyword.
```
interface IEquatable<T>
{
    bool Equals(T obj);
}
```
