# Name Spaces

## JAVA
* Java doesn't use this term but there is similar concept which is used Java which is called packages.
* Packages are used to organize files or public types to avoid 
  type conflicts. 
* Package constructs can be mapped to a file system.
* implement:
  To declare a class that implements an interface, you include an implements clause in the class declaration. Your class can implement more than one interface, so the implements keyword is followed by a comma-separated list of the interfaces implemented by the class. By convention, the implements clause follows the extends clause, if there is one.
* Used:
  While creating a package, you should choose a name for the package and include a package statement along with that name at the top of every source file that contains the classes, interfaces, enumerations, and annotation types that you want to include in the package.
  The package statement should be the first line in the source file. There can be only one package statement in each source file, and it applies to all types in the file.
  If a package statement is not used then the class, interfaces, enumerations, and annotation types will be placed in the current default package.
  To compile the Java programs with package statements, you have to use -d option as shown below.
      javac -d Destination_folder file_name.java
  Then a folder with the given package name is created in the specified destination, and the compiled class files will be placed in that folder.
  
## C#
* .NET Framework uses namespaces to organize its many classes. The ```namespace``` keyword is used to declare a scope. The ability to create scopes within your project helps organize code and lets you create globally-unique types.  Declaring your own namespaces can help you control the scope of class and method names.
```
namespace  SampleNamespace  
{  
	class  SampleClass  
	{  
		public  void  SampleMethod()  
		{  
			System.Console.WriteLine(  
			"SampleMethod inside SampleNamespace");  
		}  
	}  
}
```
