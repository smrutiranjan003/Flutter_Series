# 🧱 Dart Basics – Beginner to Interview Ready

This file explains core Dart basics with simple definitions, code examples, and step-by-step explanations.

---

# Dart Basics – First Program, Class & Object, Variables & Data Types
---

## 1️⃣ Create First Program in Dart

### Definition
A Dart program always starts execution from the main() function.  
It is the entry point of any Dart application.

---

### Example Code
```dart
import 'dart:io';

void main() {
  print('Welcome to Dart!');
  stdout.write('Enter your Name: ');
  var name = stdin.readLineSync();
  print('Welcome, $name');
}
```
---

Explanation (Line by Line)

import 'dart:io';

• Imports input/output library
• Required for user input (stdin) and output (stdout)

---
void main() {

•`main()` is the starting point
• `void` means it returns nothing

---

• Prints output with a new line

---

stdout.write('Enter your Name: ');

• Prints text without moving to next line
• Used for user prompts

---
```dart

var name = stdin.readLineSync();

```

• Reads user input from keyboard
• Stored in variable name

---

print('Welcome, $name');

• $name is string interpolation
• Prints dynamic value inside string

---

### Interview Tip

Dart program execution always begins from `main()`.

---

## 2️⃣ Dart Class and Object

### Definition

* **Class** → A blueprint or template that defines properties and behavior
* **Object** → A real instance of a class

---

### Code: Class and Object Example

```dart
class Human {
  String name = "Ram";
  int age = 25;

  void speak() {
    print('Hello, my name is $name and I am $age years old.');
  }
}

void main() {
  Human raman = Human(); // object creation
  raman.speak();
}
```

---

### Explanation

* `class Human` → defines a class
* `String name` → property (variable)
* `void speak()` → method (function)
* `Human()` → constructor call
* `raman` → object of class Human

---

### Output

```
Hello, my name is Ram and I am 25 years old.
```

---

### Interview Tip

Dart follows object-oriented programming where everything revolves around classes and objects.

---

## 3️⃣ Variables and Data Types in Dart

### Definition

* **Variable** → A container used to store data
* **Data type** → Defines what kind of data a variable can store

---

### Common Dart Data Types

| Type   | Description              |
| ------ | ------------------------ |
| int    | Whole numbers            |
| double | Decimal numbers          |
| num    | int or double            |
| String | Collection of characters |
| bool   | true / false             |
| BigInt | Very large integers      |
| var    | Auto type detection      |

---

### Code: Variables & Data Types

```dart
import 'dart:io';

void main() {
  // String (collection of characters)
  String name = "Ram";
  name = "Ram Kumar";
  print(name);

  // Integer
  int age = 21;
  print(age);

  // Decimal number
  double percentage = 99.91;
  print(percentage);

  // num (can store int or double)
  num score = 88;
  score = 88.5;
  print(score);

  // Boolean
  bool isLogin = false;
  isLogin = true;
  print(isLogin);

  // BigInt (for very large values)
  BigInt longValue = BigInt.parse(
    '536742434373499999997777788882220022464',
  );
  print(longValue);
}
```

---

### Explanation (Important)

#### String

String is a collection/array of characters.

```dart
String name = "Ram";
```

Each character in `"Ram"` is stored sequentially.

---

#### int & double

```dart
int a = 7;
double b = 99.91;
```

* `int` → whole numbers
* `double` → decimal values

---

#### num

```dart
num value = 10;
value = 10.5;
```

Can store both int and double.

---

#### bool

```dart
bool isLogin = true;
```

Used for conditions and logic.

---

#### BigInt

```dart
BigInt big = BigInt.parse('12345678901234567890');
```

Used when int limit is exceeded.

---

### Common Mistakes You Had (Fixed)

❌ Printing variable name as text

```dart
print('name'); // wrong
```

✅ Correct way

```dart
print(name);
```

❌ Assigning BigInt directly

```dart
a = 5367424343734; // wrong
```

✅ Correct way

```dart
BigInt a = BigInt.parse('5367424343734');
```

---

### Interview One-Line Summary

Dart is a strongly typed, object-oriented language where variables store typed data and execution starts from the `main()` function.

---

### Advanced Dart Topics Roadmap
---

## 1️⃣ Constructors in Dart

### Definition

A constructor is a special function used to initialize a class object.
It runs automatically when an object is created.

---

### Example Code

```dart
class Student {
  String name;
  int age;

  // Constructor
  Student(this.name, this.age);

  void display() {
    print('Name: $name, Age: $age');
  }
}

void main() {
  Student s1 = Student('Raman', 21);
  s1.display();
}
```

---

### Explanation

* `Student(this.name, this.age)` → constructor
* Automatically assigns values to variables
* Called when `Student()` is used

---

### Output

```
Name: Raman, Age: 21
```

---

### Interview Line

A constructor initializes class variables when an object is created.

---

## 2️⃣ final vs const

### Definition

| Keyword | Meaning                   |
| ------- | ------------------------- |
| final   | Value set once at runtime |
| const   | Value set at compile time |

---

### Code Example

```dart
void main() {
  final time = DateTime.now();
  print(time);

  const pi = 3.14;
  print(pi);
}
```
---

### Key Difference

* `final` → value known at runtime
* `const` → value must be fixed before execution
 
---

### Interview Trick

All `const` are final, but not all final are const.

---

## 3️⃣ Null Safety in Dart

### Definition

Null safety prevents variables from holding `null` unless explicitly allowed.

---

### Code Example

```dart
void main() {
  String name = 'Raman';
  
  String? city;
  city = 'Delhi';

  print(name);
  print(city);
}
```

---

### Important Symbols

| Symbol | Meaning           |
| ------ | ----------------- |
| ?      | Nullable variable |
| !      | Force unwrap      |
| ??     | Default value     |

---

### Example with `??`

```dart

String? data;
print(data ?? 'No Data');

```
---

### Interview Line

Null safety helps avoid runtime null reference errors.

---

## 4️⃣ Lists, Maps & Sets

### 📌 List (Ordered, allows duplicates)

```dart

void main() {
  List<String> subjects = ['Math', 'Science', 'Math'];
  print(subjects);
}

```
---

### Output

```
[Math, Science, Math]

```
---

### Interview Tip

Every Dart application starts executing from the `main()` function.

---
### 📌 Map (Key–Value pair)

```dart

void main() {
  Map<String, int> marks = {
    'Math': 90,
    'Science': 85,
  };
  print(marks['Math']);
}

```
---

### Output

```
90

```
---
### 📌 Set (Unique values only)

```dart

void main() {
  Set<int> numbers = {1, 2, 2, 3};
  print(numbers);
}

```
---

### Output

```
{1, 2, 3}

```
---
Interview Summary

* `List` → ordered collection
* `Map` → key-value storage
* `Set` → unique items only

---

## 5️⃣ var vs dynamic (IMPORTANT)

```dart
void main() {
  print('Welcome to Dart!');

  // dynamic example
  dynamic section;
  section = "D";     // String
  section = 7;       // int
  section = false;   // bool

  print(section);

  // var example
  var rollno = 7;
  rollno = 17;
  // rollno = "Seven"; ❌ NOT allowed

  var subject = "Maths";
  subject = "Hindi";

  print(subject);
}

```

---

### Difference Table

| Feature             | var  | dynamic |
| ------------------- | ---- | ------- |
| Type fixed          | Yes  | No      |
| Can change type     | No   | Yes     |
| Compile-time safety | High | Low     |
| Recommended         | Yes  | Limited |

---

### Interview Line

`var` is type-safe, `dynamic` bypasses type checking.

---

## 6️⃣ Dart for Flutter Interview Q&A (Fresher → Advance)

### Basic Level

Q1. What is Dart?

Dart is an object-oriented programming language used to build Flutter apps.

Q2. Why Dart for Flutter?

Because of fast compilation, null safety, and UI optimization.
  
---

### Intermediate Level

Q3. Difference between Stateless and Stateful widget?

Stateless has no state change, Stateful can rebuild UI dynamically.

Q4. What is `BuildContext`?

It represents the location of a widget in the widget tree.

---

### Advanced Level

Q5. What is hot reload?

It updates UI instantly without restarting the app.

Q6. Why null safety is important in Flutter?

To prevent crashes caused by null values at runtime.

---

### Final One-Line Summary (Interview Gold)

Dart is a null-safe, object-oriented language where constructors initialize objects, collections manage data efficiently, and type safety improves Flutter app stability.

---

## 1️⃣ Dart Functions

### What is a Function?

A function is a **block of reusable code** that performs a specific task.

---

### Basic Function

```dart
void greet() {
  print('Welcome to Dart');
}

void main() {
  greet();
}
````

**Explanation**

* `void` → returns nothing
* `greet()` → function name
* Called inside `main()`

---

### Function with Parameters

```dart
void greetUser(String name) {
  print('Hello $name');
}

void main() {
  greetUser('Raman');
}
```

---

### Function with Return Value

```dart
int add(int a, int b) {
  return a + b;
}

void main() {
  int result = add(3, 4);
  print(result);
}
```

---

### Interview Line

> Functions help write clean, reusable, and testable code.

---

## 2️⃣ Arrow Syntax (`=>`)

### What is Arrow Syntax?

Arrow syntax is a **short form for single-expression functions**.

---

### Normal vs Arrow Function

```dart
// Normal
int square(int x) {
  return x * x;
}

// Arrow
int squareArrow(int x) => x * x;
```

---

### Usage in Flutter (Very Common)

```dart
onPressed: () => print('Button Clicked');
```

---

### Interview Line

> Arrow syntax improves readability for simple functions.

---

## 3️⃣ Async, Future & Stream

This is **VERY important for Flutter jobs**.

---

## 🔹 Future (Single async value)

### Definition

A `Future` represents a value that will be available **later**.

---

### Future Example

```dart
Future<String> fetchData() async {
  await Future.delayed(Duration(seconds: 2));
  return 'Data Loaded';
}

void main() async {
  String data = await fetchData();
  print(data);
}
```

---

### Explanation

* `async` → function runs asynchronously
* `await` → waits for Future to complete

---

### Flutter Usage

* API calls
* Database fetch
* File reading

---

## 🔹 Stream (Multiple async values)

### Definition

A `Stream` provides **continuous data over time**.

---

### Stream Example

```dart
Stream<int> numberStream() async* {
  for (int i = 1; i <= 3; i++) {
    await Future.delayed(Duration(seconds: 1));
    yield i;
  }
}

void main() async {
  await for (var value in numberStream()) {
    print(value);
  }
}
```

---

### Flutter Usage

* Firebase real-time updates
* Live location
* Chat apps

---

### Interview Difference

| Future    | Stream          |
| --------- | --------------- |
| One value | Multiple values |
| API call  | Live updates    |

---

## 4️⃣ Flutter Widgets – Interview Q&A

### Basic Level

**Q1. What is a widget?**
Everything in Flutter is a widget.

**Q2. Stateless vs Stateful?**
Stateless → no UI change
Stateful → UI changes dynamically

---

### Intermediate Level

**Q3. What is `setState()`?**
It rebuilds the UI when data changes.

**Q4. What is `BuildContext`?**
It links widgets to the widget tree.

---

### Advanced Level

**Q5. Difference between `initState()` and `build()`?**
`initState()` runs once
`build()` runs every UI update

**Q6. Why Flutter is fast?**
Because it uses its own rendering engine (Skia).

---

## 5️⃣ Real Flutter Mini Project

### 🟣 Project: Async Counter App

This project uses:

* Functions
* Arrow syntax
* Async
* Future
* Stateful widget

---

### `main.dart`

```dart
import 'package:flutter/material.dart';

void main() {
  runApp(const MyApp());
}

class MyApp extends StatelessWidget {
  const MyApp({super.key});

  @override
  Widget build(BuildContext context) {
    return const MaterialApp(
      home: CounterScreen(),
    );
  }
}
```

---

### `counter_screen.dart`

```dart
import 'package:flutter/material.dart';

class CounterScreen extends StatefulWidget {
  const CounterScreen({super.key});

  @override
  State<CounterScreen> createState() => _CounterScreenState();
}

class _CounterScreenState extends State<CounterScreen> {
  int count = 0;

  Future<void> increment() async {
    await Future.delayed(const Duration(seconds: 1));
    setState(() => count++);
  }

  @override
  Widget build(BuildContext context) {
    return Scaffold(
      appBar: AppBar(title: const Text('Async Counter')),
      body: Center(
        child: Text(
          'Count: $count',
          style: const TextStyle(fontSize: 30),
        ),
      ),
      floatingActionButton: FloatingActionButton(
        onPressed: () => increment(),
        child: const Icon(Icons.add),
      ),
    );
  }
}
```

---

### What Interviewer Sees Here

* Async handling
* Clean state update
* Arrow syntax
* Proper widget lifecycle

---

## Interview Closing Line (Use This)

> “I use Dart async features like Future and Stream to manage real-time data and build responsive Flutter UIs.”

---

## 1️⃣ What is a Function in Dart?

### Definition

A function is a block of reusable code that performs a specific task.

Instead of writing the same logic again and again, you write it once inside a function and call it whenever needed.

---

## 2️⃣ Why Do We Use Functions?

### Main Uses

### ✅ Reduce Redundancy

Without functions, you repeat the same code multiple times.

### ✅ Increase Reusability

One function can be used in many places, even inside different classes.

### ✅ Improve Readability

Code becomes cleaner, shorter, and easier to understand.

### ✅ Easy Maintenance

If logic changes, update it in one place only.

---

## 3️⃣ Parts of a Function

### Function Declaration

Tells Dart:  
• function name  
• return type  
• parameters  

### Function Definition

The actual code written inside `{ }`

### Function Calling

Using the function by its name

---

## 4️⃣ Corrected & Clean Dart Example (Your Code Fixed)

### Complete Working Code

```dart
void main() {
  print("Welcome to Dart!");

  var myC = MyClass(); // object creation

  // Function calling
  print(myC.add(5, 3));
  print(myC.add(10, 20));

  myC.printName("Shree");
  myC.printName("Flutter");
  myC.printName("Dart");
}

class MyClass {
  // Constructor
  MyClass() {
    print("MyClass Object created!");
  }

  // Function declaration + definition
  void printName(String name) {
    print(name);
  }

  // Function with return type
  int add(int no1, int no2) {
    int sum = no1 + no2;
    return sum; // must be last executable line
  }
}
````

---

## 5️⃣ Explanation Step by Step

### Object Creation

```dart
var myC = MyClass();
```

• Creates an object of `MyClass`
• Automatically calls the constructor

---

### Function Declaration + Definition

```dart
void printName(String name) {
  print(name);
}
```

• `void` → returns nothing
• `printName` → function name
• `String name` → parameter
• `print(name)` → function body

---

### Function Calling

```dart
myC.printName("Flutter");
```

• Calls the function
• Passes `"Flutter"` as argument

---

### Function With Return Type

```dart
int add(int no1, int no2) {
  int sum = no1 + no2;
  return sum;
}
```

• `int` → function must return an integer
• `return` → sends value back to caller
• Code after `return` is **unreachable**

❌ Wrong

```dart
return sum;
sum = no1 + no2; // unreachable code
```

---

## 6️⃣ `void` vs Return Type (VERY IMPORTANT)

### `void` Function

```dart
void showMessage() {
  print("Hello");
}
```

• Returns nothing
• Dart internally returns `null`
• No `return` needed

---

### Non-void Function

```dart
int add(int a, int b) {
  return a + b;
}
```

• Must return a value
• `return` is mandatory
• Return statement ends function execution

---

## 7️⃣ How Functions Reduce Redundancy

❌ Without function

```dart
print(5 + 3);
print(10 + 20);
print(7 + 9);
```

✅ With function

```dart
add(5, 3);
add(10, 20);
add(7, 9);
```

Same logic, written once, used many times.

---

## 8️⃣ How Functions Increase Reusability

The same `add()` function:
• Can be reused in other classes
• Can be reused in Flutter widgets
• Can be reused across files

That’s real-world clean coding.

---

## 9️⃣ Constructor (Quick Note)

```dart
MyClass() {
  print("MyClass Object created!");
}
```

• Special function
• Same name as class
• No return type
• Runs automatically on object creation

---

## 🔑 Interview One-Liners (Memorize These)

• A function is a reusable block of code that performs a specific task
• Functions reduce redundancy and improve code reusability
• `void` functions return nothing
• Non-void functions must return a value
• Code after `return` is unreachable
• Constructor is a special function used to initialize objects

--- 
# Dart List (Collection) – Basics to Operations

## What is a Dart List?

Dart List is a **collection of multiple data**.  
It is similar to an **array**, which is an **ordered collection of objects**.

### Key Points
- Ordered collection
- Uses **index** (starts from 0)
- Stores **elements**
- Declared using **square brackets `[ ]`**
- Elements are separated using **comma `,`**

---

## Syntax

```dart
var listName = [element1, element2, element3];
````

* `[]` → defines a list
* `,` → separates elements
* `index` → position of element
* `element` → actual stored value

---

## Dart List Example Code

```dart
/*dart list -> collection of multiple data.
similar to an array which is the ordered collection of the objects.
syntax declaring:?  role of [] and ,
index, element 

*/
//import 'package:flutter/cupertino.dart'; 
void main() {
    var listNo = [10, 20, 30, 40];
    listNo.add(88);
    
    //blank list
    var names = [];
    names.add("Meera");
    names.add("Arjun");
    names.add("Dhruv");
    print("$names");
    print("listNo");
     //update
    //names[0] = "Mira";
    //names.addAll(listNames);
    
    // diff add and insert
    //insert //use for particular index
    //names.insert(5,100);
    //names.insertAll(6, listNo);
    
    //replace 
    listNo.replaceRange(0, 3, [1, 2, 3]);
    print("listNo");
    
    //remove
    listNo.remove(40);
    //remove add
    listNo.removeAt(1);
    listNo.removeAt(1);
    
    listNo.removeRange(0, 5);
    //operation you must know
      print("Length: ${listNo.length}");
      print("Reverse: ${listNo.reversed}");
      print("First: ${listNo.first}");
      print("Last: ${listNo.last}");
      print("Is Empty: ${listNo.isEmpty}");
      print("Is Not Empty: ${listNo.isNotEmpty}");
      print("Element At 2nd index: ${listNo.elementAt(2)}");
    
  print("$names");
}
```

---

## Important List Operations You Must Know (Interview Focus)

* `add()` → adds element at the end
* `insert()` → adds element at a specific index
* `replaceRange()` → replaces multiple elements
* `remove()` → removes specific value
* `removeAt()` → removes element by index
* `removeRange()` → removes multiple elements

---

## Common Properties

* `length` → number of elements
* `reversed` → reverse order
* `first` → first element
* `last` → last element
* `isEmpty` → checks if list is empty
* `isNotEmpty` → checks if list has data
* `elementAt(index)` → element at given index

---

## Interview One-Liner

A Dart List is an ordered collection of objects accessed using index values and supports dynamic operations like add, remove, and replace.


# Maps and Hash Maps in Dart

## Maps in Dart

• In Dart programming, Maps are dictionary-like data types that exist in key-value form (known as lock-key).  
• There is no restriction on the type of data that goes in a map data type.  
• Maps are very flexible and can mutate their size based on the requirements.  
• It is important to note that all locks (keys) need to be unique in a map data type.  

### Syntax

```

var map_name = {key1: value1, key2: value2, ...};

````
## Explanation of the Given Dart Map Code

This Dart program demonstrates how **Maps** work in Dart, how to create them, update values, perform common operations, and why they are important for real-world use cases like JSON and APIs.

---

### 1️⃣ Creating a Map Using Literal Syntax

```dart
var map_name = {
  'Key1':'Value1',
  'Key2':2,
  'Key3':3.0,
  'Key4':false,
};
````

* A **Map** stores data in **key–value pairs**
* Keys can be `String`, `int`, etc.
* Values can be of **any data type** (`String`, `int`, `double`, `bool`)
* Curly braces `{}` are used to define a map
* Keys must be **unique**

---

### 2️⃣ Updating (Overriding) a Value in Map

```dart
map_name['Key1'] = 'Ram';
print(map_name['Key1']);
```

* Accessing a map value is done using `[]` with the key
* Assigning a new value to an existing key **overrides** the old value
* Output will be:

```
Ram
```

---

### 3️⃣ Re-declaring a Map

```dart
var map_name = {
  'Name':'Value1',
  'YOE':2,
  'Avg.Rating':3.0,
  'VEG':false,
};
```

* Here, `map_name` is **re-declared**
* The previous map is replaced by a new one
* This is allowed inside the same scope only if redeclaration rules permit

---

### 4️⃣ Creating an Empty Map and Adding Values Dynamically

```dart
var mapName = {}; //use literal
mapName['Name'] = "Ramanujan";
mapName['YOE'] = "9";
```

* An empty map is created first
* Key–value pairs are added later
* This approach is commonly used when data is added dynamically (like API responses)

---

### 5️⃣ Common Map Operations

```dart
print(mapName.isNotEmpty);
print(mapName.isEmpty);
print(mapName.length);
print(mapName.keys);
print(mapName.values);
print(mapName.containsKey('Name'));
print(mapName.containsValue(false));
print(mapName.remove('CanLocateTo0ffice'));
print(mapName);
```

Explanation of each operation:

* `isNotEmpty` → checks if map has data
* `isEmpty` → checks if map is empty
* `length` → number of key–value pairs
* `keys` → returns all keys
* `values` → returns all values
* `containsKey()` → checks if a key exists
* `containsValue()` → checks if a value exists
* `remove()` → removes a key and returns its value
* Printing the map shows the updated content

---

### 6️⃣ Updating a Key in Map Again

```dart
map_name['Name'] = 'Raman';
print(map_name);
```

* Updates the value of existing key `'Name'`
* Demonstrates mutability of Dart Maps

---

### 7️⃣ Maps and JSON / APIs

```dart
// json use for dynamic.
// when u use json. API formation large. Role of map is important
```

* Maps are the **foundation of JSON**
* API responses are usually converted into `Map<String, dynamic>`
* Flutter heavily relies on Maps for backend communication

---

### 8️⃣ Fetching Values from Map

```dart
print(map_name['Key2']);
print(map_name['key7']); //case sensitive
```

* Values are fetched using `map[key]`
* Dart Maps are **case-sensitive**
* If a key does not exist, output will be `null`

---

## Key Takeaways

* Maps store data in **key–value format**
* Keys must be **unique**
* Maps are **mutable** (can change size and values)
* Used extensively for **JSON, APIs, and dynamic data**
* Access values using `[]`
* Maps are **case-sensitive**

---

## Interview One-Liner

In Dart, Maps are dynamic key–value collections used mainly for JSON handling, API data, and structured data storage.


## Important Notes

* Keys in a map are **unique**
* Values can be of **any data type**
* Maps are widely used in **JSON** and **API data handling**
* Access values using **square brackets `[key]`**
* Maps are **case-sensitive**

---

## Interview One-Liner

A Map in Dart is a dynamic key-value collection used heavily for JSON handling and API data management.

# FINAL vs CONST in Dart – Explanation (Based on Your Notes)

This document explains the **difference between `final` and `const` in Dart**, how they behave at compile time and runtime, and clarifies the points you mentioned in your code and comments.

---

## Core Difference: `final` vs `const`

### `final`
- Value is assigned **once**
- Value is decided at **runtime**
- Variable **cannot be reassigned**
- Object **can be mutable** (can change internal data)

### `const`
- Value is assigned **once**
- Value must be known at **compile time**
- Variable **cannot be reassigned**
- Object is **completely immutable**

---

## Understanding Your Code Step by Step

### 1️⃣ Using `final`

```dart
final name = "Raman";
name = "Ramanujan";
````

❌ **Error Explanation**

* `final` means the variable can be assigned **only once**
* Reassigning it again is not allowed

✅ Correct understanding:

> `final` variables cannot be reassigned once initialized

---

### 2️⃣ Declaring `final` Without Initialization

```dart
final String name;
name = "Ramanujan";
```

✅ **This is allowed**

* `final` variables can be declared first
* They must be initialized **before use**
* Assignment can happen later, but only once

---

### 3️⃣ `final` with `var` (Not Allowed)

```dart
final String name;
```

✅ Correct

```dart
final var name; // ❌ Not allowed
```

Explanation:

* `final` already handles immutability
* `var` is for type inference
* Using both together makes no sense

---

### 4️⃣ `final dynamic` Confusion

```dart
final dynamic name;
```

Explanation of your point:

* `dynamic` allows changing **type**
* `final` allows assignment **only once**
* So using `dynamic` with `final` is **logically useless**
* You can assign only once anyway

✅ Correct understanding:

> `dynamic` loses its benefit when combined with `final`

---

### 5️⃣ Using `const`

```dart
const name = "Raman";
name = "Ajay";
```

❌ Error Explanation:

* `const` variables must be initialized **immediately**
* They are **compile-time constants**
* Reassignment is never allowed

Correct rule:

> When using `const`, initialization is mandatory at declaration

---

### 6️⃣ `const` Cannot Change at Runtime

```dart
const name = "Raman";
```

* Value is fixed before program runs
* Cannot depend on runtime data (user input, API, DateTime, etc.)

---

### 7️⃣ `final` with List (Important Concept)

```dart
final names = ["Raman", "Aman", "Ramanujan", "Rajiv"];
```

Key points:

* `names` reference cannot be reassigned
* **But list content can be modified**

```dart
names.add("Priya"); // ✅ Allowed
```

❌ Not allowed:

```dart
names = ["Pooja", "Prem"];
```

Explanation:

* `final` locks the **reference**, not the object
* You can modify elements
* You cannot point it to a new list

---

### 8️⃣ Trying to Change Data Type

```dart
names = [1, 2, 3, 4];
```

❌ Error:

* `names` was inferred as `List<String>`
* Dart is strongly typed
* You cannot change the type

---

## Quick Comparison Table

| Feature           | final          | const             |
| ----------------- | -------------- | ----------------- |
| Assignment        | Once           | Once              |
| Time              | Runtime        | Compile time      |
| Initialization    | Can be later   | Must be immediate |
| Reassign variable | ❌             | ❌               |
| Modify object     | ✅             | ❌               |
| Used for          | Runtime values | Fixed constants   |

---

## Interview-Ready One-Liners

* `final` variables are initialized once and decided at runtime
* `const` variables are compile-time constants
* `final` allows object mutation, `const` does not
* Use `final` for API data, user input, runtime values
* Use `const` for fixed values like colors, dimensions, literals

---

## Simple Rule to Remember

> **If the value comes at runtime → use `final`**
> **If the value is fixed forever → use `const`**

---

# Conditional Programming in Dart

## What is Conditional Programming?

Conditional programming means **controlling the flow of execution based on conditions**.

In simple words:
> When we want to **navigate or divert code execution according to a condition**, we use conditional statements.

### Real-life Examples
- Login page → check username & password  
- Dialog box → show success or error  
- Navigation → open next screen only if condition is true  

All these depend on **conditions returning true or false**.

---

## Types of Conditional Statements in Dart

Dart supports the following conditional constructs:

1. `if`
2. `if – else`
3. `if – else if – else`
4. Nested `if`
5. Logical operators (`&&`, `||`, `!`)

We’ll go step by step.

---

## 1️⃣ `if` Statement

### Syntax
```dart
if (condition) {
  // code executes if condition is true
}
````

### Example

```dart
void main() {
  int age = 20;

  if (age >= 18) {
    print("Eligible to vote");
  }
}
```

### Explanation

* Condition returns a **boolean**
* If condition is `true`, block executes
* If condition is `false`, block is skipped

---

## 2️⃣ `if – else` Statement

### Syntax

```dart
if (condition) {
  // true block
} else {
  // false block
}
```

### Example

```dart
void main() {
  int marks = 35;

  if (marks >= 40) {
    print("Pass");
  } else {
    print("Fail");
  }
}
```

### Explanation

* Either `if` block OR `else` block runs
* Both can never execute together

---

## 3️⃣ `if – else if – else` Ladder

Used when **multiple conditions** are involved.

### Example (Your Code Explained)

```dart
void main() {
  var a = 100;
  var b = 50;

  if (a > 200 && b > 100) {
    // both conditions must be true
    print("Block 1");
  } else if (a < 50) {
    print("Block 2");
  } else if (a > 80) {
    print("Block 3");
  } else if (a == 77) {
    print("Block 4");
  } else {
    print("Block ELSE");
  }
}
```

### Step-by-step Execution

* `a > 200 && b > 100` → false
* `a < 50` → false
* `a > 80` → true ✅
* Execution stops here
* Output:

```
Block 3
```

### Important Rule

> Only **one block** executes in `if–else if–else`

---

## 4️⃣ Logical Operators in Conditional Programming

### `&&` (AND Operator)

* All conditions must be **true**
* If one is false → result is false

```dart
if (a > 200 && b < 10) {
  print('Block 1');
} else {
  print('Block 2');
}
```

### Explanation

* AND gate logic
* Used in **login validation**
* Username AND password must be correct

---

### `||` (OR Operator)

* Any one condition must be **true**

```dart
if (a > 200 || b < 10) {
  print('Block 1');
} else {
  print('Block 2');
}
```

### Explanation

* OR gate logic
* Used when **multiple options are acceptable**

---

### `!` (NOT Operator)

* Reverses boolean value

```dart
bool isLogin = false;

if (!isLogin) {
  print("User not logged in");
}
```
---

## 5️⃣ AND vs OR vs IF–ELSE (Difference)

| Feature     | AND (`&&`)            | OR (`||`)              | if–else              |
|------------|------------------------|-------------------------|----------------------|
| Condition  | All conditions true    | Any one condition true | Single condition     |
| Use case   | Login validation       | Optional logic         | Decision making      |
| Result     | Strict checking        | Flexible checking      | Flow control         |


### Quick interview tip

* **AND (`&&`)** is used when *everything must be correct* (username **and** password).
* **OR (`||`)** is used when *any one condition is enough* (email **or** phone login).
* **if–else** controls *which path your program follows*.

---

## 6️⃣ Nested `if` Statement

When one condition depends on another.

### Example (Your Code Explained)

```dart
void main() {
  var a = 100;
  var b = 15;

  if (a > 200) {
    if (b > 100) {
      print("Both conditions true");
    }
  }
}
```

### Explanation

* Second `if` runs **only if first is true**
* Used when conditions are **hierarchical**

---

## When Do We Use Conditional Programming?

* Navigation between screens
* Login & authentication
* Dialog box decisions
* Feature enable/disable
* API response handling

---

## Interview Tips & Tricks (Fresher Friendly)

### Common Interview Questions

**Q1. What is conditional programming?**
Conditional programming controls the execution flow based on boolean conditions.

**Q2. Difference between `&&` and `||`?**
`&&` needs all conditions true, `||` needs any one true.

**Q3. What does an `if` condition return?**
It always returns a boolean value (`true` or `false`).

**Q4. Which block executes in `if–else if–else`?**
Only the **first true condition block**.

**Q5. Where is nested if used?**
When one condition depends on another.

---

## Interview One-Liners

* Conditional statements control program flow
* `if` checks conditions that return boolean values
* `&&` represents AND gate logic
* `||` represents OR gate logic
* Nested `if` is used for dependent conditions

---

## Final Summary

Conditional programming is the backbone of **decision-making logic** in Dart and Flutter.
It is heavily used in **navigation, authentication, validations, dialogs, and API handling**.

Mastering `if–else`, logical operators, and condition flow is **mandatory for Flutter interviews**.
Below is a **clean, interview-ready Markdown (.md) explanation** based exactly on what you wrote, but corrected, structured, and explained step by step. You can paste this into your notes or GitHub.

---

# 🔁 Loops in Dart

## What is a Loop?
A **loop** is a programming construct that allows us to **repeat a block of code multiple times** until a specific condition is met.

### Why do we use loops?
- To avoid writing the same code again and again
- To perform **repeated follow-ups**
- To traverse lists, maps, strings, APIs
- To handle counters, increment and decrement logic

> In simple words:  
> **When something needs to repeat → use a loop**

---

## Key Loop Concepts
- **Initialization** → starting value
- **Condition** → decides how long loop runs
- **Increment / Decrement** → counter movement
- **Termination** → loop stops when condition becomes false

---

## Types of Loops in Dart
1. `for` loop
2. `while` loop
3. `do-while` loop

---

## 1️⃣ for Loop

### When to use?
- When the **number of iterations is fixed**
- When you know **how many times** the loop should run

> Interview line:  
> **for loop is count-specific**

### Syntax
```dart
for(initialization; condition; increment/decrement) {
  // code
}
````

### Example

```dart
void main() {
  for (int a = 1; a <= 10; a++) {
    print("HELLO WORLD!");
  }
}
```

### Explanation

* `int a = 1` → starting point
* `a <= 10` → loop runs till 10
* `a++` → increment after every iteration
* Prints **HELLO WORLD!** 10 times

---

## 2️⃣ while Loop

### When to use?

* When **condition is more important than count**
* Used when iterations are **unknown**
* Mostly used in real-world logic and traversing

> Interview line:
> **while loop is condition-specific**

### Syntax

```dart
while(condition) {
  // code
}
```

### Correct Example (Fixed)

```dart
void main() {
  int no = 10;

  while (no < 50) {
    print("No is $no");
    no++;
  }
}
```

### Explanation

* Condition is checked **before execution**
* If condition is false initially → loop will not run
* Safer than do-while

---

## 3️⃣ do-while Loop

### When to use?

* When code must run **at least once**
* Even if condition is false

> Important note:
> **do-while executes first, checks condition later**

### Syntax

```dart
do {
  // code
} while(condition);
```

### Example

```dart
void main() {
  int no = 100;

  do {
    print("No is $no");
    no++;
  } while (no < 50);
}
```

### Explanation

* `no < 50` is false
* Still executes **one time**
* That’s why do-while is rarely used

---

## 🔄 Difference: for vs while vs do-while

| Feature             | for loop    | while loop        | do-while loop   |
| ------------------- | ----------- | ----------------- | --------------- |
| Condition check     | Before      | Before            | After           |
| Execution guarantee | No          | No                | Yes (once)      |
| Best for            | Fixed count | Dynamic condition | Minimum one run |
| Usage               | Counters    | Traversing, APIs  | Rare cases      |

---

## ⚠️ Common Mistakes (Interview Favorite)

❌ Semicolon after while condition

```dart
while(no < 50); // WRONG
```

❌ Infinite loop (no increment)

```dart
while(no < 50) {
  print(no);
}
```

---

## 🎯 Real-World Use Cases

* Login attempts
* API pagination
* List traversal
* Counter-based UI updates
* Validation retries

---

## 🧠 Interview Q&A (Fresher)

### Q1. What is a loop?

A loop allows executing a block of code repeatedly until a condition is met.

### Q2. Why loops are used?

To reduce code repetition and handle repetitive tasks efficiently.

### Q3. Difference between while and do-while?

* while checks condition first
* do-while executes once even if condition is false

### Q4. Which loop is most used in Flutter?

**while and for**, especially for list traversal and async logic.

### Q5. When should you avoid do-while?

When execution should depend strictly on condition.

---

## ✅ Interview Tip

> If you know the count → **for loop**

> If you know the condition → **while loop**

> If one execution is mandatory → **do-while**

---
