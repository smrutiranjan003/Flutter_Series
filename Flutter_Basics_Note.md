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

