# Dart Basics – Beginner to Interview Ready

---

## 1️⃣ First Program in Dart

### Definition
A Dart program always starts from the `main()` function.  
`main()` is the entry point where execution begins.

---

### Code: First Dart Program
```dart
void main() {
  print('Welcome to Dart!');
}
````

---

### Explanation

* `void` → means the function returns nothing
* `main()` → entry point of Dart program
* `print()` → prints output to console

---

### Output

```
Welcome to Dart!
```

---

### Interview Tip

Every Dart application starts executing from the `main()` function.

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
