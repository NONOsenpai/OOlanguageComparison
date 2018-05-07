# Lambda
## C#
C# implements Lambda expressions,  By using lambda expressions, you can write local functions that can be passed as arguments or returned as the value of function calls. Lambda expressions are particularly helpful for writing LINQ query expressions.
C# uses lambda expressions that look like: 

	(input-parameters) => expression
	
and uses delegates instead of functions as types. 
```
public delegate void DoSomethingDelegate(Object param1, Object param2);

delegate int del(int i);  
static void Main(string[] args)  
{  
    del myDelegate = x => x * x;  
    int j = myDelegate(5); //j = 25  
}  
```


