# Singleton
## C# 
Implementation of Singleton in C# looks like the following:
- Common, non-treadsafe way:

```
public sealed class Singleton
{
    private static Singleton instance=null;
    private Singleton(){}
    public static Singleton Instance {
        get
        {
            if (instance==null)
            {
                instance = new Singleton();
            }
            return instance;
        }
    }
}
```
- To make it thread safe: 
```
public sealed class Singleton
{
    private static Singleton instance = null;
    private static readonly object padlock = new object();
    Singleton(){}
    public static Singleton Instance
    {
        get
        {
            lock (padlock)
            {
                if (instance == null)
                {
                    instance = new Singleton();
                }
                return instance;
            }
        }
    }
}
```
- The singleton instance can be lazily instantiated:
```
public sealed class Singleton
{
    private static readonly Lazy<Singleton> lazy =
        new Lazy<Singleton>(() => new Singleton());
    
    public static Singleton Instance { get { return lazy.Value; } }

    private Singleton() { }
}
```
- another way to lazy instantiate: 
```
public sealed class Singleton
{
    private Singleton(){ }

    public static Singleton Instance { get { return Nested.instance; } }
        
    private class Nested
    {
        // Explicit static constructor to tell C# compiler
        // not to mark type as beforefieldinit
        static Nested(){ }
        internal static readonly Singleton instance = new Singleton();
    }
}

```

