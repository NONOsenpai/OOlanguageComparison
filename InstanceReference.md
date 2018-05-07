# Instance reference name in data type (class) 

## JAVA
 * Primitive data types in Java
  Type	Description	Default	Size	Example Literals
  boolean	true or false	false	1 bit	true, false
  byte	twos complement integer	0	8 bits	(none)
  char	Unicode character	\u0000	16 bits	'a', '\u0041', '\101', '\\', '\'', '\n', 'ß'
  short	twos complement integer	0	16 bits	(none)
  int	twos complement integer	0	32 bits	-2, -1, 0, 1, 2
  long	twos complement integer	0	64 bits	-2L, -1L, 0L, 1L, 2L
  float	IEEE 754 floating point	0.0	32 bits	1.23e100f, -1.23e-100f, .3f, 3.14F
  double	IEEE 754 floating point	0.0	64 bits	1.23456e300d, -1.23456e-300d, 1e1d


* Range of numeric data types in Java
  Type	Size	Range
  byte	8 bits	-128 .. 127
  short	16 bits	-32,768 .. 32,767
  int	32 bits	-2,147,483,648 .. 2,147,483,647
  long	64 bits	-9,223,372,036,854,775,808 .. 9,223,372,036,854,775,807
  float	32 bits	3.40282347 x 1038, 1.40239846 x 10-45
  double	64 bits	1.7976931348623157 x 10308, 4.9406564584124654 x 10-324


## Python
* Python uses the 'self' keyword to reference the name of the data type. Python is special in that self doesn't need to be added to the signature as each object recognizes the current instance as 'self'
