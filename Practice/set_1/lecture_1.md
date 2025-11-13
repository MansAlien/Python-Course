# CS1011 - Introduction to Computer Science and Programming in Python

## 📚 Lecture 1: Getting Started with Python

---

## 🧠 What is Computational Thinking?

**Computational Thinking** is the way we approach and solve problems so that a computer (or any system) can execute the solution.

Think of it like this:
- You have a problem
- You break it down into smaller steps
- You create a clear set of instructions (algorithm)
- A computer can follow these instructions

**Real-life example:** Making a sandwich
- Problem: I'm hungry
- Input: Bread, cheese, lettuce
- Process: Stack ingredients, cut in half
- Output: Edible sandwich

---

## 🔄 The Software Development Process

When creating a program, follow these **6 steps**:

### 1️⃣ **Analyze the Problem**
- What exactly needs to be solved?
- Understand the problem completely before coding

### 2️⃣ **Determine Specifications**
- What will the program do?
- Define inputs and outputs
- Example: "User enters temperature in Celsius, program outputs Fahrenheit"

### 3️⃣ **Create a Design**
- How will the program work?
- Write pseudocode (like a recipe in plain English)
- Plan your algorithm

### 4️⃣ **Implement the Design**
- Write the actual code in Python
- Translate your design into programming language

### 5️⃣ **Test/Debug the Program**
- Run the program
- Find errors (bugs)
- Fix them (debugging)
- Try to "break" your program to find all problems!

### 6️⃣ **Maintain the Program**
- Update and improve over time
- Real programs are never "finished" - they evolve

---

## 📝 Example: Temperature Converter

Let's see all steps in action:

**Analysis:** Convert Celsius to Fahrenheit

**Specification:**
- Input: Temperature in Celsius
- Output: Temperature in Fahrenheit
- Formula: F = (9/5) × C + 32

**Design (Pseudocode):**
```
1. Ask user for temperature in Celsius
2. Calculate Fahrenheit = (9/5) * Celsius + 32
3. Display the result
```

**Implementation (Python Code):**
```python
# Get input from user
celsius = float(input("Enter temperature in Celsius: "))

# Convert to Fahrenheit
fahrenheit = (celsius * 9/5) + 32

# Display result
print(f"{celsius}°C is equal to {fahrenheit}°F")
```

**Test:**
```
Input: 34.5
Output: 34.5°C is equal to 94.1°F ✓
```

---

## 🐍 What is Python?

- **General-purpose programming language** - can do almost anything!
- **Created in 1991** by Guido van Rossum
- **Easy to learn** - simple, readable syntax
- **Cross-platform** - works on Windows, Mac, Linux
- **Supports multiple programming styles** (object-oriented, functional, etc.)

**Python Components:**
1. **Functions** - reusable blocks of code
2. **Classes** - blueprints for objects
3. **Modules** - files containing functions and classes
4. **Packages** - collections of modules

---

## 🔢 Mathematical Operations

| Operator | Meaning | Example | Result |
|----------|---------|---------|--------|
| `+` | Addition | `10 + 3` | `13` |
| `-` | Subtraction | `6 - 4` | `2` |
| `*` | Multiplication | `2 * 5` | `10` |
| `/` | Division | `10 / 7` | `1.4285...` |
| `%` | Modulus (remainder) | `10 % 7` | `3` |
| `**` | Exponentiation (power) | `3 ** 3` | `27` |

**Important:** The `%` operator gives you the **remainder** after division
- `10 % 3 = 1` (because 10 ÷ 3 = 3 remainder 1)
- `15 % 4 = 3` (because 15 ÷ 4 = 3 remainder 3)

---

## 📦 Variables

A **variable** is like a labeled box that stores a value in memory.

### Creating Variables:
```python
name = "Ahmed"
age = 20
height = 1.75
```

### Variable Naming Rules:

✅ **Allowed:**
- Must start with a letter or underscore: `_city`, `name1`
- Can contain letters, numbers, and underscores: `student_age`, `test_2`
- Case-sensitive: `Age` ≠ `age` ≠ `AGE`

❌ **Not Allowed:**
- Cannot start with a number: `1st_name` ❌
- Cannot contain spaces: `first name` ❌
- Cannot use special characters: `sum&avg` ❌
- Cannot be a keyword: `import`, `if`, `for` ❌

### Examples:

| Variable Name | Valid? | Why? |
|---------------|--------|------|
| `student_name` | ✅ | Perfect! |
| `_temp` | ✅ | Can start with underscore |
| `2nd_value` | ❌ | Starts with number |
| `my-variable` | ❌ | Contains dash (-) |
| `for` | ❌ | Python keyword |

---

## 🔒 Constants

**Constants** are variables that shouldn't change.

**Convention:** Write in ALL_CAPS with underscores

```python
PI = 3.14159
MAX_STUDENTS = 30
SPEED_OF_LIGHT = 299792458
```

These follow the same rules as variables, just different style!

---

## 🔤 Data Types

Python has different types of data:

### 1. **Integers (int)**
Whole numbers without decimals
```python
age = 25
count = 100
negative = -15
```

### 2. **Floats (float)**
Numbers with decimals
```python
price = 19.99
temperature = 36.5
pi = 3.14159
```

### 3. **Strings (str)**
Text enclosed in quotes
```python
name = "John"
message = 'Hello, World!'
address = "123 Main Street"
```

### 4. **Booleans (bool)**
True or False values
```python
is_student = True
has_passed = False
```

---

## 🔣 Expressions

**Expressions** create new values through operations:

```python
x = 2 + 3           # Result: 5 (number)
print(5 * 7)        # Result: 35 (number)
print("5" + "7")    # Result: 57 (string concatenation!)
```

⚠️ **Important:** Adding strings is different from adding numbers!
- `5 + 7 = 12` (math)
- `"5" + "7" = "57"` (gluing text together)

---

## 💬 Input and Output

### Input: Getting Data from User

```python
name = input("What is your name? ")
# User types: Ahmed
# name now contains "Ahmed"
```

⚠️ **Important:** `input()` ALWAYS returns a **string**, even if user types numbers!

```python
age = input("Enter your age: ")
# User types: 20
# age is "20" (string), not 20 (number)
```

### Output: Displaying Data

```python
print("Hello, World!")
print("Your score is:", score)
print(f"Hello {name}, you are {age} years old")
```

The `print()` function shows information on the screen.

---

## 🔄 Type Conversion

Since `input()` returns strings, we need to convert them for math:

### Converting to Integer:
```python
age_text = input("Enter your age: ")  # Gets "20" as string
age = int(age_text)                   # Converts to 20 as integer
# Or in one line:
age = int(input("Enter your age: "))
```

### Converting to Float:
```python
height = float(input("Enter your height in meters: "))
# If user enters "1.75", it becomes 1.75 (number)
```

### Example: Adding Two Numbers
```python
# WRONG WAY (without conversion):
num1 = input("Enter first number: ")   # "5"
num2 = input("Enter second number: ")  # "7"
total = num1 + num2                    # "57" (string concatenation!)

# RIGHT WAY (with conversion):
num1 = int(input("Enter first number: "))   # 5
num2 = int(input("Enter second number: "))  # 7
total = num1 + num2                         # 12 (addition!)
print("Total:", total)
```

---

## 🔑 Python Keywords (Reserved Words)

These words have special meaning in Python and **cannot** be used as variable names:

```
False      class      finally    is         return
None       continue   for        lambda     try
True       def        from       nonlocal   while
and        del        global     not        with
as         elif       if         or         yield
assert     else       import     pass
break      except     in         raise
```

Example:
```python
import = 5      # ❌ ERROR! 'import' is a keyword
my_import = 5   # ✅ OK!
```

---

## 💡 Quick Tips

1. **Always test your code** with different inputs
2. **Use descriptive variable names**: `student_age` is better than `x`
3. **Remember:** `input()` returns strings - convert when needed!
4. **Start with pseudocode** before writing actual code
5. **Comments are your friend**: Use `#` to explain your code

---

## 📝 Practice Exercise

Try writing a program that:
1. Asks for the user's name
2. Asks for the user's age
3. Asks for the user's weight in kg
4. Prints all the information in a nice format

**Solution:**
```python
# Get user information
name = input("What is your name? ")
age = int(input("What is your age? "))
weight = float(input("What is your weight in kg? "))

# Display information
print(f"Hello {name}!")
print(f"You are {age} years old")
print(f"Your weight is {weight} kg")
```

---

## 🎯 Key Takeaways

✅ Computational thinking is about breaking problems into steps  
✅ Follow the 6-step software development process  
✅ Variables store data in memory  
✅ Use proper naming conventions (snake_case for variables, ALL_CAPS for constants)  
✅ `input()` returns strings - convert with `int()` or `float()` for math  
✅ `print()` displays output to the user  
✅ Test your programs thoroughly!

---

**Good luck with your Python journey! 🚀**