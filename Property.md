# Properties



## Python
* Using 'getters' and 'setters' aren't typically used in Python but can be utilized. The typical way is just to use plain attributes to pass the information and then to dereference the attribute using the 'del' function.
However, getters and setters can be added to the code to make it consistent to other programming. These can be added using the 'property' decorator without altering the original code
```
class obj:
  @property
  def attribute(self):
    return self.__attribute
  @attribute.setter
  def attribute_setter(self, value):
    self.__attribute = value
 ```
