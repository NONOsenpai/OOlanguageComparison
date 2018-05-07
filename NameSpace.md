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
  
## Python
* Name spaces are implemented in Python by using a Dictionary -- Key to value lookup. Some examples of a Python name space are global names of a module, local names a function, built-in names such as abs() and cmp(). The name spaces exist only in the scope they are created.
