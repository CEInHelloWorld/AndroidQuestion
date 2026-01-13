# Android-Interview-Question-Answer

# LEVEL 1: Computer Science Fundamentals

## Object-Oriented Programming

<details>
<summary><strong>Explain the four pillars of OOP : Inheritance, Polymorphism, Encapsulation, and Abstraction</strong></summary>

1. Inheritance – It allows a class to inherit properties and behavior from another class, promoting code reusability. For example, a Car class can inherit from a Vehicle class.

2. Polymorphism – It means "many forms." It allows us to perform a single action in different ways — for instance, method overriding or overloading in Kotlin or Java.

3. Encapsulation – It’s about hiding internal data and exposing only necessary functionality. We achieve this using access modifiers and getter/setter methods.

4. Abstraction – It focuses on showing only essential features while hiding complex implementation details, often done through abstract classes or interfaces.
</details>


<details>
<summary><strong>What's the difference between abstract classes and interfaces?</strong></summary>

The main difference is that an abstract class can have both abstract and non-abstract methods, along with state — meaning it can hold variables and constructors.

An interface, on the other hand, is mainly used to define a contract — it only declares methods that must be implemented
</details>

<details>
<summary><strong>What's the difference between abstract classes and interfaces in Java 8+ and Kotlin?</strong></summary>

In Java 8+, interfaces can have default and static methods, so they’re no longer limited to abstract methods only.

In Kotlin, interfaces can include default method bodies and properties without backing fields, while abstract classes can hold state, constructors, and initialization logic.
</details>

<details>
<summary><strong>What is the final keyword in Java and when should you use it?</strong></summary>

The final keyword prevents modification.

- A final variable can’t be reassigned.
- A final method can’t be overridden.
- A final class can’t be inherited.
</details>

<details>
<summary><strong>What's the difference between == and .equals() in Java</strong></summary>

`==` checks reference equality — whether two objects point to the same memory.

`.equals()` checks value equality — whether two objects have the same content.
</details>

## Data Structures & Collections

<details>
<summary><strong>What's the difference between List, Set, and Map? Give common implementations</strong></summary>

- **List –** An ordered collection that allows duplicates. Example implementations: `ArrayList`, `LinkedList`

- **Set –** An unordered collection that doesn’t allow duplicates. Example implementations: `HashSet`, `LinkedHashSet`, `TreeSet`.

- **Map –** A collection of key-value pairs, where keys are unique. Example implementations: `HashMap`, `LinkedHashMap`, `TreeMap`.
</details>

<details>
<summary><strong>Explain ArrayList vs LinkedList - when would you use each?</strong></summary>

- `ArrayList` stores elements in a resizable array — fast random access (O(1)), slower inserts/deletes in the middle (O(n)). Use it when you need frequent access by index.

- `LinkedList` stores elements as nodes connected by pointers — slower random access (O(n)), but fast inserts/deletes anywhere (O(1)). Use it when you do frequent insertions or deletions.
</details>

<details>
<summary><strong>Explain HashMap internal working</strong></summary>

A `HashMap` stores data as key-value pairs using a hash table. When we add a key, its `hashCode()` determines which bucket it goes into. If multiple keys end up in the same bucket, it handles collisions using a linked list or tree.

When we call `get()`, `HashMap` uses the hash to find the bucket and then `equals()` to find the exact key. If we `put()` a key that already exists, it updates the value; otherwise, it adds a new entry.

This gives `O(1)` average performance for insert and lookup.
</details>

<details>
<summary><strong>What is a HashSet and how does it work internally?</strong></summary>

A `HashSet` is a collection that stores unique elements and doesn’t maintain order.

Internally, it’s backed by a `HashMap`. When you add an element, it’s stored as a key in the HashMap with a dummy value.
It uses the element’s `hashCode()` to determine the bucket, and `equals()` to check for duplicates.

This makes add, remove, and contains operations `O(1)` on average.
</details>

## Algorithms & Complexity

<details>
<summary><strong>Explain Big O notation (time and space complexity)
</strong></summary>

**Big O notation** is a way to describe the performance or complexity of an algorithm in terms of time or space as the input size grows.

- **Time complexity** tells how the runtime increases with input size, e.g., O(1), O(n), O(n²).
- **Space complexity** tells how memory usage grows with input size.
</details>

<details>
<summary><strong>Explain these sorting algorithms: Quick Sort, Merge Sort, Bubble Sort, Insertion Sort</strong></summary>

- **Quick Sort –** A divide and conquer algorithm that picks a pivot, partitions the array, and recursively sorts the partitions. Average O(n log n), worst O(n²). Fast in practice.

- **Merge Sort –** Also divide and conquer, splits the array into halves, sorts them recursively, and merges. Always O(n log n). Stable and good for large data.

- **Bubble Sort –** Repeatedly swaps adjacent elements if they’re in the wrong order. Simple but slow, O(n²). Mostly used for learning, not production.

- **Insertion Sort –** Builds the sorted array one element at a time by inserting elements in the correct position. O(n²), efficient for small or nearly sorted data.
</details>

<details>
<summary><strong>What's the difference between Binary Search and Linear Search?
</strong></summary>

- **Linear Search** checks each element one by one until it finds the target. Works on unsorted data, time complexity O(n).

- **Binary Search** repeatedly divides a sorted array in half to find the target. Time complexity O(log n). Much faster than linear search for large datasets, but requires sorted input.
</details>

## Threading Concepts

<details>
<summary><strong>What's the difference between Process and Thread?</strong></summary>

A **process** is an independent program running in its own memory space, while a thread is a smaller unit of execution within a process that shares the process’s memory.

- **Process:** Heavyweight, isolated memory, slower to create.
- **Thread:** Lightweight, shares memory, faster to create and switch.
</details>

<details>
<summary><strong>Explain Synchronization, Deadlocks, and Race conditions</strong></summary>

- **Synchronization** is a way to control access to shared resources so that only one thread can use it at a time, preventing inconsistent data.

- A **race condition** happens when two or more threads access shared data at same time, and the final result depends on the timing of execution, which can cause bugs.

- A **deadlock** occurs when two or more threads wait on each other indefinitely, each holding a resource the other needs, so none can proceed.

In short: synchronization prevents race conditions, but if not handled carefully, it can lead to deadlocks.
</details>

# LEVEL 2: Kotlin Language Mastery (Must Know Cold)

## Basics

<details>
<summary><strong>What's the difference between var and val in Kotlin?</strong></summary>

`var` is a mutable variable, which can be reassigned multiple times.

while, `val` is immutable variable, meaning it can be assigned only once and we can not change their value.

</details>

<details>
<summary><strong>What's the difference between val and const val?</strong></summary>

`val` is a runtime constant — its value is assigned at runtime and can depend on logic or function results.

`const val` is a compile-time constant — its value must be known at compile time and can only hold primitive or String values at the top level or inside objects/companion objects.

</details>

<details>
<summary><strong>What is lateinit and when should you use it?</strong></summary>

`lateinit` is used to declare a `non-null` variable that will be initialized later, not at the time of declaration.

 We use it when initialization depends on something that’s not available immediately — for example, initializing a View or adapter in onCreate().
</details>

<details>
<summary><strong>What is lazy initialization in Kotlin?</strong></summary>

**Lazy initialization** means delaying the creation of an object until it’s first used.

In Kotlin, we use `by lazy { ... }` for this — it runs the block only once, stores the result, and returns it for future calls.

It’s ideal for **read-only (val)** properties
</details>

<details>
<summary><strong>What is lazy initialization in Kotlin?</strong></summary>

**Lazy initialization** means delaying the creation of an object until it’s first used.

In Kotlin, we use `by lazy { ... }` for this — it runs the block only once, stores the result, and returns it for future calls.

It’s ideal for **read-only (val)** properties
</details>

<details>
<summary><strong>What's the difference between == and === in Kotlin?</strong></summary>

In Kotlin, == checks structural equality, meaning it compares the values of two objects using .equals().

=== checks referential equality, meaning it compares whether both references point to the same object in memory.

So, == checks content, while === checks memory reference.
</details>

<details>
<summary><strong>How does Kotlin handle null safety?</strong></summary>

Kotlin handles null safety through its type system.

By default, variables can’t hold null. If you want to allow null, you must declare it with a ?, like String?.

You can safely access nullable variables using safe calls (?.), provide defaults with Elvis operator (?:), or throw exceptions with !! if you’re sure it’s not null.

This helps prevent NullPointerExceptions at compile time.
</details>

<details>
<summary><strong>How kotlin is better than java?</strong></summary>

Kotlin is better than Java because it’s more concise, expressive, and safer. It reduces boilerplate code, supports null safety to avoid NullPointerExceptions, and has modern features like extension functions, coroutines, and data classes.

It’s fully interoperable with Java, so you can migrate gradually. That’s why most modern Android apps are moving to Kotlin — it makes development faster, safer, and more maintainable.
</details>

<details>
<summary><strong>What is the Elvis operator ?: used for?</strong></summary>

The Elvis operator `?:` is used to provide a default value when an expression is `null`.
</details>

<details>
<summary><strong>Explain !!, ?., and ?.let in Kotlin</strong></summary>

In Kotlin, `!!` is the not-null assertion operator. It tells the compiler that a value is not null, and if it is null at runtime, it throws a NullPointerException.

`?.` is the safe call operator. It lets you call a method or access a property only if the object is not null; otherwise, it returns null.

`?.let { }` is used to execute a block of code only if the object is not null. Inside the let block, the object is non-null and can be safely used.
</details>

<details>
<summary><strong>What is smart casting in Kotlin?</strong></summary>
Smart casting in Kotlin means the compiler automatically casts a variable to a specific type after it’s been checked with conditions like is.
</details>

<details>
<summary><strong>How can you make a function parameter optional?</strong></summary>
In Kotlin, you can make a function parameter optional by giving it a default value.

```kotlin
fun greet(name: String = "Guest") {
    println("Hello, $name")
}
```
</details>

## Functions & Extensions

<details>
<summary><strong>What are extension functions and how do they work under the hood?</strong></summary>

Extension functions let us add new functions to existing classes without changing their code.

For example, I can add a capitalizeFirst() function to String and call it like a normal method.

Under the hood, it’s just a static function, and Kotlin passes the object as the first parameter — it just looks like part of the class.
</details>


<details>
<summary><strong>Can you override an extension function? Why or why not?</strong></summary>

No, we can’t override an extension function.

Because extension functions are statically resolved — they don’t actually become part of the class, they’re just utility functions.
</details>

<details>
<summary><strong>What are higher-order functions? Give an example</strong></summary>

A higher-order function is a function that takes another function as a parameter or returns a function.

```kotlin
fun operate(a: Int, b: Int, op: (Int, Int) -> Int): Int {
    return op(a, b)
}
```

</details>


<details>
<summary><strong>What is a lambda expression?</strong></summary>

A lambda expression is an anonymous function you can pass as a value.

```kotlin
val sum = { a: Int, b: Int -> a + b }
println(sum(3, 4)) // prints 7
```
</details>

<details>
<summary><strong>What's the difference between inline, crossinline, and noinline?</strong></summary>


An inline function tells Kotlin to replace the function call with its code at compile time. This reduces the overhead of passing lambdas.

=================================================

Sometimes in an inline function, we don’t want some lambdas to be inlined (maybe we want to store them or pass them around).
We use noinline for those lambdas.

Example:

inline fun doSomething(a: Int, noinline op: (Int) -> Int) {
    println(op(a))
}

doSomething(5) { it * 2 } // prints 10


Here, op is not inlined, so it can be stored or passed to other functions.

=================================================

rossinline

By default, an inline lambda can do a non-local return — it can return from the outer function.
Sometimes we don’t want that, and we use crossinline.

Example:

```kotlin
inline fun runTask(crossinline task: () -> Unit) {
    val runnable = Runnable { task() }
    runnable.run()
}

runTask { println("Task running") } // prints "Task running"
```

Here, crossinline prevents the lambda from returning directly from runTask.

</details>

<details>
<summary><strong>When should you use inline function?</strong></summary>

We use an inline function when a function takes lambdas and is called often, and you want to reduce the overhead of creating function objects.
This makes it faster by avoiding extra objects or function calls.
</details>

## Classes & Objects

<details>
<summary><strong>What are data classes used for in Kotlin?</strong></summary>

Data classes in Kotlin are used to store data. They automatically provide `toString()`, `equals()`, `hashCode()`, and `copy()` functions, so you don’t have to write them manually.

Use them whenever you need a class mainly to hold values
</details>

<details>
<summary><strong>How do copy() and componentN() functions work in data classes?</strong></summary>

- `copy()` – lets you create a new object with some values changed while keeping others the same.

```kotlin
val user1 = User(1, "Pratik")
val user2 = user1.copy(name = "Ravi")
```

- `componentN()` – lets you get properties in order for destructuring.

```kotlin
val (id, name) = user1
println(id) // 1
println(name) // Pratik
```

So `copy()` is for modifying data, and `componentN()` is for easy destructuring.
</details>

<details>
<summary><strong>What's the difference between object, companion object, and class?</strong></summary>

- **Class** – A blueprint to create objects. You can have multiple instances.

- **Object** – A singleton; only one instance exists and it’s created automatically.

- **Companion object** – A singleton inside a class. It allows you to define static-like members that can be accessed via the class name without creating an instance.
</details>


<details>
<summary><strong>What's the purpose of sealed class?</strong></summary>

A sealed class is used to represent restricted hierarchies, where a type can have a fixed set of subclasses.

It’s useful for modeling state or handling results safely, like Success, Error, or Loading.

The compiler knows all subclasses, so when you use when, you don’t need an else.
</details>

<details>
<summary><strong>What's the difference between sealed class and enum class?</strong></summary>

- **Enum class** – Represents a fixed set of constants, usually without extra data or behavior.

- **Sealed class** – Can have a fixed set of subclasses, and each subclass can hold different data or behavior.

In short: enum = simple constants, sealed = more powerful, can hold data and logic.
</details>

<details>
<summary><strong>What is the inner keyword in Kotlin?</strong></summary>

inner is used for a nested class that can access variables and functions of the outer class.

Without inner, a nested class cannot see the outer class’s members.

So basically: inner class = nested class with access to outer class.
</details>

## Scope Functions

<details>
<summary><strong>Explain with, let, apply, also, and run scope functions</strong></summary>

- let uses it and returns the lambda result. I use it when I want to do something with an object and get a result, like safely getting the length of a nullable string.

- run uses this and also returns the lambda result. I use it when I want to configure or calculate something using the object.

- apply uses this and returns the original object. It’s great for initializing or setting up an object.

- also uses it and returns the original object. I use it for side effects like logging or validation without changing the object.

</details>

<details>
<summary><strong>What's the difference between apply and also?</strong></summary>

Both `apply` and `also` return the original object, but the difference is in how we reference the object inside the block:

- apply → uses this, so you can access properties directly. Great for initializing or configuring an object.

- also → uses it, so you usually use it for side actions like logging or validation without modifying the object.
</details>

<details>
<summary><strong>What's the difference between let and run?</strong></summary>

Both `let` and `run` return the result of the lambda, but the difference is in how you reference the object:

- `let` → uses it, good for working with a nullable object or getting a result.

- `run` → uses this, good for configuring or calculating something using the object.
</details>

## Advanced Kotlin

<details>
<summary><strong>What are generics? Can you create a generic function?</strong></summary>

Generics let us write flexible and type-safe code that works with different types without duplicating code.

```kotlin
fun <T> printItem(item: T) {
    println(item)
}

```
Here, `T` can be any type, so I can call` printItem(5)` or `printItem("Hello")`.

So, generics help reuse code safely for multiple types.
</details>

<details>
<summary><strong>What is type reification and why is it useful?</strong></summary>

type reification allows us to access the actual type of a generic at runtime, which is normally erased due to type erasure.

It’s useful when we want to check or cast types inside a generic function.

```kotlin
inline fun <reified T> isType(value: Any) = value is T
println(isType<String>("Hello")) // true

```
</details>

<details>
<summary><strong>What are delegated properties (e.g., by lazy, by viewModels())?</strong></summary>

Delegated properties let you delegate the getter and setter logic to another object instead of writing it yourself.

Examples:

by lazy – Initializes a property only when it’s first accessed.

```kotlin
val data by lazy { loadData() }
```
</details>

<details>
<summary><strong>How does by lazy work internally?</strong></summary>

by lazy works by creating a special delegate object that stores the lambda you provide.

The first time you access the property, the lambda is executed, the result is stored, and returned.

Next time, it returns the stored value without running the lambda again.

So basically, it delays initialization until needed and caches the result for future access.
</details>

<details>
<summary><strong>Explain lambdas and higher-order functions in functional programming</strong></summary>

Lambda is an anonymous function — a piece of code you can pass around as a value.
Example:

```
val sum = { a: Int, b: Int -> a + b }
println(sum(3, 4)) // 7
```

Higher-order functions are functions that take other functions as parameters or return a function.
Example:
```
fun operate(a: Int, b: Int, op: (Int, Int) -> Int) = op(a, b)
println(operate(3, 4) { x, y -> x + y }) // 7
```
So, lambdas are the function itself, and higher-order functions are functions that work with other functions.
</details>

<details>
<summary><strong>How does Kotlin handle exceptions differently from Java?</strong></summary>

Kotlin handles exceptions similarly to Java, but with one key difference:

In Java, we have checked exceptions (must be declared or handled) and unchecked exceptions.

In Kotlin, all exceptions are unchecked — you don’t need to declare them or catch them explicitly.

So Kotlin makes exception handling simpler and less boilerplate, but you still use try-catch the same way.
</details>

<details>
<summary><strong>What is typealias and when would you use it?</strong></summary>

typealias lets you give a new name to an existing type.

```kotlin
typealias Callback = (Int, String) -> Unit
fun register(callback: Callback) { ... }
```
We use it to make complex or long types easier to read and improve code clarity.
</details>

<details>
<summary><strong>Explain operator overloading in Kotlin</strong></summary>

typealias lets you give a new name to an existing type.

```kotlin
typealias Callback = (Int, String) -> Unit
fun register(callback: Callback) { ... }
```
We use it to make complex or long types easier to read and improve code clarity.
</details>

<details>
<summary><strong>What is immutability and how does copy() help?</strong></summary>

Immutability means an object cannot be changed after it’s created. This makes code safer and predictable.

In Kotlin, data classes are often immutable. If you want a modified version, you use copy():

```kotlin
val user1 = User("Pratik", 25)
val user2 = user1.copy(age = 26)
```
</details>


# LEVEL 3: Android Application Components (Must Know Cold)

## Application Fundamentals

<details>
<summary><strong>What happens when you tap on an app icon?</strong></summary>

When you tap an app icon:

- The Launcher (home screen) sends an Intent to start the app’s main activity.
- The Android system looks at the app’s manifest to find the launcher activity.
- A process is created (if not already running) and the Activity lifecycle starts (onCreate, onStart, onResume).
- The UI is drawn, and the app becomes visible to the user.

So basically: tap → intent → process/activity → UI shows up.
</details>


<details>
<summary><strong>Explain the Android Application Lifecycle (from launch to kill)</strong></summary>

The Android application lifecycle starts when you tap the app icon. First, the system creates the process and launches the main activity. The activity goes through onCreate, onStart, and onResume, and then the app is visible and interactive.

When the user switches away, the activity may go through onPause and onStop. Finally, if the system needs memory, it can call onDestroy and kill the process.

So basically, the app goes from launch → create → start → resume → pause/stop → destroy.
</details>

<details>
<summary><strong>What's the difference between compileSdkVersion, targetSdkVersion, and minSdkVersion?</strong></summary>

- **compileSdkVersion** is the API level we use to compile the app, so we can use all the latest APIs.

- **minSdkVersion** is the lowest Android version the app can run on — devices below this cannot install it.

- **targetSdkVersion** is the version the app is tested and optimized for, and it tells the system how to handle compatibility behavior on newer Android versions.
</details>

<details>
<summary><strong>Explain how an APK is built and signed</strong></summary>

When we build an APK, first the code and resources are compiled into DEX files. Then everything, including XML, images, and the manifest, is packaged into an APK. After that, it’s optimized with zipalign for performance. Finally, the APK is signed with a keystore so Android knows it’s from a trusted source.

</details>

<details>
<summary><strong>What happens under the hood when you install an APK?</strong></summary>

When you install an APK, first the Package Manager verifies the app’s signature. Then the APK is unzipped and its DEX files are optimized for the device. The resources are extracted and the system creates storage and sets permissions. Finally, the app is registered, so it can be launched.

</details>

<details>
<summary><strong>What is the Android manifest merging process?</strong></summary>

The Android manifest merging process happens when your app uses multiple manifests, like the main app manifest, library manifests, and build-specific manifests.

During build:

- The system combines all manifests into a single final manifest.
- It resolves conflicts using rules like tools:replace or tools:remove.
- The final manifest is then used for compiling and building the APK.

</details>

<details>
<summary><strong>What happens if two libraries define the same permission?`</strong></summary>

If two libraries define the same permission, Android merges them automatically into the final manifest.

- There’s no conflict because the permission is the same.
- If they were different or conflicting attributes, you might need to use tools:replace to resolve it.

So basically: same permission → merged automatically, no problem.
</details>

## Context

<details>
<summary><strong>What is Context in Android?</strong></summary>

In Android, Context is basically a handle to the system. It lets your app access resources, start activities, use services, or get preferences.

For example, an Activity, Service, or Application is a Context.

</details>

<details>
<summary><strong>What's the difference between Application Context and Activity Context?</strong></summary>

Activity Context is tied to the lifecycle of an activity. Use it when you need something UI-related, like inflating layouts or showing dialogs.

Application Context is tied to the lifecycle of the app. Use it for things that need to live longer than an activity, like starting services, accessing databases, or singletons.
</details>


<details>
<summary><strong>What are the different types of Context in Android?</strong></summary>

In Android, the main two types of Context are:

- Activity Context – tied to an activity’s lifecycle, used for UI-related operations.

- Application Context – tied to the app’s lifecycle, used for app-wide operations like services or singletons.
</details>

<details>
<summary><strong>How do you avoid memory leaks with Context?</strong></summary>

To avoid memory leaks with Context:

- Don’t hold a long-lived reference to an Activity Context; use Application Context if needed.
- Be careful with static variables or singletons holding references to activities or views.
- Unregister listeners or callbacks in onDestroy() or onStop().
- Avoid anonymous inner classes or long-running threads that reference an activity.

</details>

## Activity Lifecycle

<details>
<summary><strong>Explain the Activity lifecycle in detail</strong></summary>

The Activity lifecycle defines how an Activity behaves from the moment it’s created until it’s destroyed.

- **onCreate()** – This is called when the activity is first created. You set up your UI, initialize data, and prepare things like View Binding or ViewModels.

- **onStart()** – The activity becomes visible to the user but is not yet in the foreground.

- **onResume()** – The activity is now in the foreground and ready for user interaction. This is where you start animations or camera previews.

- **onPause()** – The activity is partially visible, maybe because another activity is coming on top. You should pause animations or release temporary resources here.

- **onStop()** – The activity is no longer visible. You should stop heavy tasks or background updates to save resources.

- **onDestroy()** – The activity is finishing or being destroyed by the system. Clean up any remaining resources here.

- **onRestart()** – Called when the activity is coming back to the foreground after being stopped.

</details>


<details>
<summary><strong>What happens during Activity rotation?</strong></summary>

When an Activity rotates, like when you turn your phone from portrait to landscape, Android treats it as a configuration change.

That means the current Activity is destroyed and recreated.

**So the sequence is:**
👉 `onPause()` → `onStop()` → `onDestroy()` — then Android restarts it — → `onCreate()` → `onStart()` → `onResume()`.

This happens because things like layout dimensions, screen orientation, and resources may change.

To preserve data, we usually use:

- **ViewModel**, which survives rotation,
- **onSaveInstanceState()** to save small UI data,

</details>

<details>
<summary><strong>What happens during Activity rotation?</strong></summary>

When an Activity rotates, like when you turn your phone from portrait to landscape, Android treats it as a configuration change.

That means the current Activity is destroyed and recreated.

**So the sequence is:**
👉 `onPause()` → `onStop()` → `onDestroy()` — then Android restarts it — → `onCreate()` → `onStart()` → `onResume()`.

This happens because things like layout dimensions, screen orientation, and resources may change.

To preserve data, we usually use:

- **ViewModel**, which survives rotation,
- **onSaveInstanceState()** to save small UI data,

</details>

<details>
<summary><strong>What happens during back press?</strong></summary>

When you press the back button, Android starts the Activity finish process.

So first, it calls the Activity’s onPause(), then onStop(), and finally onDestroy() — which means the Activity is removed from the back stack.

If there’s another Activity underneath in the stack, that one becomes visible again and goes through onRestart() → onStart() → onResume().

If the current Activity is the last one in the task, then pressing back will close the app and the task goes to the background.

</details>

<details>
<summary><strong>What happens during multitasking?</strong></summary>

When multitasking happens — like when you switch between apps — Android manages Activities using the activity stack system.

So, when your app goes into the background, the current Activity’s onPause() is called first, then onStop() — meaning it’s no longer visible, but it’s still kept in memory.

If the user switches back to your app, Android simply calls onRestart() → onStart() → onResume(), and your Activity becomes visible again.

However, if the system needs memory, it might kill your process while your app is in the background.
In that case, when the user returns, your app restarts from scratch, but you can restore data using savedInstanceState or ViewModel.

</details>

<details>
<summary><strong>What's the difference between onCreate() and onStart()?</strong></summary>

- **onCreate()** is called only once when the Activity is created for the first time.

You usually use it to set up your UI, like using setContentView(), initializing variables, binding views, and restoring any saved data.

- **onStart()**, on the other hand, is called every time the Activity becomes visible to the user — even after coming back from the background.

You use it to start tasks that need to run when the Activity is visible — like starting animations, or registering broadcast receivers.

</details>

<details>
<summary><strong>What's the difference between onStart() and onResume()?</strong></summary>

- **onStart()** is called every time the Activity becomes visible to the user — even after coming back from the background.

You use it to start tasks that need to run when the Activity is visible — like starting animations, or registering broadcast receivers.

- **onResume()**  is called right after **onStart()** — when the Activity comes to the foreground and the user can start interacting with it (like tapping buttons or typing).

</details>

<details>
<summary><strong>What's the difference between onPause() and onStop()?</strong></summary>

- onPause() is called when the Activity is partially visible — for example, the user switches to another app 
At this stage, your app is still visible but not interactive.

- onStop() happens after that — when your Activity is no longer visible at all on the screen.

</details>

<details>
<summary><strong>What happens when you press the Home button?</strong></summary>

When you press the Home button, your current activity doesn’t get destroyed — it just goes into the background.

- The system first calls `onPause()`, meaning your app is no longer in the foreground.
- Then it calls `onStop()`, because the activity is now completely invisible.

Your app is still kept in memory, so when you come back, it usually resumes from where you left off — calling onRestart() → onStart() → onResume().

</details>

<details>
<summary><strong>How does onSaveInstanceState() work?</strong></summary>

- `onSaveInstanceState()` is called right before your activity is about to be destroyed — for example, during screen rotation or when the system needs to reclaim memory.

It’s used to save small, temporary UI data like scroll position, text input, or selected items, so that when the activity is recreated, you can restore the same state.

</details>

<details>
<summary><strong>How does onRestoreInstanceState() work?</strong></summary>

- `onRestoreInstanceState()` is called after `onStart()`, only when there’s actually saved data from onSaveInstanceState().

It’s used to restore the UI state — like putting back text in a textbox or scrolling to the same position after rotation.

</details>

<details>
<summary><strong>How do you handle configuration changes?</strong></summary>

When a configuration change happens, like screen rotation, Android by default destroys and recreates the activity.

To handle this, I usually do one of three things:

- Use ViewModel to store data, because it survives rotation automatically.
- Use onSaveInstanceState() to save small UI state, like text input or scroll position, and restore it in onCreate() or onRestoreInstanceState().
- In rare cases, handle it manually by adding android:configChanges="orientation|screenSize" in the manifest and override onConfigurationChanged() — but this is only for special cases like camera or video.

</details>

<details>
<summary><strong>What happens if the app is in background and a call comes?</strong></summary>

When your app is in the background and a call comes:

- Your activity is already stopped or paused, so it’s not visible.
- The system keeps your app in memory, but may pause any running tasks if needed to free resources.
- If the system needs memory, it might kill your process, but you can restore data using ViewModel or onSaveInstanceState() when the user returns.

So basically: incoming call → your app stays in background → may pause or get killed → restored when user comes back.

</details>

## Launch Modes & Task Management

<details>
<summary><strong>What are launchModes in Android? Explain each</strong></summary>

Launch modes control how activities are launched and placed in the back stack. There are four main types:

- **standard (default)** – Every time you start the activity, a new instance is created and pushed onto the back stack.

- **singleTop** – If the activity is already at the top of the stack, it reuses that instance instead of creating a new one. Otherwise, a new instance is created.

- **singleTask** – There will be only one instance in the entire system. If it exists, it is brought to the front, and everything above it in the stack is cleared.

- **singleInstance** – Similar to singleTask, but the activity is the only one in its task. Any activity started from it opens in a separate task.

</details>

<details>
<summary><strong>What's the difference between singleTop and singleTask?</strong></summary>

- **singleTop** – If the activity is already at the top of the stack, it reuses the same instance. If it’s not on top, a new instance is created.

- **singleTask** – There can be only one instance in the entire system. If it already exists anywhere in the stack, that instance is brought to the front, and all activities above it are cleared.

</details>

<details>
<summary><strong>What are TaskAffinity and Intent Flags?</strong></summary>

- TaskAffinity is basically a name for the task an activity “belongs” to. Most activities in your app go into the same task, but if you want an activity to open in a different task, you can change its taskAffinity in the manifest.

- Intent Flags are like special instructions you give when starting an activity. They tell Android how to launch it and handle the back stack.

</details>

<details>
<summary><strong>How does FLAG_ACTIVITY_CLEAR_TOP work?</strong></summary>

FLAG_ACTIVITY_CLEAR_TOP is used when you start an activity that already exists in the back stack.

What happens:
- Android finds the existing instance of that activity in the stack.
- It removes all activities above it.
- The existing activity is brought to the top and onNewIntent() is called.

Example:

- Stack: A → B → C → D
- Start B with CLEAR_TOP
- Resulting stack: A → B
- C and D are removed.

</details>

## Fragment

<details>
<summary><strong>What is Activity?</strong></summary>

- An Activity is basically a single screen in an app where the user can interact with the UI.
- It’s the entry point for user interaction.
- It has its own lifecycle to manage creation, pause, resume, and destruction.

</details>

<details>
<summary><strong>What is Fragment?</strong></summary>

A Fragment is a reusable portion of UI inside an Activity.
It has its own lifecycle, can handle its own UI and logic, and allows you to divide your screen into smaller, modular components.

For example, on a tablet, you can show two fragments side by side in one activity.

</details>

<details>
<summary><strong>Explain the Fragment lifecycle</strong></summary>

A Fragment is a reusable portion of UI inside an Activity.
It has its own lifecycle, which is closely tied to the Activity lifecycle.

- `onAttach()` – Fragment is attached to the activity.
- `onCreate()` – Initialize essential data not related to UI.
- `onCreateView()` – Inflate the fragment’s layout.
- `onViewCreated()` – UI is ready; set up listeners or adapters.
- `onStart()` – Fragment becomes visible.
- `onResume()` – Fragment is active and interactive.
- `onPause()` – Fragment is partly visible, user can’t interact.
- `onStop()` – Fragment is not visible.
- `onDestroyView()` – Clean up view-related resources.
- `onDestroy()` – Clean up remaining resources.
- `onDetach()` – Fragment is detached from the activity.

</details>

<details>
<summary><strong>What are the differences between Fragment and Activity lifecycle?</strong></summary>

- **Attachment** – Fragments have onAttach() and onDetach(), because they are attached to an activity. Activities don’t have this.

- **View lifecycle** – Fragments have onCreateView() and onDestroyView() to manage their UI. Activities just use onCreate() and onDestroy().

- **Tied to Activity** – A fragment’s lifecycle is directly dependent on the hosting activity. If the activity is destroyed, the fragment is destroyed too.

</details>

<details>
<summary><strong>How do you communicate between two fragments?</strong></summary>

Fragments should not talk directly. The main ways to communicate are:

- Through the Activity – Fragment A tells Activity, Activity passes to Fragment B.
- Shared ViewModel – Both fragments use the same ViewModel; one updates, the other observes.
- Fragment Result API – Fragment A sets a result, Fragment B listens for it.

</details>

<details>
<summary><strong>What is a retained Fragment?</strong></summary>

A retained fragment is a fragment that survives configuration changes like screen rotation.

- You set it using setRetainInstance(true).
- Its instance and data are kept, so you don’t lose things like ongoing tasks or network calls when the activity is recreated.

</details>

<details>
<summary><strong>How to handle fragment transactions properly?</strong></summary>

To handle fragment transactions properly:

- Use FragmentManager to add, replace, or remove fragments.
- Always call commit() or commitAllowingStateLoss() at the right time.
- Use addToBackStack() if you want the user to navigate back.

</details>

## Intent

<details>
<summary><strong>What is an Intent?</strong></summary>

An Intent is a messenger that tells Android what you want to do. In other words, you describe your intention

It can be used to start an activity, start a service, or send a broadcast.

There are two types of Intent:
- Explicit Intent → Explicit Intent is used to call a specific component when you know exactly which one to launch.
For example, from Activity A to Activity B, you create an explicit intent targeting Activity B.

- Implicit Intent → Implicit Intent defines the action you want to perform instead of a specific component.
The system decides which component can handle it, like sharing text or opening a URL.
</details>

<details>
<summary><strong>What are IntentFilters?</strong></summary>

intent filter is expression which present in manifest in your app that specify the type of intents that the component is to receive. If component does not have any intent filter it can receive explicit intent. If component with filter then receive both implicit and explicit intent
</details>

<details>
<summary><strong>What is a PendingIntent?</strong></summary>

A PendingIntent is like a token that you give to another app or the system to execute later on your app’s behalf.

- It’s commonly used in notifications, alarms, or widgets.
- Even if your app is not running, the system can use the PendingIntent to start your activity, service, or broadcast.
</details>

<details>
<summary><strong>What's the difference between startActivity() and startActivityForResult()?</strong></summary>

- startActivity() is used when you just want to open another activity — for example, going from Home to Settings. You don’t expect any data back.
- startActivityForResult() is used when you expect a result back from the opened activity.
For example, if you open the gallery to pick an image, you’ll get that selected image back in onActivityResult().
</details>

<details>
<summary><strong>What is the Activity Result API (modern replacement)?</strong></summary>

The Activity Result API is the modern way to start another activity and get a result back — it replaces the old startActivityForResult() and onActivityResult() methods.

Instead of overriding methods, you register a launcher using registerForActivityResult() and pass in a contract (like StartActivityForResult(), TakePicture(), etc.).

When the result comes back, you get it directly in a callback — which makes the code cleaner and lifecycle-safe.
</details>

## Services

<details>
<summary><strong>What's the difference between Service, IntentService, and JobIntentService?</strong></summary>

- A Service runs tasks in the background even if there’s no user interface — like playing music or downloading files.
But it runs on the main thread by default, so if your work is heavy, you must manually move it to a background thread.

- An IntentService is a subclass of Service that automatically runs work on a background thread and stops itself when the job is done. It’s good for simple one-off background tasks.
However, it’s deprecated now because it’s not very battery-friendly and doesn’t work well with newer Android versions.

- A JobIntentService was introduced to fix that — it works like an IntentService but schedules the work properly using the JobScheduler API, so it’s safer for Android 8.0+ and follows background limits.
</details>

<details>
<summary><strong>What are the different types of services? (Started, Bound, Foreground)</strong></summary>

- A Started Service runs in the background once started and doesn’t return any result — like playing music or downloading a file.
- A Bound Service allows components like activities to bind and interact with it — it’s used when you need two-way communication, like controlling media playback.
- A Foreground Service keeps running with a visible notification, so the user knows it’s active — for example, navigation or fitness tracking.
</details>

<details>
<summary><strong>When should you use a foreground service vs background service?</strong></summary>

- You should use a foreground service when your task is important to the user and must keep running even if the app is in the background — like playing music, tracking location, or recording video.

- A background service is for short, less critical tasks that don’t need user awareness — like syncing data or uploading logs.
</details>

<details>
<summary><strong>How does a bound service work?</strong></summary>

- A bound service works by allowing other components like activities or fragments to bind to it and communicate directly using an interface.

- When a component calls bindService(), the system creates a connection, and the service returns an IBinder that the client uses to call methods inside the service.

- It stays alive only while something is bound to it, and once all clients unbind, the service is destroyed.
</details>

## BroadcastReceiver

<details>
<summary><strong>What are BroadcastReceivers used for?</strong></summary>

- A BroadcastReceiver is used to listen for and respond to system-wide or app-wide events.

- For example, it can detect when the device connects to Wi-Fi, battery is low, or when your app sends a custom broadcast.

- It runs only when the event occurs and doesn’t stay active all the time
</details>

<details>
<summary><strong>What are the use cases and pitfalls of BroadcastReceiver?</strong></summary>

- Use cases: BroadcastReceivers are great for reacting to system events like network changes, boot completed, or custom in-app broadcasts

- Pitfalls: They can cause memory leaks if registered incorrectly, especially in activities, and performance issues if they do heavy work on the main thread.
</details>

<details>
<summary><strong>What's the difference between manifest-registered and context-registered receivers?</strong></summary>

- A manifest-registered receiver is declared in the AndroidManifest, so it can listen to system events even when the app isn’t running — like BOOT_COMPLETED or CONNECTIVITY_CHANGE.

- A context-registered receiver is registered in code using registerReceiver() — it only works while the app or activity is alive, and you must unregister it in onPause() or onStop() to avoid leaks.
</details>

<details>
<summary><strong>How do you register a BroadcastReceiver dynamically?</strong></summary>

- You can register a BroadcastReceiver dynamically in code using `registerReceiver()`.

- You usually do this inside `onStart()` or `onResume()`, and don’t forget to unregister it in `onStop()` or `onPause()` using `unregisterReceiver()` to avoid memory leaks.
</details>

## ContentProvider

<details>
<summary><strong>What are ContentProviders and where are they used?</strong></summary>

- A ContentProvider is a component that shares data between apps in a controlled way.

- It provides a standard interface to access data like databases, files, or other storage using URIs.

- Common use cases include accessing contacts, calendar, or media files from another app.
</details>

## IPC & System

**There is another repo for this related question Please refer it**

## Application Class

<details>
<summary><strong>What is the Application class and its lifecycle?</strong></summary>

- The Application class is the base class for your app — there’s only one instance per app process. It’s created before any activity, service, or receiver runs.

- Its lifecycle starts when the app process is created and ends when the process is killed.

- You can override methods like `onCreate()` to initialize global resources, like singletons, databases, or analytics.
</details>

<details>
<summary><strong>What's the difference between Application class and Singleton object?</strong></summary>

- The Application class is an Android component that exists for the entire app process and is managed by the system. You use it to initialize global resources when the app starts.

- A Singleton object is a language-level construct (like Kotlin’s object) that ensures only one instance exists and can be used anywhere in the app.
</details>

<details>
<summary><strong>When should you use the Application class?</strong></summary>

You use the Application class when you want to set up something once for the whole app.

For example, you can initialize a database, analytics, or dependency injection there. You can also keep global state that all activities and services can access.
</details>

# LEVEL 4: UI & View System/

## Layout Basics

<details>
<summary><strong>What's the difference between Margin and Padding?</strong></summary>

- Margin is the space outside a view — it creates distance from other views.
- Padding is the space inside a view — it creates distance between the view’s content and its border.
</details>

<details>
<summary><strong>How do you handle multiple screen sizes (mobile vs tablet vs TV)?</strong></summary>

To handle multiple screen sizes in Android, I use responsive layouts and resource qualifiers. I provide different layouts and dimensions in folders like layout-sw600dp for tablets or layout-xhdpi for high-density screens.

 I use ConstraintLayout or Compose’s responsive modifiers to make UI flexible. For TV, I use leanback support libraries and larger touch targets. 
 
 I also test on multiple devices and emulators to ensure proper scaling and usability. This ensures the app looks good and works correctly on mobile, tablet, and TV

</details>

<details>
<summary><strong>How do you support different screen sizes and densities?</strong></summary>

I support different screen sizes and densities using density-independent pixels (dp) and scalable pixels (sp) for layouts and text. 

I provide alternative resources like drawable-mdpi, drawable-xhdpi, layout-sw600dp for tablets, and values folders with different dimens.xml. 

I also use ConstraintLayout or Compose’s responsive modifiers to make UI flexible across devices, ensuring consistent appearance on all screens

</details>

<details>
<summary><strong>Explain layout inflation process</strong></summary>

Layout inflation in Android is the process of converting an XML layout file into corresponding View objects in memory. When we call LayoutInflater.inflate() or setContentView(), Android reads the XML, creates all the Views defined, and sets up their properties and hierarchy. This allows us to work with Views programmatically.

</details>

## View Rendering

<details>
<summary><strong>Explain the Android View rendering process (measure → layout → draw)</strong></summary>

Layout inflation in Android is the process of converting an XML layout file into corresponding View objects in memory. When we call LayoutInflater.inflate() or setContentView(), Android reads the XML, creates all the Views defined, and sets up their properties and hierarchy. This allows us to work with Views programmatically.

</details>

<details>
<summary><strong>What's the use of requestLayout() and invalidate()?</strong></summary>

- `requestLayout()` tells the system that the View’s size or position has changed, triggering a measure → layout → draw cycle.

- `invalidate()` tells the system that the View’s appearance has changed, so it needs to redraw, calling `onDraw()` without re-measuring or re-layout.

</details>

## ConstraintLayout

<details>
<summary><strong>What is ConstraintLayout and how does it improve performance?
</strong></summary>

- ConstraintLayout is a flexible Android layout that lets you position and size Views using constraints relative to other Views or the parent. 

- It reduces the need for nested layouts, which decreases the view hierarchy depth, improving layout performance and rendering speed. It also supports features like chains, barriers, and guidelines, making complex UIs easier to build without multiple nested LinearLayouts or RelativeLayouts

</details>

<details>
<summary><strong>What are the advantages of ConstraintLayout over RelativeLayout and LinearLayout?
</strong></summary>

- It reduces nested layouts, flattening the view hierarchy for better performance.
- It allows flexible positioning using constraints, chains, and guidelines, which is more powerful than RelativeLayout.
- Unlike LinearLayout, it can align and distribute Views both horizontally and vertically without extra wrappers.
- It improves layout performance and makes complex UIs easier to maintain and adapt to different screen sizes.”

</details>

## RecyclerView

<details>
<summary><strong>What is RecyclerView? How does it differ from ListView?
</strong></summary>

- RecyclerView is a flexible and efficient ViewGroup for displaying large lists in Android. 

Unlike ListView, it recycles item views using ViewHolder to improve performance, supports different layout managers (linear, grid, staggered), and provides built-in animations for adding or removing items.

</details>

<details>
<summary><strong>What is DiffUtil in RecyclerView?
</strong></summary>

DiffUtil is a utility class in Android that calculates the difference between two lists and outputs a minimal set of updates for a RecyclerView adapter. 

Instead of calling notifyDataSetChanged() and redrawing the whole list, DiffUtil lets us update only the changed items, improving performance and enabling smooth animations when the list updates

</details>

<details>
<summary><strong>How to update only a specific item in RecyclerView efficiently?
</strong></summary>

To update a specific item efficiently in RecyclerView, you should use notifyItemChanged(position) instead of notifyDataSetChanged(). This tells the adapter to redraw only that item. 

For more complex scenarios, you can use DiffUtil to calculate changes and update only the affected items, ensuring smooth animations and better performance

</details>

## View Binding & Data Binding

<details>
<summary><strong>What is ViewBinding?
</strong></summary>

ViewBinding is a feature in Android that generates a binding class for each XML layout, giving type-safe references to all views. It replaces `findViewById()` calls, reduces boilerplate

</details>

<details>
<summary><strong>What is DataBinding?
</strong></summary>

DataBinding is an Android feature that binds UI components in XML directly to data sources, such as ViewModel or LiveData. It allows you to write expressions in XML and reducing boilerplate code

It supports two-way binding, letting UI and data update each other automatically, which improves code clarity, maintainability, and reactive UI updates.

</details>

<details>
<summary><strong>What's the difference between ViewBinding and DataBinding?
</strong></summary>

ViewBinding only provides type-safe references to views in XML, replacing findViewById() without any logic or data binding.

 on the other hand DataBinding, lets you bind UI components directly to data sources (like LiveData or ViewModel) and supports two-way binding, allowing UI and data to update automatically. 
 
 ViewBinding is simpler, while DataBinding is more powerful for reactive UI.

</details>

<details>
<summary><strong>What are the advantages of ViewBinding over findViewById?
</strong></summary>

ViewBinding offers several advantages over findViewById():

- Type safety — no need to cast views manually.
- Null safety — prevents null pointer exceptions.
- Less boilerplate — eliminates repetitive findViewById() calls.

</details>

<details>
<summary><strong>What are the advantages of ViewBinding over findViewById?
</strong></summary>

ViewBinding offers several advantages over findViewById():

- Type safety — no need to cast views manually.
- Null safety — prevents null pointer exceptions.
- Less boilerplate — eliminates repetitive findViewById() calls.

</details>

<details>
<summary><strong>How would you implement a dark theme in a app?
</strong></summary>

I’d implement a dark theme using the Material Design guidelines. I define separate color schemes for light and dark themes, then apply them through the app’s theme setup. In XML-based apps, I use `AppCompatDelegate` to switch between light and dark modes, and in Jetpack Compose I use `isSystemInDarkTheme()` with MaterialTheme. The user’s preference is stored in DataStore or SharedPreferences so it persists across app restarts

</details>

<details>
<summary><strong>How do you debug UI rendering performance issues?
</strong></summary>

To debug UI rendering performance issues, I use tools like Layout Inspector and Profile GPU Rendering in Android Studio to identify overdraw, slow rendering, and layout complexity. I also enable Show layout bounds to check nested layouts, and use Systrace or the System Tracing tool for frame drops. Optimizing includes reducing nested views, using ConstraintLayout, reusing views, and avoiding heavy work on the main thread

</details>

<details>
<summary><strong>How do you handle localization?
</strong></summary>

I handle localization by moving all text to strings.xml and creating separate string files for each language. I never hardcode text and use getString() for retrieval. I also ensure proper formatting for dates, numbers, and support RTL layouts. For dynamic language change, I update the app’s locale and recreate the context

</details>

# LEVEL 5: Jetpack Compose (Modern UI)

## Compose Basics

<details>
<summary><strong>What is Jetpack Compose?
</strong></summary>

Jetpack Compose is Android’s modern UI toolkit that lets you build native UIs using declarative programming in Kotlin. Instead of XML layouts, you describe how the UI should look, and Compose automatically updates it when data changes

</details>

<details>
<summary><strong>How is Compose different from the legacy View system?
</strong></summary>

Compose is declarative, while the legacy View system is imperative. In Compose, the UI automatically updates when state changes, whereas in the View system you manually update views. Compose uses Kotlin code instead of XML, has less boilerplate, better reusability, and integrates naturally with state management and lifecycle, leading to faster and cleaner UI development

</details>

<details>
<summary><strong>What is recomposition and how does it work?
</strong></summary>

Recomposition in Jetpack Compose means the UI automatically redraws when the data or state changes. Compose re-executes only the affected parts of the UI to reflect the new state. It’s efficient because Compose skips recomposing unchanged parts, ensuring smooth performance

</details>

<details>
<summary><strong>What is State Hoisting in Compose?
</strong></summary>

State hoisting in Jetpack Compose means moving a state variable out of a composable to a higher level, so the parent controls the state. This makes the composable stateless and reusable. It’s usually done by passing the current value and a callback (like onValueChange) from the parent

</details>


<details>
<summary><strong>Explain remember and rememberSaveable
</strong></summary>

- `remember` and `rememberSaveable` are both used in Jetpack Compose to store state values across recompositions.
- `remember` keeps the state only in memory — it’s lost when the configuration changes like screen rotation.
- on the other hand `rememberSaveable`, uses a `SavedStateHandle` or `Bundle` to automatically save and restore the state after configuration changes

**💡 In short:**

- `remember` → survives recomposition
- `rememberSaveable` → survives recomposition and configuration changes

</details>


<details>
<summary><strong>Explain remember and rememberSaveable
</strong></summary>

- `remember` and `rememberSaveable` are both used in Jetpack Compose to store state values across recompositions.
- `remember` keeps the state only in memory — it’s lost when the configuration changes like screen rotation.
- on the other hand `rememberSaveable`, uses a `SavedStateHandle` or `Bundle` to automatically save and restore the state after configuration changes

**💡 In short:**

- `remember` → survives recomposition
- `rememberSaveable` → survives recomposition and configuration changes

</details>

## Side Effects

<details>
<summary><strong>What is SideEffect and when to use it?
</strong></summary>

- `SideEffect` is used in Compose to run code that affects things outside of Compose, like updating logs, analytics, or external variables. It runs after every successful recomposition, ensuring your UI is stable before the side effect happens.

</details>

<details>
<summary><strong>What is LaunchedEffect and when to use it?
</strong></summary>

- `LaunchedEffect` is a side-effect API in Jetpack Compose. It is used in Compose to run suspend functions or side effects when a composable first appears or when a key changes. Common uses include fetching data, showing snackbars, or running animations.”

</details>

<details>
<summary><strong>What is disposableEffetc when to use it
</strong></summary>

- `DisposableEffect` in Jetpack Compose is used when you need to perform a setup when a composable enters the composition and clean up when it leaves. It’s lifecycle-aware and great for things like registering listeners, starting observers, or managing resources that need to be released later.

</details>

<details>
<summary><strong>What are the different side effect handlers in Compose?
</strong></summary>

Jetpack Compose provides several side-effect handlers to manage tasks that happen outside the composable lifecycle. The main ones are:

- **LaunchedEffect** – runs suspend functions when a key changes or composable enters composition.
- **rememberCoroutineScope** – provides a coroutine scope to launch tasks manually from UI events.
- **SideEffect** – runs non-suspending code after every successful recomposition.
- **DisposableEffect** – runs setup and cleanup code tied to the composable’s lifecycle.
- **ProduceState** – converts non-Compose data sources (like Flow) into Compose state.
- **derivedStateOf** – optimizes recomposition by deriving new state only when dependent values change.”

💡 In short:

- Each effect handles side tasks differently — `LaunchedEffect` for suspend work, `SideEffect` for UI-safe changes, `DisposableEffect` for cleanup, and `ProduceState` for bridging external data.

</details>

## Performance

<details>
<summary><strong>How to optimize Compose performance?
</strong></summary>

To optimize Compose performance, I minimize unnecessary recompositions, use remember and derivedStateOf to cache state, and keep composables small and stateless when possible.

I use LazyColumn instead of Column for large lists, avoid heavy work inside composables, and use tools like the Recomposition Counter or Layout Inspector to detect over-recompositions

</details>

<details>
<summary><strong>How to control recomposition in Compose? // How to reduce recompositions in Compose?
</strong></summary>

Recomposition happens when a state used by a composable changes. While it’s automatic, too much recomposition can slow your app
- To control recomposition in Jetpack Compose, I make sure to use remember to store state so it doesn’t reset on every recompositio.
- I also use derivedStateOf when I need to compute derived values efficiently.
- Then, I hoist the state up so that only the necessary composables recompose, not the entire hierarchy.
- Additionally, I keep my composables small, pass only stable data, and use immutable data classes to help minimize unnecessary recompositions
- Avoid creating new lambdas or objects inside composables — instead, use remember { } or rememberUpdatedState().
- Split your UI into smaller composables so only affected parts recompose.
- Mark stable classes with @Stable or @Immutable when appropriate.

</details>


<details>
<summary><strong>What is derivedStateOf and when to use it?
</strong></summary>

derivedStateOf in Jetpack Compose is used to create a value that automatically updates only when its dependent state changes. It helps avoid unnecessary recompositions.

For example, if you’re calculating something based on another state — like filtering a list — you can wrap it in derivedStateOf so Compose only recomposes when that input state changes, not on every recomposition.

</details>

<details>
<summary><strong>What is recomposition skipping in Compose?
</strong></summary>

Recomposition skipping in Jetpack Compose means Compose won’t re-execute a composable if its input data (state or parameters) hasn’t changed

For example, if your UI depends on a count value and the count hasn’t changed, Compose will skip that recomposition.

</details>

<details>
<summary><strong>How to ensure smooth scrolling with large data in Compose list?
</strong></summary>

To ensure smooth scrolling with large data in Jetpack Compose, you should use LazyColumn or LazyVerticalGrid, since they only compose visible items — not the whole list at once.
Also follow
- Use stable keys with key = { item.id } so Compose can reuse item layouts.
- Keep each item’s UI lightweight and avoid heavy recompositions inside items.
- Don’t put large business logic or network calls inside the item composable.
- And if the list is really big, paginate your data using Paging 3 with Compose.

</details>

## Integration

<details>
<summary><strong>How does ViewModel + Compose interaction work?
</strong></summary>

In Jetpack Compose, the ViewModel acts as the source of truth for UI data. It exposes State objects — usually StateFlow, LiveData, or MutableState — that the composables observe.

You use functions like collectAsState() or observeAsState() inside composables to automatically recompose the UI whenever the ViewModel data changes.

The key idea is — ViewModel holds the data and logic, while Compose just reacts to those state updates, keeping the UI declarative and lifecycle-aware.

</details>

<details>
<summary><strong>How do you handle themes, dark mode, and configuration changes in Compose?
</strong></summary>

In Jetpack Compose, themes and dark mode are handled using the MaterialTheme system. You define light and dark color schemes, typography, and shapes in your theme setup.

Compose automatically reacts to system dark mode using isSystemInDarkTheme(), so you can switch between light and dark themes dynamically.

For configuration changes like rotation or locale changes, Compose works with ViewModel and rememberSaveable() to retain state. Since Compose is lifecycle-aware, it automatically recomposes when configuration changes occur — keeping the UI consistent without manual handling.

</details>

<details>
<summary><strong>How to implement dark mode dynamically in Compose?
</strong></summary>

To implement dark mode dynamically in Compose, you can maintain a theme state in your ViewModel or remember it in the UI using `remember { mutableStateOf(isSystemInDarkTheme()) }`.

Then, wrap your UI in a `MaterialTheme` and switch between light and dark color schemes based on that state.

When the user toggles dark mode, just update the state — Compose will recompose automatically, applying the new theme instantly across the app

</details>

<details>
<summary><strong>How to handle navigation in Compose?
</strong></summary>

In Jetpack Compose, navigation is handled using the Navigation Component for Compose. You set up a NavHost with a NavController, then define composable destinations using the composable() function.

You navigate between screens using navController.navigate("route"), and you can pass arguments or handle back navigation easily.

</details>

# LEVEL 6: Architecture & Design Patterns

## Architecture Patterns

<details>
<summary><strong>Which architecture pattern do you prefer and why?
</strong></summary>

I prefer MVVM because it fits naturally with Android’s architecture components like ViewModel, LiveData, and Flow.

It keeps the UI (View) and logic (ViewModel) separate — making the code cleaner, testable, and lifecycle-aware.

Also, it works perfectly with Jetpack Compose and DataBinding, allowing the UI to automatically react to state changes without manual updates

</details>

<details>
<summary><strong>Explain MVVM pattern with a detailed example
</strong></summary>

MVVM stands for Model–View–ViewModel. It separates UI from logic using three layers:

**Model** → Handles data (API, database, repository).

**View** → Displays UI and observes changes.

**ViewModel** → Holds UI data and business logic, exposes it as LiveData or StateFlow to the View.

For example —
In a weather app:

- The Model fetches weather data from an API.
- The ViewModel processes it and exposes temperature as LiveData<String>.
- The View observes this LiveData and updates the TextView automatically when data changes.

This makes the app clean, testable, and lifecycle-aware

</details>

<details>
<summary><strong>Explain MVI (Model-View-Intent)
</strong></summary>

**MVI stands for Model–View–Intent**, and it follows a **unidirectional data flow** — everything moves in one direction.

Here’s how it works:

- **Intent** → represents user actions, like button clicks or typing.
- **ViewModel (or Intent Processor)** → takes those intents, processes logic, and updates the state.
- **Model** → holds the immutable UI state.
- **View** → observes that state and renders the UI accordingly.

For example — in a login screen:

- The user clicks ‘Login’ (Intent)
- ViewModel validates credentials and updates a LoginState (Model)
- The View observes this and shows success or error UI.

It’s great for predictable state management, easy debugging, and reactive UIs — especially with Kotlin Flow or Compose

</details>

<details>
<summary><strong>Explain MVC (Model-View-Controller)
</strong></summary>

**MVC stands for Model–View–Controller**, one of the oldest architecture patterns.

- **Model** → Manages the data and business logic.
- **View** → Handles the UI and user interactions.
- **Controller** → Acts as a bridge, taking input from the View and updating the Model or View as needed.

In Android, however, Activities or Fragments often act as both View and Controller, which causes tight coupling and makes testing harder.
</details>


<details>
<summary><strong>Explain MVP (Model-View-Presenter)
</strong></summary>

**MVP stands for Model–View–Presenter**. It improves on MVC by separating the UI logic more cleanly.

- **Model** → Handles data operations (API, database, etc.)
- **View** → Displays data and forwards user actions to the Presenter.
- **Presenter** → Contains all the UI logic, updates the View through an interface, and interacts with the Model.

The key point is — the View is passive and doesn’t contain logic; the Presenter controls everything.

It’s easier to test and maintain than MVC, but the Presenter can become large in complex screens
</details>

<details>
<summary><strong>What is Unidirectional Data Flow (UDF)?
</strong></summary>

Unidirectional Data Flow means that data in the app moves in a single direction — from the source of truth down to the UI, and user actions flow back up to update that source.

In simple terms, the View observes the state, the ViewModel updates the state, and the state flows back to the View. This one-way flow makes the app’s behavior predictable and easy to debug.

</details>

## Clean Architecture

<details>
<summary><strong>Explain Clean Architecture layers (Data → Domain → Presentation)
</strong></summary>

Clean Architecture separates the app into three main layers — Data, Domain, and Presentation — to keep code testable, and maintainable

- Data Layer → This layer handles data operations like network calls, databases, or caching. It contains Repository implementations that fetch data and map it into domain models.

- Domain Layer – Contains the business logic and use cases. It doesn’t depend on Android. It defines what the app does, not how it’s displayed.

- Presentation Layer → This layer handles UI logic. It includes ViewModels, Compose UI, or Activities/Fragments. The ViewModel calls use cases from the domain layer and exposes UI state to the view.

</details>

<details>
<summary><strong>How do you handle business logic vs UI logic separation?
</strong></summary>

- All the business logic — like data validation, decision-making, or API processing — goes into the domain layer or the ViewModel, depending on the complexity. This part doesn’t know anything about the UI.

- Then, the UI logic — like showing progress bars, displaying messages, or handling user interactions — stays in the presentation layer, such as a Composable or Activity.

For example, a ‘LoginUseCase’ handles the login rules, while the UI layer just observes the result and updates the screen.

</details>

<details>
<summary><strong>How do you separate data, domain, and presentation layers?
</strong></summary>

- **The data layer** handles everything related to external sources — like API calls, databases, and repositories. It knows how to get the data.

- **The domain layer** is the core of the app — it contains business logic, use cases, and repository interfaces. It defines what the app does, but not how.

- **The presentation layer** handles the UI — it includes ViewModels, Activities, Fragments, or Composables. It just observes state from the domain layer and displays it.

So the flow is one-way:
**Presentation → Domain → Data**, and results come back **Data → Domain → Presentation**

This clear separation makes the app easier to test, maintain, and scale

</details>

## Repository Pattern

<details>
<summary><strong>What is the Repository pattern?
</strong></summary>

The Repository pattern acts as a single source of truth between the data sources and the rest of the app.

Instead of the ViewModel or use cases directly calling APIs or databases, they interact with the Repository, which decides where the data should come from — like a remote API, local cache, or database.

This keeps the data access logic centralized, hides complexity, and makes the code easier to maintain and test.

In short, the Repository abstracts the data layer so the rest of the app doesn’t care how or from where the data is fetched — it just gets clean, ready-to-use data.

</details>

<details>
<summary><strong>What is the purpose of Repository pattern?
</strong></summary>

The main purpose of the Repository pattern is to separate data logic from business logic and provide a clean, API for accessing data.

It acts as a bridge between the data layer and the domain layer. So instead of the ViewModel or use case directly talking to the network or database, they call the Repository.

The Repository decides whether to fetch data from the remote API, local database, or cache, and returns the final result.

</details>

<details>
<summary><strong>How to manage multiple data sources in Repository?
</strong></summary>

To manage multiple data sources in a Repository, I let the Repository decide where the data should come from — either the local database or the remote API.

For example, if the data is already available and fresh in the database, the Repository returns it directly.
If it’s missing or outdated, it fetches new data from the API, saves it locally, and then returns it.

This way, the Repository hides all that decision-making, and the ViewModel or use case just asks for data — without caring whether it’s coming from the network or local storage

</details>

## UseCase/Interactor

<details>
<summary><strong>What is a UseCase/Interactor in architecture?
</strong></summary>

- A UseCase (also called an Interactor) represents a single business logic in your app’s architecture.

It sits between the ViewModel and the Repository layers and defines what action needs to be done, not how it’s done.

For example, a GetUserProfileUseCase might fetch user data from the repository — the ViewModel just calls this use case instead of handling the logic itself.

</details>

<details>
<summary><strong>How do UseCases fit into Clean Architecture?
</strong></summary>

In Clean Architecture, UseCases sit in the domain layer, which is the core of the app.

They contain the business logic — the rules that define how your app works. The presentation layer (like ViewModels or UI) calls these UseCases to perform actions, and the data layer (like repositories or APIs) provides the data they need.

So, UseCases act as a bridge between the UI and data layers, making the app modular, testable, and independent of frameworks or platforms

</details>

<details>
<summary><strong>When should you use UseCases?
</strong></summary>

You should use UseCases when your app has clear business logic or reusable operations that shouldn’t be tied to the UI or data layers.

For example, tasks like ‘fetch user profile,’ ‘validate login,’ or ‘update favorites’ fit well as UseCases.

They’re especially useful in Clean Architecture or large projects, where separating logic improves testability, readability, and scalability.

In very small apps, you might skip them

</details>

## ViewModel

<details>
<summary><strong>What is a ViewModel and why do we use it?
</strong></summary>

A ViewModel, part of the Android Architecture Components, is responsible for holding and managing UI-related data

We use it to separate UI logic from business logic, so the UI stays simple and focused only on displaying data.

It survives survives configuration changes like screen rotations, so data doesn’t get lost when the activity is recreated.

It also helps make code cleaner, lifecycle-aware, and easier to test, since the ViewModel isn’t destroyed with the UI

</details>

<details>
<summary><strong>How does ViewModel survive configuration changes?
</strong></summary>

When a configuration change happens, like rotating the screen, the activity or fragment is destroyed and recreated.

However, the ViewModel is stored inside the ViewModelStore, which is tied to the lifecycle owner — not the activity instance itself.

So when the new activity is created, it gets the same ViewModel instance from the ViewModelStore, meaning no data lost.

That’s why ViewModels can survive configuration changes and keep UI data consistent

</details>

<details>
<summary><strong>How does ViewModel survive configuration changes?
</strong></summary>

When a configuration change happens, like rotating the screen, the activity or fragment is destroyed and recreated.

However, the ViewModel is stored inside the ViewModelStore, which is tied to the lifecycle owner — not the activity instance itself.

So when the new activity is created, it gets the same ViewModel instance from the ViewModelStore, meaning no data lost.

That’s why ViewModels can survive configuration changes and keep UI data consistent

</details>

<details>
<summary><strong>How does ViewModel work internally?
</strong></summary>

Inside Android, every Activity or Fragment has something called a ViewModelStore.

When you create a ViewModel using ViewModelProvider, it checks if that ViewModel already exists in the store.

If it does, it gives you the same instance.

If not, it creates a new one and saves it in the store.

When a configuration change happens, like screen rotation, the Activity is destroyed but the ViewModelStore is kept in memory. The new Activity then reconnects to the same store and gets the same ViewModel instance.

The ViewModel is only cleared when the Activity or Fragment is truly finished

</details>

<details>
<summary><strong>How does ViewModel survive process death internally?
</strong></summary>

Actually, a ViewModel doesn’t survive process death by itself.

When the system kills your app’s process to free memory, everything in memory — including the ViewModel — is lost.

</details>

<details>
<summary><strong>What's the difference between ViewModelStoreOwner and LifecycleOwner?
</strong></summary>

-A LifecycleOwner is any class (like an Activity or Fragment) that has a lifecycle — it knows when it’s created, started, paused, or destroyed.
It’s mainly used for observing things like LiveData safely according to the lifecycle.

- A ViewModelStoreOwner, is a class that owns a ViewModelStore, which keeps ViewModels in memory.

</details>

## State Management

<details>
<summary><strong>Compare LiveData, StateFlow, and SharedFlow
</strong></summary>

LiveData – lifecycle-aware data holder used mostly in Android. It automatically updates the UI when data changes and stops observing when the lifecycle is destroyed. But it’s not part of Kotlin — it’s Android-specific.

StateFlow – a Kotlin Flow that always holds one current value. It’s like a hot stream that emits updates to all collectors. Perfect for holding and updating UI state in ViewModels.

SharedFlow – similar to StateFlow, but it doesn’t store a single current value. Instead, it’s used for one-time events like showing a Toast or navigation actions.

</details>

<details>
<summary><strong>What's the difference between LiveData and Flow?
</strong></summary>

LiveData is part of Android — it’s lifecycle-aware, so it automatically stops updating when the UI is not visible. It runs on the main thread by default and is simple to use for UI data.

Flow is part of Kotlin Coroutines — it’s not lifecycle-aware, but it’s more powerful and flexible. It supports things like transformations, combining flows, and running on background threads easily.

</details>

<details>
<summary><strong>What is StateFlow and why it's preferred in Compose?
</strong></summary>

StateFlow is a special kind of Kotlin Flow that always holds one latest value — like a current state of the UI. Whenever the value changes, it automatically emits the new one to all collectors.

It’s preferred in Jetpack Compose because Compose is state-driven — the UI updates automatically when the state changes.

</details>

<details>
<summary><strong>When to use StateFlow vs SharedFlow?
</strong></summary>

Use StateFlow when you want to hold and observe a current state — like a screen’s UI data.
It always has one latest value, and new collectors immediately get that value.
For example, things like loading status or user details.

Use SharedFlow when you want to send one-time events — things that shouldn’t repeat automatically,
like showing a Toast, navigating to another screen, or displaying an error message.

</details>


<details>
<summary><strong>What's the difference between cold Flow and hot Flow?
</strong></summary>

A cold Flow starts running only when someone collects it.
Each collector gets its own new stream of data.
For example, if you call an API inside a cold Flow, it runs again for every collector.
Regular flow {} in Kotlin is cold.

A hot Flow keeps running and emits data whether anyone is listening or not.
When a new collector joins, it just receives the latest values.
Examples of hot flows are StateFlow and SharedFlow.

</details>


<details>
<summary><strong>Why prefer Immutable UI state over mutable?
</strong></summary>

I prefer immutable UI state because it makes the app’s behavior predictable and easier to debug.
When the state is immutable, you can’t change it directly — you always create a new copy with updated values.
This avoids accidental changes and makes it easier to track how and when the UI changes.

</details>

## Design Principles

<details>
<summary><strong>What is SOLID Principle
</strong></summary>

I prefer immutable UI state because it makes the app’s behavior predictable and easier to debug.
When the state is immutable, you can’t change it directly — you always create a new copy with updated values.
This avoids accidental changes and makes it easier to track how and when the UI changes.

</details>

<details>
<summary><strong>What is the Single Responsibility Principle and how does it apply to ViewModel or Repository layers?
</strong></summary>

The Single Responsibility Principle means that a class should have only one reason to change — it should do one specific job.

In Android architecture:

- A ViewModel should only handle UI-related logic, like preparing data for the screen or reacting to user actions.
- A Repository should only handle data operations, like fetching data from a network or database.

</details>

<details>
<summary><strong>How does the Dependency Inversion Principle improve testability and scalability in Android?
</strong></summary>

The Dependency Inversion Principle means that high-level classes shouldn’t depend directly on low-level classes — both should depend on an interface or abstract layer.

In Android, instead of a ViewModel creating a Repository itself, we give it an interface of the Repository and inject the actual implementation later using something like Hilt.

This makes the app easier to test, because we can pass a fake or mock Repository in tests.

</details>

<details>
<summary><strong>Give a real example where applying SOLID improved your project architecture.
</strong></summary>

In one of my projects, I had a single Activity that was doing everything — handling UI, network calls, and data logic all in one place. It became very hard to manage and test.

So, I applied SOLID principles:

I used the Single Responsibility Principle to move data logic into a Repository and business logic into UseCases, keeping the Activity only for UI work.

Then I applied Dependency Inversion, so the ViewModel depended on interfaces, not real implementations.

After that, my project became modular, easy to test, and easier to extend. I could add new features without touching existing code

</details>

<details>
<summary><strong>Which SOLID principle helps you add new features without modifying existing classes?
</strong></summary>

In one of my projects, I used the Open/Closed Principle when I had to support multiple types of media players.

At first, I had one class handling all types — video, audio, and live streams — and it was full of if-else statements. Whenever I added a new type, I had to change the same class again and again.

So I applied the Open/Closed Principle — I created a Player interface and then separate classes like VideoPlayer, AudioPlayer, and LivePlayer.
Now, when I need a new player type, I just add a new class without touching the old code.

It made the project cleaner, easier to extend, and safer from bugs

</details>

<details>
<summary><strong>What SOLID principle helps avoid fat interfaces in Android (e.g., callbacks or listeners)?
</strong></summary>

In one of my projects, I used the Interface Segregation Principle to avoid one big listener doing everything.

Before, I had a single interface called PlayerListener that handled play, pause, stop, error — all in one place. Every class that implemented it had to override all methods, even if it needed only one.

So I split it into smaller interfaces like OnPlaybackListener, OnPlaySuccessErrorListener.
Now, each class just implements what it really needs — no extra code, no confusion.

</details>

<details>
<summary><strong>Can you describe a situation where violating SOLID caused maintenance problems?
</strong></summary>

In one of my older projects, we had a single Repository that handled everything — API calls, database operations, and data mapping.

At first, it worked fine, but later it became a mess.
Whenever we changed something in the API logic, it broke the database part.

It clearly violated the Single Responsibility Principle, because one class was doing too many things.

After splitting it into separate classes — one for API, one for DB, and one for mapping — the code became much easier to test, debug, and maintain

</details>

## Design Pattern & Architecture Questions

<details>
<summary><strong>Explain how the Repository Pattern fits into Clean Architecture
</strong></summary>

In Clean Architecture, the Repository Pattern acts like a middle layer between the data sources and the domain or ViewModel.

It hides where the data actually comes from — like API, database, or cache.
The ViewModel just asks the repository for data and doesn’t care whether it’s from the network or local storage.

This makes the app more flexible and easier to maintain, because if we change the data source later, we don’t need to touch the ViewModel or use cases

</details>


<details>
<summary><strong>When would you use the Strategy Pattern in Android?
</strong></summary>

In one of my apps, I used the Strategy Pattern to handle different video players.

We had to support both ExoPlayer and VLC Player depending on user selection.
Instead of writing big if-else blocks everywhere, I created a PlayerStrategy interface with methods like play() and pause().

Then I made separate classes — ExoPlayerStrategy and VlcPlayerStrategy.
At runtime, I just switched the strategy based on the user’s setting.

</details>

<details>
<summary><strong>Explain the difference between Factory and Builder pattern with Android examples.
</strong></summary>

The Factory Pattern is used when you need to decide which object or subclass to create.
For example, ViewModelProvider.Factory in Android decides which ViewModel instance to provide — you just ask for it, and the factory handles the creation logic.

The Builder Pattern is used when you need to build a complex object step by step.
For example, AlertDialog.Builder or Retrofit.Builder — you set title, message, buttons, or base URL step by step, and then call build() or create() to get the final object.

So in short — Factory chooses the right object, while Builder gradually constructs it.

</details>

<details>
<summary><strong>When and why would you use the Observer Pattern in Android?
</strong></summary>

I use the Observer Pattern when I want the UI to update automatically when data changes.

For example, LiveData or Flow let the ViewModel send updates, and the Activity or Fragment observes them.

</details>


<details>
<summary><strong>What is the difference between MVVM and MVI architecture?
</strong></summary>

- In MVVM, the View observes data from the ViewModel — usually using LiveData or StateFlow — and updates automatically when data changes.
- In MVI, the View sends intents to the ViewModel, which processes them and returns a new immutable state each time.
- MVI gives predictable and consistent UI states, while MVVM is simpler and more flexible

</details>

<details>
<summary><strong>You currently use Retrofit but want to move to Ktor without breaking ViewModels.
How would you design this?
</strong></summary>

I’d use the Dependency Inversion Principle.

First, I’d create an ApiService interface that defines all API methods.
Then I’d have two implementations — RetrofitApiService and KtorApiService.

The Repository depends only on the interface, not the actual library.
So later, I can switch from Retrofit to Ktor very easily.

</details>


# LEVEL 7: Dependency Injection

## DI Fundamentals

<details>
<summary><strong>What’s the difference between tight coupling and loose coupling?
</strong></summary>

Tight coupling means classes are highly dependent on each other — if one changes, the other breaks. Loose coupling means each class depends on abstractions
- In Android, Dependency Injection helps achieve loose coupling by providing dependencies from outside. This makes the code easier to maintain

</details>

<details>
<summary><strong>What is Dependency Injection?
</strong></summary>

Dependency Injection is a design pattern where the required objects or dependencies of a class are provided from outside instead of creating them inside the class. This makes the code more flexible, reusable, and easier to test. In Android, we usually use tools like Dagger Hilt or Koin. 

</details>

<details>
<summary><strong>How do you use Dependency Injection in Android?
</strong></summary>

- In Android, I usually use Hilt, which is built on top of Dagger, for dependency injection. I create classes like repositories, data sources, or use cases and annotate them with @Inject or @Singleton. Then I use @HiltViewModel or @AndroidEntryPoint in my activities and fragments to get those dependencies automatically. This setup removes the need for manual object creation, reduces boilerplate

================================================================================

- In my projects, I use Koin for dependency injection because it’s lightweight and easy to set up compared to Dagger or Hilt. I define all my dependencies inside Koin modules using single { } or factory { }. Then I start Koin in the Application class and inject dependencies directly into ViewModels or classes using by inject() or get(). It keeps my code modular, and makes it easy to swap implementations if needed.

</details>

<details>
<summary><strong>How do you use Dependency Injection in Android?
</strong></summary>

- In Android, I usually use Hilt, which is built on top of Dagger, for dependency injection. I create classes like repositories, data sources, or use cases and annotate them with @Inject or @Singleton. Then I use @HiltViewModel or @AndroidEntryPoint in my activities and fragments to get those dependencies automatically. This setup removes the need for manual object creation, reduces boilerplate

================================================================================

- In my projects, I use Koin for dependency injection because it’s lightweight and easy to set up compared to Dagger or Hilt. I define all my dependencies inside Koin modules using single { } or factory { }. Then I start Koin in the Application class and inject dependencies directly into ViewModels or classes using by inject() or get(). It keeps my code modular, and makes it easy to swap implementations if needed.

</details>

<details>
<summary><strong>Explain the advantages of Dependency Injection
</strong></summary>

Dependency Injection has several advantages. 
- It makes the code loosely coupled, so classes don’t directly depend on each other. 
- It also improves testability, because we can easily pass mock or fake dependencies during testing. 
- It helps with code reusability and maintainability, since changing one class doesn’t affect others. 

</details>

<details>
<summary><strong>What are the advantages of Koin?
</strong></summary>

- Koin is lightweight and very easy to set up compared to Dagger or Hilt.
- It doesn’t need any code generation or annotations — everything is written in pure Kotlin. That makes it faster to configure and great for small or medium-sized projects. 
- It’s also very flexible for testing since we can easily replace dependencies at runtime. Overall, it’s simple, readable, and fits perfectly in Kotlin-based projects

</details>

<details>
<summary><strong>What are the advantages of Dagger Hilt?
</strong></summary>

- Hilt is a powerful dependency injection framework built on top of Dagger. 
- It provides compile-time safety, meaning it catches dependency errors early. 
- It automatically manages Android components through annotations like @AndroidEntryPoint and @HiltViewModel. 
- It’s highly optimized for large projects, improves performance, and integrates well with Jetpack libraries.

</details>

<details>
<summary><strong>Why is Dagger Hilt recommended for large projects, and can we use Koin instead?
</strong></summary>

You can definitely use Koin in large projects — there’s no hard rule against it. The main difference is in how they work internally. 

- Hilt (based on Dagger) uses compile-time dependency injection, meaning it generates all the dependency code at build time. This gives better performance, type safety, and catches errors early — which is important in large, complex codebases.

- Koin, on the other hand, uses runtime dependency injection, which is easier to set up but can be slightly slower and doesn’t catch dependency errors until the app runs. That’s why Hilt is usually preferred for large or enterprise projects, where performance and stability matter more. But for small or mid-sized apps, Koin is perfectly fine — it’s faster to implement and easier to maintain.

</details>


<details>
<summary><strong>What's the difference between constructor injection and field injection?
</strong></summary>

Constructor injection means we pass the dependencies through the class constructor. It’s considered the best practice because it makes the dependency required and ensures the object can’t be created without it — great for testing and immutability.

Field injection, on the other hand, uses annotations like @Inject directly on class fields or properties. It’s simpler for Android components like Activities or Fragments, but those dependencies are set after the object is created, so it’s less safe. In short — constructor injection is cleaner and more reliable, while field injection is convenient but should be used only when necessary

</details>

## Dagger/Hilt

<details>
<summary><strong>How does Dagger/Hilt work under the hood?
</strong></summary>

Dagger and Hilt use compile-time dependency injection. That means, when we build the project, they automatically generate the code that connects all dependencies together using annotation processing.
This approach gives better performance, because everything is resolved at compile time

</details>

<details>
<summary><strong>What are Scopes in Dagger / Hilt? (like @Singleton, @ActivityScoped, @ViewModelScoped)
</strong></summary>

In Dagger and Hilt, Scopes define how long a dependency should live — basically its lifecycle.
When we use annotations like @Singleton, @ActivityScoped, or @ViewModelScoped, we’re telling Hilt how long to keep that instance in memory.

- @Singleton means the dependency will live as long as the entire app — one shared instance.
- @ActivityScoped means a new instance is created for each Activity and shared within it.
- @ViewModelScoped means the dependency lives as long as the ViewModel.

</details>

## Koin

<details>
<summary><strong>How does Koin work internally?
</strong></summary>

Koin works using runtime dependency injection. When the app starts, Koin builds a dependency graph in memory using the modules we define. Each time we call get() or use by inject(), Koin looks up the dependency in that graph and provides the right instance based on how it’s defined — single, factory, or scoped.

</details>

===========================================

<details>
<summary><strong>What are Scopes in Hilt/Dagger, and why are they important?
</strong></summary>

- Scopes define how long a dependency should live. 
- For example, @Singleton means one instance for the whole app, @ActivityScoped means one per activity, and @ViewModelScoped means tied to the ViewModel’s lifecycle. Scopes prevent unnecessary object creation and memory leaks

</details>

<details>
<summary><strong>What are some performance or build-time trade-offs between Hilt and Koin?
</strong></summary>

Hilt works at compile-time, so it has slightly longer build times but faster runtime performance and better type safety. Koin, on the other hand, works at runtime, which makes it faster to build and easier to set up, but slightly slower during app startup and runtime dependency resolution. So, Hilt suits large-scale apps, while Koin is great for small to mid-size project

</details>


<details>
<summary><strong>What are some performance or build-time trade-offs between Hilt and Koin?
</strong></summary>

Hilt works at compile-time, so it has slightly longer build times but faster runtime performance and better type safety. Koin, on the other hand, works at runtime, which makes it faster to build and easier to set up, but slightly slower during app startup and runtime dependency resolution. So, Hilt suits large-scale apps, while Koin is great for small to mid-size project

</details>

<details>
<summary><strong>How do you inject Retrofit, Room, or Repository classes in Hilt?
</strong></summary>

I create a @Module annotated class, define a @Provides function for Retrofit or Room, and mark it with @Singleton. Then I inject those dependencies into repositories using @Inject constructor. Finally, ViewModels get the repository through constructor injection. This keeps the network, database, and domain layers clean and testable

</details>

<details>
<summary><strong>How do you provide different implementations of the same interface (e.g., Fake vs Real Repository)?
</strong></summary>

We use qualifiers like @Named("RealRepo") or @Named("FakeRepo") or create custom qualifiers. Each @Provides function defines a different implementation. When injecting, we specify the qualifier. This is very useful for switching between fake and real data sources in testing or different build variants

</details>

<details>
<summary><strong>You have a legacy project without DI — how would you migrate it to Hilt step-by-step?
</strong></summary>

First, I’d add the Hilt Gradle plugin and annotate the Application class with @HiltAndroidApp. Then, I’d start by converting major dependencies like Retrofit and Database into @Modules. Next, I’d annotate Activities and Fragments with @AndroidEntryPoint one by one. Gradual migration keeps the app stable while introducing DI layer by layer

</details>

<details>
<summary><strong>If a dependency is taking too long to initialize, how would you optimize it with DI?
</strong></summary>

I’d move heavy or rarely used dependencies to lazy injection using @Inject lateinit var dependency: Lazy<YourClass>. Hilt will only create it when actually used.

</details>

# LEVEL 8: Jetpack Components

## ViewModel & Scopes

<details>
<summary><strong>Why are Lifecycle-aware components important?
</strong></summary>

Lifecycle-aware components are important because they automatically respond to changes in an Android component’s lifecycle — like when an Activity or Fragment is created, paused, or destroyed. This helps prevent memory leaks and crashes

</details>

<details>
<summary><strong>What is ViewModelScope?
</strong></summary>

viewModelScope is a CoroutineScope that’s built into the Android ViewModel class. It’s used to launch coroutines that should live as long as the ViewModel. When the ViewModel is cleared — for example, when the user leaves the screen — all coroutines started in viewModelScope are automatically cancelled.

This helps prevent memory leaks and ensures background tasks don’t continue after the ViewModel is destroyed

</details>

<details>
<summary><strong>What's the difference between viewModelScope, lifecycleScope, and GlobalScope?
</strong></summary>

- viewModelScope is tied to a ViewModel’s lifecycle. When the ViewModel is cleared, all coroutines are automatically cancelled — perfect for tasks related to UI data, like API calls or database operations.

- lifecycleScope is tied to an Activity or Fragment’s lifecycle. When the UI component is destroyed, the coroutines are cancelled — good for UI-related tasks like animations or observing LiveData.

- GlobalScope lives as long as the entire app process. It’s not tied to any lifecycle, so coroutines keep running even if the UI is destroyed — which can cause memory leaks if not handled carefully.

</details>

## LiveData

<details>
<summary><strong>What is LiveData?
</strong></summary>

LiveData is a lifecycle-aware observable data holder provided by Jetpack. When data changes, LiveData automatically notifies all active observers — like Activities or Fragments — but only when they’re in an active state (started or resumed).

This prevents memory leaks and crashes because LiveData automatically stops updating when the UI is destroyed.

</details>


## Room Database

<details>
<summary><strong>What is Room? How does it relate to SQLite?
</strong></summary>

Room is a Jetpack persistence library that provides an easy and type-safe way to work with SQLite databases in Android. It acts as an abstraction layer over SQLite — so instead of writing raw SQL queries, we use annotations like `@Entity`, `@Dao`, and `@Query`

</details>

<details>
<summary><strong>Explain Entity, DAO, and Database in Room
</strong></summary>

- Entity represents a table in the SQLite database. Each field in the Entity class becomes a column, and we mark it with @Entity.

- DAO (Data Access Object) defines methods to interact with the database — like inserting, updating, deleting, or querying data. It’s annotated with @Dao, and Room generates all the SQL code for us.

- Database is the main access point that ties everything together. It’s an abstract class annotated with @Database and lists all entities and DAOs. It extends RoomDatabase and provides the instance of each DAO.

</details>

<details>
<summary><strong>How do you handle database migrations in Room?
</strong></summary>

When we change the database schema — like adding a new column or table — Room requires a migration to update the existing database without losing data. We handle this by creating a Migration object with the old and new version numbers, and overriding the migrate() method to run SQL statements.

Then we pass that migration object to the Room database builder using .addMigrations(). This way, existing user data stays intact.

</details>

## Datastore 

<details>
<summary><strong>What are SharedPreferences? What are their limitations?
</strong></summary>

SharedPreferences is an Android storage option used to save small amounts of key-value data, like user settings, login state, or app preferences. It stores data in an XML file inside the app’s private storage.

but

- It’s not suitable for large or complex data
- It’s not secure by default, so sensitive data like passwords should not be stored there
- It doesn’t support transactions, and performs synchronously, which can block the main thread if overused

</details>

<details>
<summary><strong>What’s the difference between DataStore and SharedPreferences?
</strong></summary>

DataStore is the modern and improved replacement for SharedPreferences. DataStore is built on Kotlin coroutines and Flow, making it asynchronous, thread-safe, and more reliable.

- SharedPreferences, on the other hand, works synchronously, whike Datastore making it asynchronous
- Overall, DataStore is faster, safer, and better suited for modern apps

</details>

<details>
<summary><strong>Why is DataStore better than SharedPreferences?
</strong></summary>

DataStore is better than SharedPreferences because it’s asynchronous, safe, and modern. SharedPreferences reads and writes data synchronously, which can block the main thread and cause ANRs. DataStore, on the other hand, uses Kotlin coroutines and Flow, so all operations happen off the main thread.

Plus, DataStore can store both key-value pairs and typed data models using Proto DataStore

</details>

## WorkManager

<details>
<summary><strong>What is WorkManager?
</strong></summary>

WorkManager is a Jetpack component library used to schedule and manage background tasks in Android that need to run even if the app is closed or the device restarts. It’s the recommended solution for guaranteed background work — for example, syncing data, uploading logs, or sending analytics.

</details>

<details>
<summary><strong>What's the difference between WorkManager, AlarmManager, and JobScheduler?
</strong></summary>

WorkManager, AlarmManager, and JobScheduler are all used for background work, but they serve different purposes.

- **AlarmManager** is for exact or time-based tasks — it just triggers code at a specific time, but doesn’t guarantee completion if the device restarts or the app is killed.

- **JobScheduler** batches and manages background jobs efficiently but works only on API 21+.

- **WorkManager** is the most flexible — it automatically picks the best option internally (AlarmManager or JobScheduler) and ensures the work is guaranteed to run, even after device reboot. It also supports chaining, constraints, and asynchronous tasks with coroutines or RxJava.

</details>

<details>
<summary><strong>What is JobScheduler?
</strong></summary>

JobScheduler is an Android API introduced in API 21 (Lollipop) that allows scheduling background tasks to run under specific conditions — like when the device is charging, idle, or connected to Wi-Fi.

However, JobScheduler only works on Android 5.0 and above, and it doesn’t guarantee execution if the app process is killed on older devices

</details>

## Paging 3


<details>
<summary><strong>What is Paging 3?
</strong></summary>

Paging 3 is a Jetpack library that helps load and display large lists of data efficiently by fetching it in small pages instead of loading everything at once. It’s built on Kotlin coroutines and Flow, making it lifecycle-aware and easy to integrate with RecyclerView or Jetpack Compose

Paging 3 also handles things like loading states, errors, and refreshing data, which makes it much easier

</details>

<details>
<summary><strong>How does Paging 3 work internally?
</strong></summary>

Paging 3 works by using a Pager and a PagingSource to load data in small chunks instead of all at once.

The PagingSource defines how to load pages of data — either from a network API or a local database. The Pager then controls when and how much data to load based on user scrolling. As the user scrolls, it automatically requests the next page and updates the list.

It emits data using Flow (or LiveData), so the UI layer — like a PagingDataAdapter — gets new pages automatically.
Internally, Paging 3 handles caching, load states, and error retries, making it efficient and smooth for lists that can grow very large

</details>

<details>
<summary><strong>How does RemoteMediator handle API + DB sync?
</strong></summary>

RemoteMediator is a part of Paging 3 that helps you keep data from a remote API and a local database (like Room) in sync. It acts as a bridge between them.

When Paging 3 needs more data — for example, when the user scrolls to the end of the list — it calls RemoteMediator.load(). Inside that method, you fetch data from the API, then store it in the database. The PagingSource then loads from the local DB, not directly from the network.

This makes the app work offline-first, since data always comes from the database, while the RemoteMediator updates it in the background

</details>

<details>
<summary><strong>What are caching strategies in Paging 3?
</strong></summary>

Paging 3 supports different caching strategies to balance between network calls and local data reuse. The main goal is to reduce API usage and make scrolling smooth, even offline.

The most common approach is the Network + Database (RemoteMediator) pattern — data is fetched from the API, saved into a local Room database, and displayed from there. This ensures the UI always reads from the cache, and the database stays updated in the background.

There’s also in-memory caching, handled by the PagingDataAdapter, which keeps recently loaded pages in memory to avoid re-fetching when you scroll back.

</details>

<details>
<summary><strong>How do you handle pagination manually without Paging 3?
</strong></summary>

I call the API with parameters like page=1, limit=20, and when the user scrolls to the end of the list, we trigger another API call with page=2.

We then append the new data to the existing list in the adapter, usually with a loading indicator at the bottom. We also handle loading states, error retries, and prevent duplicate requests using flags like isLoading or hasMoreData.

This approach gives full control but requires more boilerplate and careful state management compared to Paging 3

</details>

## Other Components

<details>
<summary><strong>What is App Startup?
</strong></summary>

App Startup is a Jetpack library that helps you initialize components and libraries efficiently when your app launches. Instead of using multiple ContentProviders or custom Application logic for each library, App Startup provides a single, optimized initialization mechanism.

You define initializers by implementing Initializer<T> and register them in the manifest or via code. The library automatically runs them in the right order and only when needed.

This improves startup performance, reduces boilerplate code, and helps you control the initialization sequence of your libraries or SDKs
</details>

<details>
<summary><strong>What's a Loader and why is it deprecated?
</strong></summary>

Loader was an older Android component used to load data asynchronously in Activities or Fragments — especially for tasks like querying a database or fetching data from a network.

However, it’s now deprecated because newer, more robust solutions exist — like ViewModel, LiveData, and coroutines — which handle lifecycle awareness and async operations more clean.
</details>

# LEVEL 9: Networking & Data

## Networking Libraries

<details>
<summary><strong>What libraries have you used for networking? (Retrofit, Volley, OkHttp)
</strong></summary>

I’ve mainly used Retrofit for networking in my projects, and sometimes Volley for simpler or legacy cases.

Retrofit is my preferred choice because it’s built on top of OkHttp, supports coroutines, and automatically handles JSON serialization with converters like Gson. It’s great for clean API interfaces and error handling.

Volley, while easy for basic requests or image loading, is older and less flexible for large-scale apps, so I mostly stick to Retrofit

</details>

<details>
<summary><strong>What's the difference between Retrofit and Volley?
</strong></summary>

Retrofit is built on OkHttp and is ideal for RESTful APIs. It automatically converts JSON responses into data models using converters like Gson or Moshi, supports Kotlin coroutines, and handles complex API calls cleanly with minimal code.

Volley, on the other hand, is older and works well for simple requests, like fetching text or images. But it doesn’t have built-in serialization or coroutine support — you have to handle parsing manually.

</details>

<details>
<summary><strong>How do you make a network request in a modern Android app?
</strong></summary>

Retrofit is built on OkHttp and is ideal for RESTful APIs. It automatically converts JSON responses into data models using converters like Gson or Moshi, supports Kotlin coroutines, and handles complex API calls cleanly with minimal code.

Volley, on the other hand, is older and works well for simple requests, like fetching text or images. But it doesn’t have built-in serialization or coroutine support — you have to handle parsing manually.

</details>

<details>
<summary><strong>What are interceptors in OkHttp?
</strong></summary>

Interceptors in OkHttp are components that let you observe, modify, or retry network requests and responses before they reach the server or app.They’re useful for tasks like adding headers, logging requests, handling authentication, or caching responses.

</details>

<details>
<summary><strong>How to add headers dynamically in Retrofit?
</strong></summary>

There are two main ways to add headers dynamically in Retrofit.

- The first is by using the @Header annotation directly in your API interface. For example, if you have an authorization token that changes, you can pass it as a parameter — so it only applies to that specific request.

The second, and more common way, is by using an OkHttp interceptor. You create a custom interceptor that reads the latest token SharedPreferences or DataStore and adds it automatically to every request. This is better for global headers like authentication

</details>

## API Error Handling

<details>
<summary><strong>How to handle API errors gracefully (timeouts, 500s, 401s)?
</strong></summary>

I usually wrap all my network calls in a safe API call function that catches exceptions and maps them to a clean result type — like Success, Error, or Loading.

For example, timeouts or no internet are caught as IOException, and I show a retry message to the user. 500-series errors mean a server problem, so I display a friendly error message instead of crashing. 

For 401 errors, which usually mean an expired token, I trigger a token refresh or redirect the user to the login screen.

</details>

## Security

<details>
<summary><strong>Explain certificate pinning
</strong></summary>

Certificate pinning means the app trusts only a specific SSL certificate or public key from the server.

Normally, an app trusts any certificate signed by a trusted authority, but with pinning, it checks for a specific one — so even if a hacker installs a fake certificate, the app will reject it.
This helps protect against man-in-the-middle attacks and makes your network communication more secure

</details>

## Concurrent Requests

<details>
<summary><strong>How to make multiple API calls in parallel using coroutines?
</strong></summary>

To make multiple API calls in parallel, I use async and await inside a coroutineScope.
Each API call runs in its own coroutine, and then I wait for all results together

</details>

# LEVEL 10: Data & Storage

## Local Storage Options


<details>
<summary><strong>How would you store sensitive data like API keys or tokens?
</strong></summary>
There are some ways to store sensitive data.

- EncryptedSharedPreferences – it automatically encrypts the data before saving, so even if someone accesses the storage, they can’t read it.

- Fetch keys or endpoints from a secure server – instead of hardcoding them, the app requests them safely from the backend when needed.

- Use NDK with C++ – I can store keys in native code to make reverse engineering harder, though it’s not 100% secure.

</details>

<details>
<summary><strong>What is EncryptedSharedPreferences?
</strong></summary>

EncryptedSharedPreferences is just like normal SharedPreferences, but it automatically encrypts all keys and values before saving them.

</details>

# LEVEL 11: Concurrency & Coroutines

## Coroutines Basics

<details>
<summary><strong>What are Coroutines?
</strong></summary>

Coroutines are a lightweight way to run background tasks in Kotlin without blocking the main thread.
They help you write asynchronous code that looks simple and sequential.

</details>

<details>
<summary><strong>What are suspend functions?
</strong></summary>

A suspend function is a special Kotlin function that can pause execution without blocking the thread, then resume later.

It can only be called from another suspend function or within a coroutine Scope.

</details>

<details>
<summary><strong>Can suspend functions be called from a regular function?
</strong></summary>

No, Suspend function can not be called from regular function, It can be called from other suspend function or inside coroutine scope

</details>

<details>
<summary><strong>What happens if you call a suspend function outside a coroutine scope?
</strong></summary>

If you call a suspend function outside a coroutine scope, the code won’t compile.

</details>

## Launch vs Async

<details>
<summary><strong>What's the difference between launch and async?
</strong></summary>

- The main difference is that launch doesn’t return anything, it’s used for fire-and-forget tasks like saving data or showing logs.

- On the other hand async, is used when you want to get a result back — it returns a Deferred, and you call .await() to get that result.

</details>

<details>
<summary><strong>What's the difference between launch, async, and runBlocking?
</strong></summary>

- launch is used to start a coroutine that doesn’t return any result — it’s mainly for background work like saving to database or logging.

- async is similar, but it returns a Deferred value, so I use it when I need a result from a background task. I can call .await() to get that result.

- runBlocking is different — it blocks the current thread until the coroutine completes. It’s mostly used in tests or main functions, not in Android UI, because it freezes the thread.

</details>

## Coroutine Scopes

<details>
<summary><strong>What's the difference between CoroutineScope and lifecycleScope?
</strong></summary>

- CoroutineScope is a general-purpose scope for launching coroutines that you need to manage manually - you create it and you're responsible for cancelling it.

- lifecycleScope is a pre-defined scope tied to Android lifecycle components like Activities and Fragments. It automatically cancels all its coroutines when the component is destroyed, preventing memory leaks.

</details>

<details>
<summary><strong>What's the difference between viewModelScope, lifecycleScope, and GlobalScope?
</strong></summary>

- GlobalScope is the global coroutine scope that lives for the entire app lifetime, It can cause memory leaks if not managed carefully.

- lifecycleScope is tied to Android lifecycle components like Activities and Fragments - it automatically cancels when the Activity/Fragment is destroyed.

- viewModelScope is tied to ViewModels - it automatically cancels when the ViewModel is cleared,

</details>

<details>
<summary><strong>What is GlobalScope and when should you avoid it?
</strong></summary>

GlobalScope is the global coroutine scope that lives for the entire app lifetime.

We should avoid GlobalScope in most cases because it can cause memory leaks - coroutines continue running even after Activities or Fragments are destroyed

</details>

## Dispatchers

<details>
<summary><strong>Explain Dispatchers (Main, IO, Default) / How do Dispatchers.Main, Dispatchers.IO, and Dispatchers.Default differ?
</strong></summary>

- Dispatchers.Main - Runs on the UI thread. Use it for UI operations like updating Views, LiveData, or StateFlow. It's the default for Android UI components.

- Dispatchers.IO - used for input/output work like network or database calls

- Dispatchers.Default - used for heavy CPU work like sorting or parsing large data

</details>

<details>
<summary><strong>How to switch contexts in coroutines?
</strong></summary>

- I can switch coroutine contexts using withContext().

</details>

## Structured Concurrency

<details>
<summary><strong>What is structured concurrency? Explain with example
</strong></summary>

Structured concurrency means all coroutines are launched in a proper scope and follow the parent’s lifecycle.
If the parent is cancelled, all child coroutines are cancelled too — this prevents memory leaks or orphan coroutines.

</details>

<details>
<summary><strong>How does structured concurrency prevent leaks?
</strong></summary>

Structured concurrency ties every coroutine to a parent scope, like lifecycleScope or viewModelScope.
So if the parent is cancelled (like when an Activity or ViewModel is destroyed), all its child coroutines are automatically cancelled.
This prevents background coroutines from continuing and holding memory — that’s how it avoids leaks.

</details>

## Exception Handling

<details>
<summary><strong>How does exception handling work in coroutines?
</strong></summary>

In coroutines, exceptions are handled using try-catch inside the coroutine or by using a CoroutineExceptionHandler.

</details>


<details>
<summary><strong>What is SupervisorJob and why use it?
</strong></summary>

A SupervisorJob is a special type of Job that changes how coroutine failures are handled.

Normally, with a regular Job, if any child coroutine fails, it automatically cancels all other children and the parent itself. This is like "fail-fast" behavior.

But with a SupervisorJob, if one child fails, it doesn't affect the other children or the parent. Each coroutine fails independently.

In situations where you have multiple independent operations and you don't want one failure to cancel everything else.

For example, if you're uploading multiple images to a server, you'd want each upload to be independent - if one fails, the others should continue. That's where SupervisorJob makes sense.

</details>

<details>
<summary><strong>How to handle global error handling in coroutines?
</strong></summary>

For global error handling, I use a CoroutineExceptionHandler.
It catches uncaught exceptions from coroutines launched with launch.

Example:

```
val handler = CoroutineExceptionHandler { _, exception ->
    Log.e("Error", "Caught: $exception")
}

CoroutineScope(Dispatchers.Main + handler).launch {
    throw RuntimeException("Test error")
}
```


This is useful for handling global crashes, logging errors, or showing a generic error message.
But remember — it doesn’t catch exceptions from async, since those are handled when you call .await().

</details>

## Cancellation

<details>
<summary><strong>How to cancel coroutines correctly?
</strong></summary>

1. Automatic cancellation - When you use scopes like lifecycleScope or viewModelScope, cancellation happens automatically when the Activity/Fragment/ViewModel is destroyed.

2. Manual cancellation - Keep a reference to the Job and call cancel() when needed:

```kotlin
val job = viewModelScope.launch {
    // Long running work
}

// Later, when you want to cancel
job.cancel()
```
</details>


<details>
<summary><strong>How do you cancel a coroutine safely?
</strong></summary>

To cancel a coroutine safely, I call `cancel()` on its Job or parent Scope.
Then inside the coroutine, I check for cancellation using isActive or ensureActive() before doing long or repeating work.

Example:
```
val job = launch {
    for (i in 1..1000) {
        ensureActive() // stops if cancelled
        println(i)
    }
}
job.cancel()
```

This makes sure the coroutine stops cleanly without leaving partial work or memory leaks.
</details>

## Coroutine Context

<details>
<summary><strong>What are coroutine contexts and how are they composed?
</strong></summary>

A coroutine context is a set of data that defines how a coroutine runs — it includes things like the Dispatcher, Job, and ExceptionHandler.

You can combine them using the + operator.
Example:

val context = Dispatchers.IO + Job() + CoroutineExceptionHandler { _, e -> ... }


This means the coroutine will run on the IO thread, be linked to that Job, and use that handler for errors.
So basically, the context decides where, how, and under what rules your coroutine works.
</details>

# LEVEL 12 : Flow

## Flow Basic


<details>
<summary><strong>What is Flow?
</strong></summary>

Flow is a type in Kotlin used to handle streams of data asynchronously — it emits values one by one over time.

Think of it as a better alternative to RxJava or LiveData for stream processing. It's built on coroutines and follows the suspendable programming model.

Flow is particularly useful for real-time data updates, network streams, database changes, or any scenario where you need multiple values over time
</details>

<details>
<summary><strong>What's the difference between Flow, StateFlow, and SharedFlow?
</strong></summary>
 - Pending
</details>

<details>

<summary><strong>What's the difference between Flow and LiveData? Pros and cons
</strong></summary>

Flow and LiveData both send data updates to the UI, but they work differently.

LiveData is Android-only and lifecycle-aware. LiveData's advantages are its simplicity and automatic lifecycle management - it automatically stops updating when your activity is in the background, which prevents memory leaks.

Flow is Kotlin-based, not tied to Android, and much more powerful. It works in ViewModel, repository, and even backend code. It supports operators, handles threads better, and fits perfectly with coroutines. But it needs a coroutine scope to collect it.
</details>

<details>

<summary><strong>How does Flow fit into Clean Architecture?
</strong></summary>

In the data layer, Flow is ideal for repositories to expose data from multiple sources - like database, network, or cache. You can use Flow to create a single stream that combines these sources.

In the domain layer, use Flow for use cases that need to process streams of data or handle real-time operations.

In the presentation layer, collect Flows in ViewModels and expose UI state using StateFlow or SharedFlow to the UI components.

The key benefit is that Flow provides a consistent, reactive way to handle data across all architecture layers while maintaining the separation of concerns that Clean Architecture promotes
</details>

<details>
<summary><strong>What's the difference between Flow and Channel?
</strong></summary>

- Pending

</details>

## Cold vs Hot Flow

<details>
<summary><strong>What's the difference between cold and hot Flow?
</strong></summary>

A cold Flow runs only when someone collects it. Every collector gets its own fresh stream. For example, a network request — if two collectors collect it, it runs twice.

A hot Flow is already running and keeps emitting values whether someone is listening or not. Collectors join in the middle and share the same stream. Examples are StateFlow and SharedFlow.

</details>

## Flow Operators


<details>
<summary><strong>What are the operators in Flow? (map, flatMapConcat, combine, debounce, etc)
</strong></summary>

Flow has operators that help modify or control the data before it reaches the UI.

- map → changes each value. Example: convert API model to UI model.

- filter → only pass values that match a condition.

- flatMapConcat / flatMapLatest → switch to another Flow.
flatMapLatest cancels the old one (good for search typing).

- combine → mix two flows and emit whenever any one changes.

- debounce → wait for a pause before emitting (useful for search text).

- retry → try again if an API call fails.

- catch → handle errors.

</details>

<details>
<summary><strong>How can you combine multiple flows?
</strong></summary>

You can combine multiple Flows using the combine operator.
It lets you take values from two or more flows and create one new result whenever any flow updates.

Example:

One Flow gives user name

Another Flow gives user age
When either changes, combine gives a new pair.

</details>

<details>
<summary><strong>What's the use of catch, retry, and onCompletion in Flow?
</strong></summary>


In Flow, these operators help manage errors and the flow lifecycle.

- catch → used to handle errors safely. If something fails (like an API call), you can show an error message or return fallback data.

- retry → tries the flow again if it fails. Useful for unstable network calls.

- onCompletion → runs when the flow finishes — whether it's success or failure. Good for hiding loaders or cleaning up.

</details>

<details>
<summary><strong>Explain operators: map, flatMapConcat, combine, zip, debounce, catch
</strong></summary>

- map → changes each value. Example: convert API model to UI model.

- flatMapConcat / flatMapLatest → switch to another Flow.
flatMapLatest cancels the old one (good for search typing).

- combine → mix two flows and emit whenever any one changes.

- debounce → wait for a pause before emitting (useful for search text).

- catch → used to handle errors safely. If something fails (like an API call), you can show an error message or return fallback data.

</details>

## Flow Conversion

<details>
<summary><strong>How do you convert callback APIs into Flow?
</strong></summary>

To convert a callback-based API into a Flow, we use callbackFlow.
It lets us send data into a Flow whenever the callback gives a result.

</details>

## Backpressure & Cancellation

<details>
<summary><strong>How to handle backpressure in Flow?
</strong></summary>

Flow handles backpressure automatically because it’s suspending.
If the collector is slow, the producer waits — so nothing crashes or overloads.

</details>

<details>
<summary><strong>How do you cancel a Flow collection safely?
</strong></summary>

You cancel a Flow safely by cancelling the coroutine scope that is collecting it.
Because Flow follows structured concurrency, when the scope is cancelled, the Flow stops automatically.

Don’t cancel the Flow itself — cancel the coroutine scope, and the Flow stops safely.

</details>

# LEVEL 13: Performance & Optimization

## Memory Leaks

<details>
<summary><strong>What are common causes of memory leaks in Android?
</strong></summary>

Common memory leaks in Android usually happen when something holds a reference longer than needed.

Some common cases are:

- Holding a reference to Activity or Context in a long-running object like a ViewModel, Singleton, or background thread.

- Not removing listeners or callbacks, for example, location updates, Firebase listeners, or lifecycle observers.

- Keeping views or adapters alive after the screen is destroyed, like storing a Fragment view in a variable.

- Using static variables incorrectly, especially storing UI elements or context in them.

</details>

## ANR (Application Not Responding)

<details>
<summary><strong>What are some common causes of ANRs?
</strong></summary>

ANRs happen when the main thread is blocked for too long and the app can’t respond.

Common causes are:
- Doing heavy work on the main thread, like large loops, JSON parsing, or database operations.
- Slow network calls running on the main thread.
- Long file operations like reading big images or videos.
- Too many tasks happening during startup before UI becomes interactive.

</details>


<details>
<summary><strong>How do you prevent and debug ANRs?
</strong></summary>

To prevent ANRs:

- Offload heavy work like networking, JSON parsing, or database queries to background threads using coroutines with the right dispatcher (e.g., Dispatchers.IO or Dispatchers.Default).
- Never block the main thread with calls like Thread.sleep(), runBlocking(), or long synchronous operations.
- Use async patterns instead of long-running tasks.
- Use timeouts and cancellation to avoid waiting indefinitely for slow tasks or APIs.
- Optimize startup work and delay non-critical initialization so the UI loads quickly.

To debug ANRs:

- Check the traces.txt file to identify what blocked the main thread at the time of the ANR.
- Use Android Studio Profiler to track CPU usage and confirm if the UI thread is overloaded.
- Enable StrictMode in debug builds to detect disk access or network calls happening on the main thread.
- Use monitoring tools like Firebase Performance or Crashlytics to detect slow frames or freezes in production.

</details>

## Startup Optimization

<details>
<summary><strong>How would you reduce app startup time?
</strong></summary>

To reduce startup time, I focus on loading only what’s needed for the first screen and push everything else later. I avoid heavy work on the main thread and move database setup, large object initialization, or analytics to background threads.

I also use lazy initialization so objects are created only when they’re actually needed. For UI, I make sure the first screen layout is lightweight because heavy view hierarchies slow rendering.

</details>

<details>
<summary><strong>How do you reduce cold start time?
</strong></summary>

To improve cold start time, I focus on reducing work before the first frame. That means avoiding heavy initialization in Application and delaying things like analytics, large objects, and database warm-up until after the UI is visible.

I also check the launch screen layout — fewer nested views means faster rendering. For dependencies, I use lazy or on-demand initialization instead of creating everything upfront.

</details>

## APK Optimization

<details>
<summary><strong>How to reduce APK size?
</strong></summary>

To reduce APK size, I usually start with the basics — enabling R8 with code shrinking and minification so unused classes and methods are removed. Then I use Android App Bundle instead of a single APK, which helps deliver only the resources needed for each device like screen density or CPU architecture.

I also clean up resources — removing unused assets, converting images to WebP or using vector drawables where possible. For native libraries, I split by ABI instead of packaging all of them. And I try to avoid heavy libraries; if a library is too big for a small feature, I replace it with a lighter option or write it myself.

With these steps, I’ve reduced app size significantly in past projects

</details>

<details>
<summary><strong>What is R8/ProGuard?
</strong></summary>

ProGuard and R8 are tools in Android used mainly for shrinking and optimizing code. They remove unused classes, methods, and resources, and they also obfuscate the code so it’s harder to reverse-engineer.

</details>

<details>
<summary><strong>What is App Bundle and how does it differ from APK?
</strong></summary>

The difference is: an APK is a single installable package, and everyone gets the same file even if half the content isn’t needed. But with an App Bundle, the Play Store builds and delivers a smaller, device-specific APK, which reduces download size and install size.

</details>

## Image Optimization

<details>
<summary><strong>What are image loading optimizations? 
</strong></summary>

- Picasso is the simplest and oldest—good for basic loading but limited with GIFs and complex transformations.
- Glide is more powerful and optimized for large images and video thumbnails, and it handles caching
- Coil is newer, built with Kotlin and Coroutines, lighter, and integrates well with Jetpack Compose

In production, I usually optimize by resizing images, using placeholders, enabling caching strategies, and avoiding loading full-resolution assets unnecessarily. This keeps scrolling smooth and reduces memory spikes

</details>

# LEVEL 14 : Testing

<details>
<summary><strong>What's the difference between Unit Tests, Integration Tests, and UI Tests (Instrumentation Tests)?
</strong></summary>

Unit tests check one small piece of code, like a function or ViewModel, without Android or network.
Integration tests check how multiple parts work together, like ViewModel + Repository + DB.
UI tests (Instrumentation tests) check the actual app on a device, testing screens, clicks, navigation, animations — basically what the user sees.

</details>

<details>
<summary><strong>What is Espresso basics?
</strong></summary>

Espresso is Android’s testing framework used for UI tests.
It lets you find a view, perform an action, and then check the result.
For example: click a button and verify if a new text appears.

</details>

# LEVEL 15: Security

## Data Security

<details>
<summary><strong>How do you store sensitive data securely?
</strong></summary>

For sensitive data like tokens or API keys, I never store them in plain text.
I use EncryptedSharedPreferences for small items, because it encrypts everything.
Another option is to keep keys on a secure server and fetch them when needed, so nothing sensitive stays inside the app.
And for native-level protection, I can put secrets inside NDK/C++, which makes it harder to extract.

</details>

<details>
<summary><strong>What is Android Keystore and how to use it?
</strong></summary>

Android Keystore is a secure system inside the device that stores encryption keys safely.
The keys never leave the hardware, so even if someone roots the phone or decompiles the app, they can’t read the keys.
We use it to encrypt things like tokens, passwords, or any sensitive data.

</details>

<details>
<summary><strong>How to protect API keys in Android?
</strong></summary>

First, I move keys to a secure backend and fetch them when needed — this is the safest option.
If I must keep something inside the app, I store it using Android Keystore + EncryptedSharedPreferences, so even if the device is compromised, the raw key isn’t exposed.
For extra protection, I sometimes hide parts of the logic in NDK/C++, which makes reverse-engineering much harder.

</details>

# LEVEL 16: Build System & CI/CD

## Gradle

<details>
<summary><strong>Explain Gradle basics and optimization
</strong></summary>

Gradle is the build system for Android uses to compile code, download dependencies, create APKs/app bundles, and run tasks.
Every module has a build.gradle file that tells Gradle what plugins to use, which libraries to include, and how to build the app.

</details>

<details>
<summary><strong>What are build flavors and variants?
</strong></summary>

Build flavors are different versions of the same app — for example dev, staging, and production.
Each flavor can have its own API URL, icons, or settings.

Build variants are the final combinations of flavors + build types (like debug or release).
So if I have 2 flavors and 2 build types, I get 4 variants.

</details>

<details>
<summary><strong>How do you handle dependency management?
</strong></summary>

I handle dependency management by keeping all versions in one central place, like a versions.toml or a single dependencies.gradle file.
This keeps the project clean and makes updates easier.
I also avoid adding heavy or unused libraries, because they slow down build time and increase APK size.

</details>

# LEVEL 17: Android TV & OTT Development

## TV Fundamentals

<details>
<summary><strong>What are the biggest differences between developing for Mobile Phones and Android TV?
</strong></summary>

The biggest difference is how the user interacts.
On mobile, everything is touch-based.
On Android TV, everything is controlled by the remote, so focus navigation becomes the main challenge.

The UI is also very different.
Phone screens are small and close, so we can use dense layouts.
TV screens are big and far, so items must be larger, spaced out, and easy to read from distance.

Performance needs more care on TV because most TV devices have weaker hardware than phones.
So smooth scrolling, optimized images, and lightweight adapters are important.

</details>

<details>
<summary><strong>Explain the TV-specific activity lifecycle (why onStop vs onPause)
</strong></summary>

On Android TV, onPause doesn’t always mean the activity is hidden. System overlays like volume or Assistant can trigger onPause, but the user can still see your screen. So if you stop video or release resources in onPause, it causes glitches.

onStop is the real signal that your activity is no longer visible on TV. That’s why TV apps do important cleanup—like stopping the player or heavy work—in onStop instead of onPause

</details>

<details>
<summary><strong>How do you design a TV UI that is effective for a "10-foot experience"?
</strong></summary>

A good TV UI follows the ‘10-foot experience’ rule, meaning users sit far away and use a remote, not touch.
So the design must be simple, big, and easy to navigate with arrows.
I focus on large text, high contrast, big cards, and clear spacing so things are readable from distance.

Every screen must work with directional focus. Nothing should require precision. The user should always know where the focus is, and moving up/down/left/right should feel predictable.
Animations need to be smooth and minimal—no fast or complex transitions because they feel confusing on TV.

</details>

<details>
<summary><strong>What are the best practices for TV app navigation (DPad, remote control)?
</strong></summary>

On TV, navigation must work only with the D-Pad or remote. Every item should be reachable in predictable up, down, left, right moves. Always keep one item focused, and highlight it clearly so the user knows where they are.

Layouts should be simple grids or lists. Avoid hiding actions or making users press too many buttons. Scroll smoothly, and at the edges of a row or column, focus should stop instead of jumping randomly

</details>

## Leanback Library

<details>
<summary><strong>What is the Leanback library?
</strong></summary>

The Leanback library is a set of Android components and helpers specifically for TV apps. It provides pre-built UI elements like Rows, Headers, BrowseFragment, and PlaybackSupportFragment that follow Android TV design guidelines.

It handles things like focus navigation, D-Pad support, smooth scrolling, and common TV patterns, so you don’t have to build everything from scratch.

</details>

## Focus & Navigation

<details>
<summary><strong>How do you handle focus management on TV?
</strong></summary>

On Android TV, focus management is one of the most important things.
Users don’t touch the screen — they only use the D-Pad — so I make sure every clickable view is properly focusable and gives a clear highlight when focused.

I avoid putting multiple focusable views inside one item because that creates random focus jumps.
When the default focus movement isn’t correct, I manually set nextFocusUp/Down/Left/Right to control where the focus should go.

</details>

<details>
<summary><strong>How to handle focus navigation and D-pad key events?
</strong></summary>

On Android TV, we handle focus navigation mainly through D-pad keys.
For simple screens, I rely on default focus rules using focusable and nextFocusXXX.
But when the UI is custom—like carousels, grids, or big cards—I manually handle D-pad events.

I override dispatchKeyEvent() or onKeyDown(), check which D-pad key the user pressed, and then use FocusFinder to move the focus to the correct view.
This gives me full control and keeps the focus predictable on TV

</details>

<details>
<summary><strong>What are common focus pitfalls?
</strong></summary>

On TV, focus issues happen mostly because the UI wasn’t designed with D-pad in mind.
- Views are not focusable
- Wrong nextFocus attributes
- Invisible or off-screen items stealing focus
- Complex layouts (nested Rows/Columns) confuse FocusFinder
- RecyclerView items losing focus on scroll
- Animations removing a view before focus moves

</details>

## Media Playback - ExoPlayer

<details>
<summary><strong>What is ExoPlayer? How is it different from MediaPlayer?
</strong></summary>

ExoPlayer is a modern, customizable video player from Google.
It’s smoother, more flexible, and supports streaming formats like HLS, DASH, DRM, ads, and custom UI.

MediaPlayer is the old, built-in player. It’s simple but limited — fewer formats, harder to customize, and not great for streaming.

ExoPlayer is preferred for any real production app because it gives better performance, better buffering control, and full customization.

</details>

<details>
<summary><strong>Explain the key components of ExoPlayer: Player, MediaSource, TrackSelector, LoadControl
</strong></summary>

Player
It handles playback state, buffering, seeking, and interacts with the UI layer. In most cases we use ExoPlayer (the concrete implementation). It doesn’t decide what to play—just how to play it.

MediaSource
This describes what media to play and how to fetch it. Each type of stream—HLS, DASH, MP4—creates its own MediaSource. It handles manifest parsing, segment loading, and prepares the timeline that the Player will use.

TrackSelector
This decides which audio/video/text tracks to use.
For example:
language-specific audio tracks,

LoadControl
This defines buffering strategy. It controls:
how much data to buffer before starting playback,
how aggressively to buffer during playback,
when to pause/resume buffering.
It directly affects startup time, smoothness, and memory usage.

</details>

## Streaming Protocols

<details>
<summary><strong>What adaptive streaming protocols have you worked with? (HLS, DASH, SmoothStreaming)
</strong></summary>

I’ve mainly worked with HLS.

HLS
- Very common in production. I’ve used it for live and VOD streams.
- Good CDN support, easy failover, and ExoPlayer handles master playlists and rendition switching smoothly.

</details>


<details>
<summary><strong>How do you implement HLS/DASH streaming with ExoPlayer?
</strong></summary>

To integrate HLS or DASH with ExoPlayer, I mainly focus on three things.

First, I create the correct MediaSource.
For HLS, I use an HlsMediaSource, and for DASH I use a DashMediaSource.
Both of them automatically handle the manifest and adaptive bitrate part.

Second, I prepare the player.
I build an ExoPlayer instance with a DefaultTrackSelector, set the MediaSource, call prepare(), and then start playback.
If I need specific audio or video tracks, I configure the track selector accordingly.

Third, I handle streaming details.
On TV or weak networks, I sometimes use a custom LoadControl to control buffering, and I use a proper DataSource factory for network timeouts and retries.

</details>

<details>
<summary><strong>How to handle multiple bitrates (adaptive streaming)?
</strong></summary>

For multiple bitrates, I rely on ExoPlayer’s adaptive streaming system.
The manifest—either HLS or DASH—already contains different quality levels.
ExoPlayer reads that and uses the TrackSelector to pick the best track based on network speed, device capability, and video size.

The player keeps monitoring the bandwidth during playback.
If the network drops, it switches to a lower bitrate.
If the network improves, it moves back to higher quality.
All of this is seamless and doesn’t interrupt playback.

</details>

## Audio & Playback

<details>
<summary><strong>How do you manage audio focus for a media app on TV and mobile?
</strong></summary>

For audio focus, I treat TV and mobile slightly differently, but the core idea is the same.
On both platforms, I use the AudioManager or AudioFocusRequest API to request audio focus before starting playback.
If I get full focus, I start or continue playback.
If I lose focus permanently, I pause.

</details>

<details>
<summary><strong>What are the considerations for background playback on TV vs Mobile?
</strong></summary>

For background playback, the behavior is different on TV and mobile.

On mobile, background playback is common.
So I use a foreground service with a media notification, and keep the player alive while the activity goes to the background.

On TV, most apps don’t continue playback once the user leaves the screen.
TV launchers expect you to stop playback when the user presses Home or switches apps.
So I usually pause and release the player in onStop(), unless the product specifically wants audio-only background playback.

The main idea is: mobile encourages background media, TV does not.
</details>

<details>
<summary><strong>How to handle playback state restoration? / How to handle playback state restoration in ExoPlayer?
</strong></summary>

For playback state restoration, I save two things: the media position and the player state.
When the user leaves the screen, I store the current position, whether the video was playing or paused, and any selected tracks if needed.

When the user comes back, I recreate the player, seek to the saved position, and restore the play/pause state.
On TV, I do this only when the app returns to the same playback flow, because TV apps often release the player on every navigation.

</details>

## OTT Features

<details>
<summary><strong>How to implement recommendations and watch history?
</strong></summary>

For watch history, I store what the user watched, how much they watched, and the last playback position.
This usually goes into a local database first, and then I sync it with the backend so all devices stay in sync.

For recommendations, I use that watch history plus categories, genres, and viewing patterns.
The backend normally generates the recommendation list, and the app just fetches and displays it.
On Android TV, I can also push recommendations to the home screen using the Recommendations or Channels API.

</details>

<details>
<summary><strong>How to display TV recommendations?
</strong></summary>

I use that watch history plus categories, genres, and viewing patterns.
The backend normally generates the recommendation list, and the app just fetches and displays it.
On Android TV, I can also push recommendations to the home screen using the Recommendations or Channels API.

The main idea is: track user behavior accurately, sync it, and let the server decide what to recommend.
The app’s job is to store clean history and display the right content

</details>

<details>
<summary><strong>Describe how you would build a "Continue Watching" row that syncs across devices
</strong></summary>

To build a Continue Watching row, I track three things for every video: the content ID, the last watched position, and the total duration.
When playback stops or pauses for a few seconds, I save that data locally and also send it to the backend.

The backend becomes the single source of truth.
So when the user opens the app on another device — mobile, TV, or web — I fetch the synced watch history and build the Continue Watching row from that list.

On the UI side, I sort items by most recently watched and show the progress bar using the saved position.
When the user clicks an item, I start playback from the saved timestamp.

</details>

## Performance & Optimization

<details>
<summary><strong>How to handle large images/thumbnails for OTT apps?
</strong></summary>

For large images or thumbnails, I never load full-size images directly.
I use libraries like Glide or Coil but mostly prefer coil to load images asynchronously, resize them to the target view, and cache them locally.
I also use placeholders or low-res versions first, then replace them with high-res images when ready

</details>

<details>
<summary><strong>How to handle large media lists efficiently?
</strong></summary>

For large media lists, I use RecyclerView or LazyColumn with pagination so we load items in chunks, not all at once.
I enable view recycling, diffing with ListAdapter or PagingDataAdapter, and prefetch only what’s visible.
For TV, I also make sure focus handling is smooth while scrolling large grids

</details>

<details>
<summary><strong>How to optimize UI performance on low-memory TV devices?
</strong></summary>

To optimize UI on low-memory TV devices, I keep layouts simple and flat to reduce rendering cost.
I use Leanback components like VerticalGridView or RowsSupportFragment for efficient focus handling and view recycling.
Images are downscaled, loaded asynchronously, and cached, while heavy tasks run on background threads.
Animations are minimal and hardware-accelerated.

</details>

## Content Management

<details>
<summary><strong>How to cache streaming content?
</strong></summary>

To cache streaming content, I use ExoPlayer’s Cache and SimpleCache with a CacheDataSource.
This stores downloaded media segments on local storage so future playback is faster and works offline.
I set cache size limits to avoid filling the device.
For TV, I also prefetch the next few items in the playlist to make navigation smooth and reduce buffering

</details>
