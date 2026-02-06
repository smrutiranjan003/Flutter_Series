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

## Advanced Dart Topics Roadmap

### Topics Covered

* Constructors in Dart
* final vs const
* Null safety
* Lists, Maps & Sets
* var vs dynamic
* Dart for Flutter Interview Q&A (Fresher → Advanced)

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

## 4️⃣ Lists, Maps & Sets

### List

```dart
List<String> subjects = ['Math', 'Science', 'Math'];
```

### Map

```dart
Map<String, int> marks = {
  'Math': 90,
  'Science': 85,
};
```

### Set

```dart
Set<int> numbers = {1, 2, 2, 3};
```

---

## 5️⃣ var vs dynamic

```dart
void main() {
  dynamic section;
  section = "D";
  section = 7;
  section = false;

  var rollno = 7;
  rollno = 17;

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

---

## 6️⃣ Dart for Flutter Interview Q&A

### Basic

* What is Dart?
  Dart is an object-oriented language used to build Flutter apps.

### Intermediate

* Stateless vs Stateful widget
  Stateless has no state change, Stateful can rebuild UI.

### Advanced

* What is hot reload?
  Updates UI instantly without restarting the app.

---

### Final Interview Gold Line

Dart is a null-safe, object-oriented language where constructors initialize objects, collections manage data efficiently, and type safety improves Flutter app stability.

```

```
