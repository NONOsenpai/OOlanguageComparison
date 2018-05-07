# Comparisons of References and Values
## C# 
"Equals" and "==" will compare by reference by default if they're not overriden / overloaded in a subclass. ReferenceEquals will always compare by reference.  ```String.Compare``` a compares two specified String objects and returns an integer that indicates their relative position in the sort order.  ```String.CompareTo``` compares this instance with a specified object or String and returns an integer that indicates whether this instance precedes, follows, or appears in the same position in the sort order as the specified object or String.

Strings overload == to implement value equality; also, since they're immutable, C# will generally reuse the same instance for the same literal string. 
```
C# program that compares strings for equality

using System;

class Program
{
    static void Main()
    {
        string a = "a" + 1;
        string b = "a" + 1;

        // 1
        // Compare a to b using instance method on a.
        if (a.Equals(b))
        {
            Console.WriteLine("a.Equals(b) = true");
        }

        // 2
        // Compare b to a using instance method on b.
        if (b.Equals(a))
        {
            Console.WriteLine("b.Equals(a) = true");
        }

        // 3
        // Compare a to b with op_Equality
        if (a == b)
        {
            Console.WriteLine("a == b = true");
        }

        // 4
        // Compare with string.Compare; this returns zero if they are equal
        if (string.Compare(a, b) == 0)
        {
            Console.WriteLine("string.Compare(a, b) = 0");
        }

        // 5
        // Compare with string.CompareOrdinal
        // This returns zero if the char numeric values are equal
        if (string.CompareOrdinal(a, b) == 0)
        {
            Console.WriteLine("string.CompareOrdinal(a, b) = 0");
        }

        // 6
        // Compare with instance Compare method
        if (a.CompareTo(b) == 0)
        {
            Console.WriteLine("a.CompareTo(b) = 0");
        }
    }
}

Output

a.Equals(b) = true
b.Equals(a) = true
a == b = true
string.Compare(a, b) = 0
string.CompareOrdinal(a, b) = 0
a.CompareTo(b) = 0
```
