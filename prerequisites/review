# Review
Along with understanding how to create simple programs in Java, the following topics will be used extensively throughout the course.
## Abstraction and Interfaces
An **application programming interface (API)** or simply an **interface** is an understanding between two entities on how to communicate. An API specifies that if a certain function is called, with specific values, what is returned by the call. This also an understanding of what operation the function will preform. 
For example, the method `public int add(int a, int b)` takes two integers and returns a single integer. Given the name of the method, it is likely the returned value is the addition of the two parameters `a,b`.

In this course we will use interfaces to define the "blueprint" of each data structure. Such interfaces are called **Abstract data types (ADT)**. They do not implement any functionality of the data structures that use them, only define the methods that must be supported. While interfaces are not needed, they serve two purposes:
1. If a data structure fails to correctly implement any method defined by the interface, a complier error will occur.
2. It forces the programmer to use encapsulation. Typically all public methods are specified by the interface; this requires the developer to be clear on what the data structure will do.

Below is an example of an interface and a class that implements it. 
```
public interface Math {
	public int add(int a, int b);
	public int subtract(int a, int b);
	public int multiply(int a, int b);
	public int divide(int a, int b);
}

public class MathOps implements Math {
	@Override()
	public int add(int a, int b){
		// Add ...
	}
	public int subtract(int a, int b){
		// Subtract
	}
	public int multiply(int a, int b) {
		// multiply
	}
	public int divide(int a, int b) {
		// check divisiblity, divide. 
	}
}
```

In Java we use the keywords `interface` and `implements` to define the interface class and to enable another class to implement it. We can also use the `@Override` annotation to signify that this method is defined elsewhere, although it is optional. 

## Generic Types
