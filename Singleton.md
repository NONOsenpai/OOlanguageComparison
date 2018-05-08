# Singleton

## Java
* The easiest implementation consists of a private constructor and a field to hold its result, and a static accessor method with a name like getInstance().
```java
// File Name: Singleton.java
public class Singleton {

   private static Singleton singleton = new Singleton( );

   /* A private Constructor prevents any other
    * class from instantiating.
    */
   private Singleton() { }

   /* Static 'instance' method */
   public static Singleton getInstance( ) {
      return singleton;
   }

   /* Other methods protected by singleton-ness */
   protected static void demoMethod( ) {
      System.out.println("demoMethod for singleton");
   }
}
```
* a classic Singleton design pattern:
```java
public class ClassicSingleton {

   private static ClassicSingleton instance = null;
   private ClassicSingleton() {
      // Exists only to defeat instantiation.
   }

   public static ClassicSingleton getInstance() {
      if(instance == null) {
         instance = new ClassicSingleton();
      }
      return instance;
   }
}
```
* There are three ways through which we can achieve thread safety.
*   1. Create the instance variable at the time of class loading.
*   2. Synchronize the getInstance() method.
*   3. Use synchronized block inside the if loop.
```java
package com.journaldev.designpatterns;

public class ASingleton{

	private static ASingleton instance= null;
	private static Object mutex= new Object();
	private ASingleton(){
	}

	public static ASingleton getInstance(){
		if(instance==null){
			synchronized (mutex){
				if(instance==null) instance= new ASingleton();
			}
		}
		return instance;
	}

}
```

## C# 
* Implementation of Singleton in C# looks like the following:
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
* To make it thread safe: 
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
* The singleton instance can be lazily instantiated:
```
public sealed class Singleton
{
    private static readonly Lazy<Singleton> lazy =
        new Lazy<Singleton>(() => new Singleton());
    
    public static Singleton Instance { get { return lazy.Value; } }

    private Singleton() { }
}
```
* another way to lazy instantiate: 
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

