# Instance reference name in data type (class) 

## Java
In Java however their value types are called primitive types. These primitive types are: boolean, byte, char, short, int, long, float and double.
* Value Type
Following are some code examples of Java primitive types.
```
int a = 2;
char b = 'b';
boolean f = false;
double d = 3.40;
```
* Reference Type
Assume we have a class called Ball. The following code will show example of a reference type using class Ball. It is important to note that Java does not pass reference types to functions by reference. They are passed by value.
```
Ball b = new Ball();

Ball a = b;
// Ball a and b will reference the same object
```
* Reference Passed By Value
```
public void tricky(Point arg1, Point arg2)
{
  arg1.x = 100;
  arg1.y = 100;
  Point temp = arg1;
  arg1 = arg2;
  arg2 = temp;
}
public static void main(String [] args)
{
  Point pnt1 = new Point(0,0);
  Point pnt2 = new Point(0,0);
  System.out.println("X: " + pnt1.x + " Y: " +pnt1.y); 
  System.out.println("X: " + pnt2.x + " Y: " +pnt2.y);
  System.out.println(" ");
  tricky(pnt1,pnt2);
  System.out.println("X: " + pnt1.x + " Y:" + pnt1.y); 
  System.out.println("X: " + pnt2.x + " Y: " +pnt2.y);  
}
/* Print out would be:
   X: 0 Y: 0
   X: 0 Y: 0
   X: 100 Y: 100
   X: 0 Y: 0
*/
```


## Python
* Python uses the 'self' keyword to reference the name of the data type. Python is special in that self doesn't need to be added to the signature as each object recognizes the current instance as 'self'
