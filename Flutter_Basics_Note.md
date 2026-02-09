# 🚀 Flutter Basics – Core Widgets & UI Fundamentals

This document covers Flutter basic widgets used to build UI, with definitions, usage, examples, and interview points.

---

## 1️⃣ What is a Container in Flutter?

### Definition

• Container is an **invisible box** in Flutter

• It is used for **layout and styling**

• It can contain **only one child widget**

• It combines **painting, positioning, and sizing**


---

### Why Container is Used?

• To add **margin, padding, height, width**

• To apply **color, border, radius**

• To position widgets on screen

• To decorate child widgets

---

### Key Points

• Container is a **widget + class**

• Similar to a box that stores content

• Used for UI structure and decoration

• Commonly wraps Text, Image, Button, etc.

---

### Example: Container Widget

```dart
Container(
  height: 100,
  width: 200,
  margin: EdgeInsets.all(10),
  padding: EdgeInsets.all(16),
  color: Colors.blueGrey,
  child: Text(
    "Hello Flutter",
    style: TextStyle(color: Colors.white),
  ),
)
````

---

### Interview Tip

> Container can have only **one child**, not multiple children.

---

## 2️⃣ Flutter Text Widget

### Definition

• The Text widget displays a **string of text**

• Supports **single style**

• Text can break into multiple lines based on layout constraints


---

### Example: Text Widget

```dart
Text(
  "Welcome to Flutter",
  style: TextStyle(
    fontSize: 20,
    color: Colors.black,
    fontWeight: FontWeight.bold,
  ),
)
```

---

### Common Text Styles

• fontSize

• color

• fontWeight

• letterSpacing

• textAlign


---

### Interview Tip

> Text widget is used only to display text, not for user input.

---

## 3️⃣ Flutter Center Widget

### Definition

• Center widget aligns its **child to the center**

• Centers horizontally and vertically

• Takes full available screen space

---

### Example: Center Widget

```dart
Center(
  child: Text("Centered Text"),
)
```

---

### Use Case

• Splash screens

• Loading screens

• Single-widget layouts

---

### Interview Tip

> Center widget accepts **only one child**.

---

## 4️⃣ Flutter Buttons (Button Widgets)

### Definition

• Buttons are UI elements that allow users to **trigger actions**

• Used for submitting forms, navigation, API calls, etc.

• Can be placed in dialogs, cards, forms, toolbars

---

### Types of Buttons in Flutter

1️⃣ **TextButton** (Flat Button)

2️⃣ **ElevatedButton** (Raised Button)

3️⃣ **OutlinedButton**

---

### TextButton (Flat Button)

```dart
TextButton(
  onPressed: () {
    print("Text Button Clicked");
  },
  child: Text("Click Me"),
)
```

---

### ElevatedButton (Raised Button)

```dart
ElevatedButton(
  onPressed: () {
    print("Elevated Button Clicked");
  },
  child: Text("Submit"),
)
```

---

### OutlinedButton

```dart
OutlinedButton(
  onPressed: () {
    print("Outlined Button Clicked");
  },
  child: Text("Cancel"),
)
```

---

### Ripple Effect

• Flutter automatically provides **ripple effect**

• Works on button click

• Implemented internally using **InkWell**

---

### Interview Tip

> `onPressed` must not be null, otherwise button is disabled.

---

## 5️⃣ How to Add Images in Flutter App

### Step 1: Create Assets Folder

```text
project_root/
 ├── assets/
 │   └── images/
 │       └── logo.png
```

---

### Step 2: Update pubspec.yml

```yaml
flutter:
  assets:
    - assets/images/
```

---

### Step 3: Run pub get

```bash
flutter pub get
```

---

### Step 4: Use Image in Code

```dart
Image.asset(
  'assets/images/logo.png',
  height: 100,
)
```

---

### Interview Tip

> Always restart app after adding new assets.

---

## 🔑 Quick Interview One-Liners

• Container is an invisible box for layout & decoration

• Container accepts only one child

• Text widget displays styled text

• Center widget aligns child to screen center

• Flutter provides three main button types

• Ripple effect is built-in

• Assets are configured in `pubspec.yml`

---

# 📘 Flutter Basics – Layouts, InkWell & Scroll Views

This file covers Flutter layout fundamentals, touch handling using InkWell, and scrollable widgets with real-world explanations and examples.

---

## 1️⃣ Rows & Columns in Flutter

### Definition

• One of the most common layout patterns in Flutter is arranging widgets **vertically or horizontally**  

• **Row** → arranges widgets **horizontally**  

• **Column** → arranges widgets **vertically**

---

### Row Widget (Horizontal Views)

```dart
Row(
  children: [
    Icon(Icons.star),
    Text("Rating"),
    Icon(Icons.favorite),
  ],
)
````

---

### Column Widget (Vertical Alignment Views)

```dart
Column(
  children: [
    Text("Title"),
    Text("Description"),
    ElevatedButton(onPressed: () {}, child: Text("Click")),
  ],
)
```

---

## 🔹 Main Axis & Cross Axis

### Axis Meaning

| Widget | Main Axis  | Cross Axis |
| ------ | ---------- | ---------- |
| Row    | Horizontal | Vertical   |
| Column | Vertical   | Horizontal |

---

### MainAxisAlignment Types

```dart
Column(
  mainAxisAlignment: MainAxisAlignment.spaceEvenly,
  children: [
    Text("One"),
    Text("Two"),
    Text("Three"),
  ],
)
```

**Types**

• start

• end

• center

• spaceBetween

• spaceAround

• spaceEvenly

---

### CrossAxisAlignment Types

```dart
Row(
  crossAxisAlignment: CrossAxisAlignment.center,
  children: [
    Text("Left"),
    Text("Right"),
  ],
)
```

**Types**

• start

• end

• center

• stretch

---

### Real UI Example (Pavlova Layout)

```dart
Column(
  children: [
    Image.asset('assets/images/pavlova.jpg'),
    Text("Strawberry Pavlova",
        style: TextStyle(fontSize: 22, fontWeight: FontWeight.bold)),
    Text(
      "Pavlova is a meringue based dessert named after the Russian ballerina Anna Pavlova.",
      textAlign: TextAlign.center,
    ),
    Row(
      mainAxisAlignment: MainAxisAlignment.center,
      children: [
        Icon(Icons.star, color: Colors.green),
        Text("170 Reviews"),
      ],
    ),
    Text("COOK"),
  ],
)
```

---

### Interview Tip

> Row and Column help build responsive layouts using main axis and cross axis alignment.

---

## 2️⃣ InkWell Widget in Flutter

### Definition

• InkWell is a **Material widget** in Flutter

• It responds to **touch actions**

• Provides **ripple effect** on interaction

---

### Why InkWell is Important?

• Makes non-button widgets clickable

• Adds user interaction feedback

• Used when GestureDetector does not give visual effect

---

### InkWell Supported Gestures

• onTap

• onDoubleTap

• onLongPress

• onTapDown

---

### InkWell Example

```dart
InkWell(
  onTap: () {
    print("Tapped");
  },
  onLongPress: () {
    print("Long Pressed");
  },
  onDoubleTap: () {
    print("Double Tapped");
  },
  child: Container(
    padding: EdgeInsets.all(16),
    color: Colors.blue,
    child: Text(
      "Tap Me",
      style: TextStyle(color: Colors.white),
    ),
  ),
)
```

---

### Interview Tip

> InkWell works only inside Material widgets to show ripple effect.

---

## 3️⃣ Scroll View Widgets in Flutter

### Why Scroll Widgets are Needed?

• Screen size is limited

• Content may overflow

• To avoid **RenderFlex overflow error**

---

## 🔹 SingleChildScrollView

• Scrolls a **single child**

• Used when content size is dynamic

```dart
SingleChildScrollView(
  child: Column(
    children: [
      Text("Item 1"),
      Text("Item 2"),
      Text("Item 3"),
    ],
  ),
)
```

---

## 🔹 Vertical Scroll (Default)

```dart
ListView(
  children: [
    Text("Item 1"),
    Text("Item 2"),
    Text("Item 3"),
  ],
)
```

---

## 🔹 Horizontal Scroll

```dart
SingleChildScrollView(
  scrollDirection: Axis.horizontal,
  child: Row(
    children: [
      Container(width: 100, color: Colors.red),
      Container(width: 100, color: Colors.green),
    ],
  ),
)
```

---

## 🔹 Common Scroll Widgets

• SingleChildScrollView

• ListView

• GridView

• PageView

---

### RenderFlex Overflow Error (Bottom)

❌ Error occurs when:

• Column height exceeds screen

• No scroll widget used

✅ Fix:

• Wrap Column with SingleChildScrollView

• Use Expanded / Flexible

• Use ListView instead of Column

---

### Interview Tip

> RenderFlex overflow occurs due to unbounded height or width in layouts.

---

## 🔑 Interview One-Liners

• Row aligns widgets horizontally

• Column aligns widgets vertically

• Main axis controls layout direction

• Cross axis controls opposite alignment

• InkWell adds ripple touch feedback

• Scroll widgets prevent overflow errors

• SingleChildScrollView handles large content

---


---
