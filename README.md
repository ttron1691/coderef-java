# Java Reference for programming

## First program
```Java
package src;

public class Main {

    public static void main(String[] args) {
        System.out.println("Hello, World!");
    }
}
```

# Java Comprehensive Reference Guide

## Table of Contents
1. [Core Java Basics](#core-java-basics)
2. [Object-Oriented Programming](#object-oriented-programming)
3. [Data Structures](#data-structures)
4. [Exception Handling](#exception-handling)
5. [File I/O](#file-io)
6. [Concurrency](#concurrency)
7. [Functional Programming](#functional-programming)
8. [Generics](#generics)
9. [Java Memory Model](#java-memory-model)
10. [Best Practices](#best-practices)
11. [Design Patterns](#design-patterns)
12. [Testing](#testing)
13. [Performance Optimization](#performance-optimization)

## Core Java Basics

### Data Types

#### Primitive Types
```java
byte b = 100;           // 8-bit signed, -128 to 127
short s = 10000;        // 16-bit signed, -32,768 to 32,767
int i = 100000;         // 32-bit signed, -2^31 to 2^31-1
long l = 100000L;       // 64-bit signed, -2^63 to 2^63-1
float f = 234.5f;       // 32-bit floating point
double d = 123.4;       // 64-bit floating point
boolean bool = true;    // true or false
char c = 'A';           // 16-bit Unicode character
```

#### Type Conversions
```java
// Widening (implicit)
int i = 100;
long l = i;  // No cast needed

// Narrowing (explicit)
long l = 100L;
int i = (int) l;  // Cast required
```

### Operators

#### Arithmetic
```java
int a = 10, b = 20;
int sum = a + b;            // Addition: 30
int difference = a - b;     // Subtraction: -10
int product = a * b;        // Multiplication: 200
int quotient = b / a;       // Division: 2
int remainder = b % a;      // Modulus: 0
a++;                        // Increment: a becomes 11
b--;                        // Decrement: b becomes 19
```

#### Comparison
```java
boolean isEqual = (a == b);         // Equal to: false
boolean isNotEqual = (a != b);      // Not equal to: true
boolean isGreater = (a > b);        // Greater than: false
boolean isLess = (a < b);           // Less than: true
boolean isGreaterOrEqual = (a >= b); // Greater than or equal to: false
boolean isLessOrEqual = (a <= b);   // Less than or equal to: true
```

#### Logical
```java
boolean x = true, y = false;
boolean andResult = x && y;         // Logical AND: false
boolean orResult = x || y;          // Logical OR: true
boolean notResult = !x;             // Logical NOT: false
```

#### Bitwise
```java
int x = 5, y = 3;
int bitwiseAnd = x & y;             // Bitwise AND: 1
int bitwiseOr = x | y;              // Bitwise OR: 7
int bitwiseXor = x ^ y;             // Bitwise XOR: 6
int bitwiseComplement = ~x;         // Bitwise NOT: -6
int leftShift = x << 1;             // Left shift: 10
int rightShift = x >> 1;            // Right shift: 2
int unsignedRightShift = x >>> 1;   // Unsigned right shift: 2
```

### Control Flow

#### Conditional Statements
```java
// If-else
if (condition) {
    // code if condition is true
} else if (anotherCondition) {
    // code if anotherCondition is true
} else {
    // code if all conditions are false
}

// Switch
switch (variable) {
    case value1:
        // code for value1
        break;
    case value2:
        // code for value2
        break;
    default:
        // default code
}

// Ternary operator
result = (condition) ? trueValue : falseValue;
```

#### Loops
```java
// For loop
for (int i = 0; i < 10; i++) {
    // code
}

// Enhanced for loop (for-each)
for (String item : collection) {
    // code
}

// While loop
while (condition) {
    // code
}

// Do-while loop
do {
    // code
} while (condition);
```

#### Jump Statements
```java
break;      // Exit loop or switch
continue;   // Skip to next iteration
return;     // Exit method
```

## Object-Oriented Programming

### Classes and Objects
```java
// Class declaration
public class MyClass {
    // Instance variables
    private int instanceVar;
    
    // Static variables
    private static int staticVar;
    
    // Constructor
    public MyClass(int var) {
        this.instanceVar = var;
    }
    
    // Instance method
    public void instanceMethod() {
        // code
    }
    
    // Static method
    public static void staticMethod() {
        // code
    }
}

// Object creation
MyClass obj = new MyClass(10);
```

### Inheritance
```java
// Base class
public class Parent {
    protected int field;
    
    public void method() {
        // code
    }
}

// Derived class
public class Child extends Parent {
    // Override method
    @Override
    public void method() {
        super.method();  // Call parent method
        // additional code
    }
}
```

### Polymorphism
```java
Parent obj = new Child();  // Upcasting
obj.method();              // Calls Child's method

// Downcasting
if (obj instanceof Child) {
    Child childObj = (Child) obj;
    // Use childObj
}
```

### Encapsulation
```java
public class Person {
    private String name;
    private int age;
    
    // Getters
    public String getName() {
        return name;
    }
    
    public int getAge() {
        return age;
    }
    
    // Setters
    public void setName(String name) {
        this.name = name;
    }
    
    public void setAge(int age) {
        if (age >= 0) {  // Validation
            this.age = age;
        }
    }
}
```

### Abstraction
```java
// Abstract class
public abstract class AbstractClass {
    // Abstract method (no implementation)
    public abstract void abstractMethod();
    
    // Concrete method
    public void concreteMethod() {
        // implementation
    }
}

// Interface
public interface MyInterface {
    // Constants
    int MAX_VALUE = 100;  // implicitly public, static, final
    
    // Abstract methods
    void methodOne();     // implicitly public and abstract
    
    // Default method (Java 8+)
    default void defaultMethod() {
        // implementation
    }
    
    // Static method (Java 8+)
    static void staticMethod() {
        // implementation
    }
    
    // Private method (Java 9+)
    private void privateMethod() {
        // implementation
    }
}
```

## Data Structures

### Arrays
```java
// Declaration and initialization
int[] numbers = new int[5];
int[] values = {1, 2, 3, 4, 5};

// Multidimensional array
int[][] matrix = new int[3][4];
int[][] irregular = {{1, 2}, {3, 4, 5}, {6}};

// Array operations
int length = numbers.length;
numbers[0] = 10;
```

### Collections Framework

#### List
```java
// ArrayList
List<String> list = new ArrayList<>();
list.add("Item");
list.add(0, "First Item");
String item = list.get(0);
list.remove(0);
boolean contains = list.contains("Item");
int size = list.size();

// LinkedList
List<String> linkedList = new LinkedList<>();
linkedList.add("Item");
((LinkedList<String>) linkedList).addFirst("First");
((LinkedList<String>) linkedList).addLast("Last");
```

#### Set
```java
// HashSet
Set<String> set = new HashSet<>();
set.add("Item");
set.remove("Item");
boolean contains = set.contains("Item");

// TreeSet (sorted)
Set<String> treeSet = new TreeSet<>();
treeSet.add("B");
treeSet.add("A");
treeSet.add("C");  // Will be stored as A, B, C
```

#### Map
```java
// HashMap
Map<String, Integer> map = new HashMap<>();
map.put("Key", 100);
Integer value = map.get("Key");
map.remove("Key");
boolean containsKey = map.containsKey("Key");
boolean containsValue = map.containsValue(100);

// TreeMap (sorted by keys)
Map<String, Integer> treeMap = new TreeMap<>();
```

#### Queue
```java
// LinkedList as Queue
Queue<String> queue = new LinkedList<>();
queue.offer("Item");  // Add to tail
String head = queue.peek();  // View head
String removed = queue.poll();  // Remove head

// PriorityQueue
PriorityQueue<Integer> pq = new PriorityQueue<>();
pq.offer(3);
pq.offer(1);
pq.offer(2);
Integer highest = pq.poll();  // Returns 1 (minimum)
```

#### Deque (Double-ended queue)
```java
Deque<String> deque = new ArrayDeque<>();
deque.addFirst("First");
deque.addLast("Last");
String first = deque.getFirst();
String last = deque.getLast();
```

## Exception Handling

### Try-Catch-Finally
```java
try {
    // Code that might throw an exception
    int result = 10 / 0;  // ArithmeticException
} catch (ArithmeticException e) {
    // Handle specific exception
    System.err.println("Division by zero: " + e.getMessage());
} catch (Exception e) {
    // Handle any exception
    System.err.println("Error: " + e.getMessage());
} finally {
    // Always executed, even if exception occurs
    // Clean-up code
}
```

### Try-with-Resources (Java 7+)
```java
try (
    FileInputStream input = new FileInputStream("file.txt");
    BufferedReader reader = new BufferedReader(new InputStreamReader(input))
) {
    // Use resources
    String line = reader.readLine();
    // Resources automatically closed after try block
} catch (IOException e) {
    // Handle exception
}
```

### Custom Exceptions
```java
// Custom checked exception
public class CustomCheckedException extends Exception {
    public CustomCheckedException(String message) {
        super(message);
    }
}

// Custom unchecked exception
public class CustomRuntimeException extends RuntimeException {
    public CustomRuntimeException(String message) {
        super(message);
    }
}

// Throwing exceptions
if (someCondition) {
    throw new CustomCheckedException("Error message");
}
```

## File I/O

### File Basics
```java
File file = new File("path/to/file.txt");
boolean exists = file.exists();
boolean isFile = file.isFile();
boolean isDirectory = file.isDirectory();
long length = file.length();
boolean success = file.createNewFile();
boolean deleted = file.delete();
```

### Classic I/O
```java
// Writing to a file
try (FileWriter writer = new FileWriter("output.txt");
     BufferedWriter bufferedWriter = new BufferedWriter(writer)) {
    bufferedWriter.write("Hello World");
    bufferedWriter.newLine();
} catch (IOException e) {
    e.printStackTrace();
}

// Reading from a file
try (FileReader reader = new FileReader("input.txt");
     BufferedReader bufferedReader = new BufferedReader(reader)) {
    String line;
    while ((line = bufferedReader.readLine()) != null) {
        System.out.println(line);
    }
} catch (IOException e) {
    e.printStackTrace();
}
```

### NIO (New I/O, Java 7+)
```java
// Writing to a file
Path path = Paths.get("output.txt");
try {
    Files.write(path, "Hello World".getBytes(), StandardOpenOption.CREATE);
} catch (IOException e) {
    e.printStackTrace();
}

// Reading from a file
try {
    List<String> lines = Files.readAllLines(Paths.get("input.txt"));
    for (String line : lines) {
        System.out.println(line);
    }
} catch (IOException e) {
    e.printStackTrace();
}

// Reading large files
try (Stream<String> stream = Files.lines(Paths.get("large-file.txt"))) {
    stream.forEach(System.out::println);
} catch (IOException e) {
    e.printStackTrace();
}
```

## Concurrency

### Threads
```java
// Extending Thread
class MyThread extends Thread {
    @Override
    public void run() {
        // Thread code
    }
}
MyThread thread = new MyThread();
thread.start();

// Implementing Runnable
class MyRunnable implements Runnable {
    @Override
    public void run() {
        // Thread code
    }
}
Thread thread = new Thread(new MyRunnable());
thread.start();

// Lambda (Java 8+)
Thread thread = new Thread(() -> {
    // Thread code
});
thread.start();
```

### Thread Operations
```java
// Thread states and operations
Thread thread = new Thread();
thread.start();
thread.interrupt();
boolean isAlive = thread.isAlive();
thread.join();  // Wait for thread to die
thread.setPriority(Thread.MAX_PRIORITY);
thread.setDaemon(true);  // Daemon thread
```

### Synchronization
```java
// Synchronized method
public synchronized void synchronizedMethod() {
    // Code accessed by only one thread at a time
}

// Synchronized block
public void method() {
    synchronized(this) {
        // Synchronized code
    }
}

// Static synchronization
public static synchronized void staticMethod() {
    // Synchronized on class lock
}
```

### Locks (java.util.concurrent.locks)
```java
Lock lock = new ReentrantLock();
try {
    lock.lock();
    // Critical section
} finally {
    lock.unlock();  // Always unlock in finally
}

// Try lock with timeout
if (lock.tryLock(1, TimeUnit.SECONDS)) {
    try {
        // Critical section
    } finally {
        lock.unlock();
    }
}
```

### Concurrent Collections
```java
// Thread-safe collections
ConcurrentHashMap<String, Integer> map = new ConcurrentHashMap<>();
CopyOnWriteArrayList<String> list = new CopyOnWriteArrayList<>();
BlockingQueue<Task> queue = new LinkedBlockingQueue<>();
```

### Atomic Variables
```java
AtomicInteger counter = new AtomicInteger(0);
int value = counter.incrementAndGet();  // Atomic ++counter
int anotherValue = counter.getAndIncrement();  // Atomic counter++
counter.compareAndSet(expected, newValue);  // CAS operation
```

### Thread Pools
```java
// Fixed thread pool
ExecutorService executor = Executors.newFixedThreadPool(5);
executor.submit(() -> {
    // Task code
});

// Scheduled executor
ScheduledExecutorService scheduler = Executors.newScheduledThreadPool(1);
scheduler.scheduleAtFixedRate(task, 0, 1, TimeUnit.SECONDS);

// Proper shutdown
executor.shutdown();
if (!executor.awaitTermination(60, TimeUnit.SECONDS)) {
    executor.shutdownNow();
}
```

### CompletableFuture (Java 8+)
```java
CompletableFuture<String> future = CompletableFuture.supplyAsync(() -> {
    // Compute result asynchronously
    return "Result";
});

future
    .thenApply(result -> result.toUpperCase())  // Transform result
    .thenAccept(System.out::println)            // Consume result
    .exceptionally(ex -> {                      // Handle exceptions
        System.err.println(ex.getMessage());
        return null;
    });
```

## Functional Programming

### Lambda Expressions (Java 8+)
```java
// Lambda syntax
Runnable r = () -> System.out.println("Hello");
Consumer<String> c = s -> System.out.println(s);
Function<String, Integer> f = s -> s.length();
BiFunction<Integer, Integer, Integer> add = (a, b) -> a + b;

// With block
Function<Integer, Integer> factorial = n -> {
    int result = 1;
    for (int i = 1; i <= n; i++) {
        result *= i;
    }
    return result;
};
```

### Functional Interfaces
```java
@FunctionalInterface
interface Calculator {
    int calculate(int a, int b);
}

Calculator addition = (a, b) -> a + b;
int result = addition.calculate(5, 3);  // 8
```

### Method References
```java
// Static method reference
Function<String, Integer> strToInt = Integer::parseInt;

// Instance method reference of particular object
Consumer<String> printer = System.out::println;

// Instance method reference of arbitrary object of particular type
Function<String, Integer> length = String::length;

// Constructor reference
Supplier<List<String>> listSupplier = ArrayList::new;
```

### Streams
```java
List<String> list = Arrays.asList("apple", "banana", "cherry");

// Basic stream pipeline
list.stream()
    .filter(s -> s.startsWith("a"))   // Intermediate operation
    .map(String::toUpperCase)         // Intermediate operation
    .sorted()                         // Intermediate operation
    .forEach(System.out::println);    // Terminal operation

// Collect results
List<String> filtered = list.stream()
    .filter(s -> s.length() > 5)
    .collect(Collectors.toList());

// Find elements
Optional<String> first = list.stream()
    .filter(s -> s.startsWith("b"))
    .findFirst();

// Numeric operations
int sum = list.stream()
    .mapToInt(String::length)
    .sum();

// Parallel processing
list.parallelStream()
    .forEach(System.out::println);
```

### Optional (Java 8+)
```java
// Creating Optionals
Optional<String> empty = Optional.empty();
Optional<String> opt = Optional.of("value");  // Non-null value
Optional<String> nullable = Optional.ofNullable(mayBeNull);

// Using Optionals
String result = opt.orElse("default");
String computed = opt.orElseGet(() -> computeDefault());
String required = opt.orElseThrow(() -> new NoSuchElementException());

// Conditional operations
opt.ifPresent(System.out::println);

// Transformations
Optional<Integer> length = opt.map(String::length);
```

## Generics

### Generic Classes
```java
// Generic class
public class Box<T> {
    private T value;
    
    public Box(T value) {
        this.value = value;
    }
    
    public T getValue() {
        return value;
    }
    
    public void setValue(T value) {
        this.value = value;
    }
}

// Usage
Box<Integer> intBox = new Box<>(10);
Box<String> strBox = new Box<>("Hello");
```

### Generic Methods
```java
public <T> T getFirst(List<T> list) {
    return list.isEmpty() ? null : list.get(0);
}

// Usage
String first = getFirst(Arrays.asList("a", "b", "c"));
```

### Bounded Type Parameters
```java
// Upper bound
public <T extends Number> double sum(List<T> list) {
    double sum = 0;
    for (T item : list) {
        sum += item.doubleValue();
    }
    return sum;
}

// Multiple bounds
public <T extends Comparable<T> & Serializable> T max(T a, T b) {
    return a.compareTo(b) > 0 ? a : b;
}
```

### Wildcards
```java
// Unknown type
void printList(List<?> list) {
    for (Object item : list) {
        System.out.println(item);
    }
}

// Upper bounded wildcard
void sumList(List<? extends Number> list) {
    double sum = 0;
    for (Number n : list) {
        sum += n.doubleValue();
    }
}

// Lower bounded wildcard
void addNumbers(List<? super Integer> list) {
    list.add(1);
    list.add(2);
}
```

### Type Erasure
```java
// At compile time:
public class Box<T> {
    private T value;
    // ...
}

// After erasure (runtime):
public class Box {
    private Object value;
    // ...
}
```

## Java Memory Model

### Stack vs Heap
- **Stack**: Stores primitive values and object references
- **Heap**: Stores actual objects

### Memory Management
```java
// Object lifecycle
Object obj = new Object();  // Allocation
obj = null;                 // Eligible for garbage collection
```

### Garbage Collection
- Mark-Sweep-Compact algorithm
- Generational collection (Young and Old generations)
- G1 Garbage Collector (default in Java 9+)

### Memory Leaks
Common causes:
- Static fields holding object references
- Unclosed resources (streams, connections)
- Incorrect implementation of equals/hashCode
- Inner classes holding references to outer instances

## Best Practices

### Naming Conventions
```java
// Classes: CamelCase starting with uppercase
public class MyClass { }

// Methods and variables: camelCase starting with lowercase
public void myMethod() {
    int myVariable = 5;
}

// Constants: All uppercase with underscores
public static final int MAX_SIZE = 100;

// Packages: All lowercase
package com.example.mypackage;
```

### Code Organization
- One public class per file
- Group related functionality
- Follow standard directory structure
- Use packages to organize code

### Documentation
```java
/**
 * Class description here.
 * 
 * @author Author Name
 * @version 1.0
 */
public class MyClass {
    /**
     * Method description here.
     * 
     * @param param1 Description of parameter
     * @return Description of return value
     * @throws Exception Description of when exception is thrown
     */
    public String myMethod(String param1) throws Exception {
        // implementation
    }
}
```

### Clean Code Principles
- DRY (Don't Repeat Yourself)
- SOLID principles
- Write self-documenting code
- Keep methods short and focused
- Proper error handling
- Use meaningful names

### Security Practices
- Input validation
- Prevent SQL injection
- Use prepared statements
- Handle sensitive data securely
- Follow principle of least privilege
- Use secure communication (HTTPS)

## Design Patterns

### Creational Patterns
```java
// Singleton
public class Singleton {
    private static Singleton instance;
    
    private Singleton() { }
    
    public static synchronized Singleton getInstance() {
        if (instance == null) {
            instance = new Singleton();
        }
        return instance;
    }
}

// Factory Method
interface Product { }
class ConcreteProduct implements Product { }

abstract class Creator {
    abstract Product createProduct();
}

class ConcreteCreator extends Creator {
    @Override
    Product createProduct() {
        return new ConcreteProduct();
    }
}

// Builder
public class User {
    private final String name;
    private final int age;
    
    private User(Builder builder) {
        this.name = builder.name;
        this.age = builder.age;
    }
    
    public static class Builder {
        private String name;
        private int age;
        
        public Builder name(String name) {
            this.name = name;
            return this;
        }
        
        public Builder age(int age) {
            this.age = age;
            return this;
        }
        
        public User build() {
            return new User(this);
        }
    }
}

// Usage
User user = new User.Builder()
    .name("John")
    .age(30)
    .build();
```

### Structural Patterns
```java
// Adapter
interface Target {
    void request();
}

class Adaptee {
    void specificRequest() {
        // Implementation
    }
}

class Adapter implements Target {
    private Adaptee adaptee;
    
    public Adapter(Adaptee adaptee) {
        this.adaptee = adaptee;
    }
    
    @Override
    public void request() {
        adaptee.specificRequest();
    }
}

// Decorator
interface Component {
    void operation();
}

class ConcreteComponent implements Component {
    @Override
    public void operation() {
        // Implementation
    }
}

abstract class Decorator implements Component {
    protected Component component;
    
    public Decorator(Component component) {
        this.component = component;
    }
    
    @Override
    public void operation() {
        component.operation();
    }
}

class ConcreteDecorator extends Decorator {
    public ConcreteDecorator(Component component) {
        super(component);
    }
    
    @Override
    public void operation() {
        super.operation();
        addedBehavior();
    }
    
    private void addedBehavior() {
        // Additional behavior
    }
}
```

### Behavioral Patterns
```java
// Observer
interface Observer {
    void update(String message);
}

class ConcreteObserver implements Observer {
    @Override
    public void update(String message) {
        System.out.println("Received: " + message);
    }
}

class Subject {
    private List<Observer> observers = new ArrayList<>();
    
    public void addObserver(Observer observer) {
        observers.add(observer);
    }
    
    public void removeObserver(Observer observer) {
        observers.remove(observer);
    }
    
    public void notifyObservers(String message) {
        for (Observer observer : observers) {
            observer.update(message);
        }
    }
}

// Strategy
interface Strategy {
    int doOperation(int a, int b);
}

class AddStrategy implements Strategy {
    @Override
    public int doOperation(int a, int b) {
        return a + b;
    }
}

class SubtractStrategy implements Strategy {
    @Override
    public int doOperation(int a, int b) {
        return a - b;
    }
}

class Context {
    private Strategy strategy;
    
    public void setStrategy(Strategy strategy) {
        this.strategy = strategy;
    }
    
    public int executeStrategy(int a, int b) {
        return strategy.doOperation(a, b);
    }
}
```

## Testing

### JUnit Basics
```java
import org.junit.jupiter.api.Test;
import static org.junit.jupiter.api.Assertions.*;

public class CalculatorTest {
    @Test
    public void testAdd() {
        Calculator calc = new Calculator();
        assertEquals(5, calc.add(2, 3));
    }
    
    @Test
    public void testDivide() {
        Calculator calc = new Calculator();
        assertThrows(ArithmeticException.class, () -> calc.divide(1, 0));
    }
}
```

### Mockito
```java
import org.mockito.Mockito;
import static org.mockito.Mockito.*;

// Create mock
UserService userService = Mockito.mock(UserService.class);

// Define behavior
when(userService.findById(1)).thenReturn(new User("John"));

// Verify interactions
verify(userService, times(1)).findById(1);
```

### Test-Driven Development (TDD)
1. Write a failing test
2. Write minimal code to make the test pass
3. Refactor code while keeping tests passing

## Performance Optimization

### Profiling
- Use tools: VisualVM, JProfiler, YourKit
- Identify hotspots and bottlenecks
- Monitor CPU, memory, and threads

### Memory Optimization
- Use primitives instead of wrappers when possible
- Avoid unnecessary object creation
- Close resources properly
- Consider object pooling for expensive objects
- Be careful with large collections

### Execution Optimization
- Use buffer for I/O operations
- Minimize database calls
- Consider caching for expensive computations
- Use appropriate data structures
- Optimize algorithms (O(n²) → O(n log n) → O(n))

