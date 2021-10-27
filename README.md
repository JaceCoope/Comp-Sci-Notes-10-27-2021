# Comp-Sci-Notes-10-27-2021

## Generic Types
```java
//example:
public static <T> List<T>
```
### Arrays Class
Could provide a static method that sorts an array of Objects
* But - what does it mean to compare two arbitrary Objects so that we can establish an ordering between them?
  * For example a String and an Integer?
* We really need a way of talking ge

### Java Generics
* A type becomes a parameter to a class and/or a method:
```java
public class ClassName<T>
{
  :
}
```
* T is the variable type that is assigned when we use the class
* Within the class definition, we can "pretend" that it is a real type (parameters, variable declarations and return types)
* `Array<String list = new ArrayList<>();`
* <> - diamond operator

### Standard Generic Type Names
* E - Element (used extensively by the Java Collections Framework)
* K - Key
* N - Number
* T - Type
* V - Value
* Java 5 and higher allows for generics classes and methods
* It tasks the compiler to check types
* A generic class or method permits only the allowable types of objects

### Advantages of Generics
* Code reuse
* Specific types are checked at compile time (as opposed to everything having to be Object)
* Easier

### Notes
* Primitive types cannot be used as generic types (Must use wrapper classes)
* Type erasure: generics are checked at compile time, not at runtime
  * This decision was made to maintain backward compatibility

### Implications of Type Erasure
* Cannot construct objects of type E
```java
E myData = new E(); //ilegal code
```
* Cannot construct arrays of type E
```java
E[] elements = new E[capacity]; //ilegal
```
  * Solution to the latter: create an array of objects and then cast to array E
  ```java
  E[] elements = (E[]) new Object[capacity]; //Legal
  ```
* instanceof() cannot distinguish same class with different generic type, because it is done at run time
* Exception classes cannot be generic
* Static data cannot be of a generic type

### Inheritcane and Generics
* In many situation, we might have more than one generic type ar part of a class or method definition
* These could be arbitrary types or we might want them to have some specific relationship
  * For example: we might want T1 to be a superclass of T2

### Generics
A type becomes a parameter

### Wildcards
There is a class hierarchy that we can use...
ArrayList<?> = Arraylist of anything
ArrayList<? extends Number> = ArrayList of anything that is a subclass of Number

### Wildcard Example I
Arrays in Java API (atucal implementation):
`binarySearch(T[] a, T key, Comparator<? super T>, etc)`
ArrayList<? super number> = Arraylist of anything that is a superclass of Number

```java
public static<T> void()
