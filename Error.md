# Errors and exception handling
## C#
A try block is used by C# programmers to partition code that might be affected by an exception. Associated catch blocks are used to handle any resulting exceptions. A finally block contains code that is run regardless of whether or not an exception is thrown in the try block, such as releasing resources that are allocated in the try block. A try block requires one or more associated catch blocks, or a finally block, or both.
```
try
{
    // Code to try goes here.
}
catch (SomeSpecificException ex)
{
    // Code to handle the exception goes here - like 
“throw new System.ArgumentOutOfRangeException("Parameter index is out of range.", e);”
}
finally
{
    // Code to execute after the try (and possibly catch) blocks 
    // goes here.
} 
```


