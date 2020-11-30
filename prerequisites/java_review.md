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
	public int add();
	public int subtract();
	public int multiply();
	public int divide();
}

public class MathOps implements Math {
	private int a, b;
	
	public MathOps(int a, int b) {
		this.a=a; 
		this.b=b;
	}
	@Override()
	public int add(){
		// Add ...
	}
	public int subtract(){
		// Subtract
	}
	public int multiply() {
		// multiply
	}
	public int divide() {
		// check divisiblity, divide. 
	}
}
```

In Java we use the keywords `interface` and `implements` to define the interface class and to enable another class to implement it. We can also use the `@Override` annotation to signify that this method is defined elsewhere, although it is optional. 

## Generic Types
Data structures can be thought of as pieces of data that are structured in a particular manner. For this reason we want our data structures to be robust, and work for many types of data. Thus we will define our data structures to "hold" generic data which is specified at a later point in time. 

This is achieved using Java's generics framework which is specified using formal type parameters in the class definition using angle brackets and by convention we use uppercase letters to denote the generic type, for example `<E>` where "E" denotes the element (data) used. We can also do this for multiple generic types (e.g. `<V,E>` for vertices and edges of a graph.) It is required that the generic type be a Java object. 

We can build on the example above to use generic types as follows:

```
public interface Math<E> {
	public E add();
	public E subtract();
	public E multiply();
	public E divide();
}

public class MathOps<E> implements Math<E> {
	private E a, b;
	
	public MathOps(E a, E b) {
		this.a=a; 
		this.b=b;
	}
	@Override()
	public E add(){
		// Add ...
	}
	public E subtract(){
		// Subtract
	}
	public E multiply() {
		// multiply
	}
	public E divide() {
		// check divisiblity, divide. 
	}
}
```

Note how the types for `a` and `b` are now `E`, along with the return types for each method. We can specify what type `E` is when we initialize our `MathOps` object using predefined classes.
```
MathOps<Integer> mathInt = new MathOps<Integer>(...);
MathOps<Double> mathDouble = new MathOps<Double>(...);
```
