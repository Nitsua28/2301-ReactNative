## Java
- Object-Oriented - 
    - Classes and Objects
    - We create classes with methods (like functions in JS) and variables/fields
    - We can create objects that are based on those classes
        - We call the objects instances of that class
        - Classes are like a blue print and the objects are the instances
    - ex: Car class, you can create many different instances of that car class
- Machine Independent
    - Write Once Run Anywhere


## Compilation Process
- 2 main steps

### Compilation
- .java file that's passed to the compiler
```java
class Car {
    int wheels;
    String color;
}
```
- Source code is encoded into Bytecode (machine-independent), .class file


### Execution
- Main class file (starting point for the app) is passed to the JVM (Java Virtual Machine)
    1. Class-Loader - loads all classes that are used in the program
    2. Bytecode verifier - checks that bytecode and makes sure that it doesn't have damaging instructions (ex: using a variable before it's initialized)
    3. Just-In-Time Compiler convert bytecode into machine code

    
![Diagram of Compilation](https://media.geeksforgeeks.org/wp-content/uploads/java.jpg)


### Installation
- JDK - Java Development Kit - This is what us, as developers, need to write, develop, run, test, debug our Java code
    - JDK contains the JRE and JVM which are required to run the code
- IDE - Interactive Development Environment
    - IntelliJ (Recommended) - Community edition is fine for our purposes
        - Create associations with .java file
        - Add bin to path
    - Eclipse


## Packages
- Like folders/directories
- We also specify which package each class is in
- We have access-modifiers 
    - public - it means it can be accessed anywhere
    - default - it can only be used in the same package
- Packages help us determine what variables can and can't be accessed

## Main Method
- The starting/entry point for our class
- Key words
    - public - call this method from anywhere in the program
    - static - the method is associated with the class rather than an instance (this is good because we wouldn't to be required to create an instance of this class before we call the main method)
    - void - doesn't return anything
- Parameters
    - String [] args - an array of strings which indicate that arguments that we pass in to our program
        - If we run our program from the command line, we can pass in additional arguments to use in the program
- Body - what runs when we execute the program
    - this can call other methods


## Primitive Types:
- any type that isn't a class
- char - letter/symbol ('a', '2', '$')
- int - whole number
- byte, shorts - whole numbers with a lower range than int
- long - whole number that has a higher range than int
- doubles/floats - a number with decimal places (doubles have more precision than floats)
- boolean - true/false values
- In order from smallest to largets: boolean, byte, short/char, int/float, long/double
- Most commonly used: int, double, boolean, char
    - Sometimes use longs if we want guaranteed larger range


## String
- Declaring String with the new keyword vs the primitive-esque assignment
    - String s = new String("Hello");
        - This is how we normally declare classes
        - This does not leverage the String pool
        - All strings created with the new keyword have their own spot in memory
    - String s = "Hello";
        - String pool
            - A way to save memory by using the same memory locaiton for identical strings
            - If we declare 3 different strings all with the same value (ex: "Hello"), only one instance of that string will be created in the String pool
            - Each of those variables will reference the same exact location
            - Strings are immutable in Java, we can't change the String itself
                - This makes sense because changing the memory would affect all references to that same String
![String Pool](https://journaldev.nyc3.digitaloceanspaces.com/2012/11/String-Pool-Java1.png)

## IntelliJ shortcuts:
- sout => System.out.println()
- psvm => main method declaration
- if your cursor is on a line hitting ctrl+c will copy the whole line
    - ctrl+v will paste

## Memory
- Primitives won't be stored in the Heap

## Wrapper Classes (More on Collections)
- Integer, Float, Character etc.
- Every primitive type has a corresponding class which then lets us have methods on those types

## The Object class
- In java, we have classes (which are like blueprints) and we have objects that are the instances of those blueprints
- But there is a class in Java called Object
- Because every thing we create in Java is an object (besides primitives), the Objecr class serves as a common ancestor for all other classes we create
- Every class we make will inherit from the Object class, meaning that it will have all of the methods that the Object class has
    - toString - takes our object and converts to a string representation
    - equals - compares two objects and returns whether or not they are equal to each other
    - hashCode - returns an integer representation of an object

## super keyword
- the super keyword lets children access elements of the parent class:
    - calling super() calls the parent constructor
    - super.method calls the parent method
    - super.field access the parent fields

## Scopes:
- method - a variable that we declare in a method won't be accessible from outside the method
- block scope - a variable declared in a block can't be accessible from outside
    - this is useful with for loops because it lets us redeclare the int i counter for every for loop
- Static/Class scope - method/variable is tied to the class itself (example: Calculator.PI)
- Instance/Object scope - variables that are attached to the particular instance (example: animal.species)

## Access Modifiers:
- Access modifier is a keyword that we apply to a method, class, variable that indicates where in the program it can be accessed
- public - it can be accessed anywhere in the project (no matter what package it's in)
- private - it can only be accessed within that same class
    - methods can only be called from other methods in that class
    - variables can only be accessed by methods in that class
- default - accessible within the same package
    - The tricky part is that we don't actually declare anything as default
    - "Default" in this case means we don't give an access modifier
- protected - accessible within the same package and sub-classes
    - can apply to methods and variables

## Non-Access Modifiers:
- These are modifiers that don't affect our access to the methods/variable/class
- abstract
    - apply to class to make it possible to have abstract methods
    - apply to method to make that method abstract (we don't need a method body)
- static
    - Scopes the method/variable to the class rather than an instance
        - ex: A calculator class, we could have a static field for PI because PI will not vary depending on which instance we have
        - We use the static keyword on our main methods because we don't actually need an instance of our class to run them
    - We can't call non-static methods or access non-static variables from a static context/method
    - We CAN call static methods and access static variables from a non-static/instance method
- final
    - 3 different contexts:
        - If we apply it to a variable, it means we can't reassign it
            - If we have an object declared as final, we can reassign the fields
        - If we apply it to a method, we can't override it
        - If we apply it to a class, we can't extend it

## This keyword:
- We use the "this" keyword in our methods to indicate that we want this particular instance's field or method
```java
class Animal {
    String name;

    
    public Animal(String nameInput) {
        // the "this" keyword denotes that we want to access the instance's name field rather than the parameter that we passed in:
        this.name = nameInput;
    }
}

```