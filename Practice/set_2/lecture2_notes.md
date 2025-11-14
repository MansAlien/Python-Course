# CS1011 - Variables, Expressions, and Control Flow

## 📚 Lecture 2: Making Decisions in Python

---

## 📦 Variables Deep Dive

### What is a Variable?

A **variable** is like a labeled box in computer memory where you can:
- Store data
- Retrieve data later using its name
- Change its contents anytime

**Visual Example:**
```python
x = 12.2    # Store 12.2 in variable x
y = 14      # Store 14 in variable y
x = 100     # Change x to 100 (old value is gone!)
```

Think of it like this:
- `x` is a box labeled "x"
- First we put `12.2` in the box
- Later we replace it with `100`

---

## 🏷️ Variable Naming Rules

### Must Follow These Rules:

✅ **Start with letter or underscore**
```python
name = "John"      # ✅ Good
_temp = 25         # ✅ Good
2nd_value = 10     # ❌ Can't start with number
```

✅ **Only letters, numbers, and underscores**
```python
student_age = 20   # ✅ Good
my-variable = 5    # ❌ No dashes
sum&avg = 10       # ❌ No special characters
```

✅ **Case Sensitive**
```python
age = 20           # Different from Age
Age = 25           # Different from AGE
AGE = 30           # All three are different variables!
```

---

## 💭 Mnemonic Variable Names

**Mnemonic** = Memory aid = Names that help you remember what's stored

### Bad Example (Confusing):
```python
x1q3z9ocd = 35.0
x1q3z9afd = 12.50
x1q3p9afd = x1q3z9ocd * x1q3z9afd
print(x1q3p9afd)
```
*What does this do? Nobody knows!* 😵

### Good Example (Clear):
```python
hours = 35.0
rate = 12.50
pay = hours * rate
print(pay)
```
*Oh! It calculates pay from hours and rate!* 💡

**Best Practice:** Use descriptive names that explain what the variable contains!

---

## 🔢 Arithmetic Operations

| Operator | Meaning | Example | Result |
|----------|---------|---------|--------|
| `+` | Addition | `10 + 3` | `13` |
| `-` | Subtraction | `6 - 4` | `2` |
| `*` | Multiplication | `2 * 5` | `10` |
| `/` | Division | `10 / 7` | `1.4285...` |
| `%` | Modulus (remainder) | `10 % 7` | `3` |
| `**` | Exponent (power) | `3 ** 3` | `27` |

### Understanding Modulus (%)
The `%` operator gives you the **remainder** after division:

```python
10 % 3 = 1    # 10 ÷ 3 = 3 remainder 1
15 % 4 = 3    # 15 ÷ 4 = 3 remainder 3
20 % 5 = 0    # 20 ÷ 5 = 4 remainder 0 (divides evenly!)
```

**Use cases:**
- Check if a number is even: `number % 2 == 0`
- Check if a number is odd: `number % 2 == 1`

---

## ⚖️ Comparison Operators

These operators compare values and return **True** or **False**:

| Operator | Meaning | Example | Result |
|----------|---------|---------|--------|
| `>` | Greater than | `5 > 1` | `True` |
| `<` | Less than | `5 < 2` | `False` |
| `==` | Equal to | `5 == 5` | `True` |
| `!=` | Not equal to | `4 != 10` | `True` |
| `>=` | Greater than or equal | `5 >= 6` | `False` |
| `<=` | Less than or equal | `5 <= 6` | `True` |

⚠️ **Common Mistake:** Don't confuse `=` (assignment) with `==` (comparison)!

```python
x = 5      # Assignment: store 5 in x
x == 5     # Comparison: is x equal to 5? (True)
```

---

## 🔗 Logical Operators

Combine multiple conditions together:

### 1. **AND** - Both must be True
```python
(5 > 1) and (43 > 4)    # True and True = True
(5 > 1) and (43 < 4)    # True and False = False
```

**Think:** BOTH conditions must pass

### 2. **OR** - At least one must be True
```python
(5 != 1) or (9 >= 10)   # True or False = True
(5 == 1) or (9 < 10)    # False or True = True
(5 == 1) or (9 > 10)    # False or False = False
```

**Think:** At least ONE condition must pass

### 3. **NOT** - Flips True/False
```python
not(5 >= 6)             # not False = True
not(5 < 6)              # not True = False
```

**Think:** Reverses the result

### Real-World Examples:

```python
# Check if someone can vote (age >= 18 AND is citizen)
age = 20
is_citizen = True
can_vote = (age >= 18) and is_citizen  # True

# Check if store is closed (Saturday OR Sunday)
day = "Saturday"
is_closed = (day == "Saturday") or (day == "Sunday")  # True

# Check if NOT a weekend
is_weekday = not((day == "Saturday") or (day == "Sunday"))
```

---

## 📊 Order of Operations (PEMDAS++)

Python follows a specific order when evaluating expressions:

### Priority (High → Low):

1. **`()`** - Parentheses first!
2. **`**`** - Exponents
3. **`%`, `/`, `*`** - Modulus, Division, Multiplication (left to right)
4. **`+`, `-`** - Addition, Subtraction (left to right)
5. **`==`, `!=`, `<`, `>`, `<=`, `>=`** - Comparisons
6. **`not`** - Logical NOT
7. **`and`** - Logical AND
8. **`or`** - Logical OR

### Examples:

```python
16 - 2 * 5 / 2 + 1
= 16 - 10 / 2 + 1      # Multiply first
= 16 - 5 + 1           # Then divide
= 11 + 1               # Then subtract
= 12                   # Finally add

2 * (4 - 10)
= 2 * (-6)             # Parentheses first!
= -12

(12 + 0) - 4 > 2 * 3 / 4
= 12 - 4 > 6 / 4       # Parentheses and multiply
= 8 > 1.5              # Subtract and divide
= True                 # Compare
```

**Pro Tip:** When in doubt, use parentheses to make your intention clear!

---

## 🎯 Decision Making (if statements)

Decisions allow your program to run different code based on conditions.

### 1. **if Statement** - Do something if condition is true

**Syntax:**
```python
if condition:
    # Code here runs ONLY if condition is True
    statement(s)
```

⚠️ **Important:** The code inside `if` must be **indented** (usually 4 spaces or 1 tab)

**Example 1: Simple Check**
```python
day = input("Enter the day: ")

if day == "thu":
    print("Have a nice weekend!")
```

**Example 2: Age Check**
```python
age = int(input("Enter your age: "))

if age >= 18:
    print("You are an adult!")
```

**Example 3: Even Number Check**
```python
number = int(input("Enter a number: "))

if number % 2 == 0:
    print("The number is even!")
```

---

### 2. **if-else Statement** - Do one thing or another

**Syntax:**
```python
if condition:
    # Code here runs if condition is True
    statement(s)
else:
    # Code here runs if condition is False
    statement(s)
```

**Example 1: Weekend Check**
```python
day = input("Enter the day: ")

if day == "thu":
    print("Have a nice weekend!")
else:
    print("Have a nice day!")
```

**Example 2: Pass/Fail**
```python
score = int(input("Enter your score: "))

if score >= 60:
    print("You passed!")
else:
    print("You failed. Study harder!")
```

**Example 3: Even or Odd**
```python
number = int(input("Enter a number: "))

if number % 2 == 0:
    print("The number is even")
else:
    print("The number is odd")
```

---

### 3. **if-elif-else Statement** - Multiple conditions

**Syntax:**
```python
if condition1:
    # Runs if condition1 is True
    statement(s)
elif condition2:
    # Runs if condition1 is False and condition2 is True
    statement(s)
elif condition3:
    # Runs if previous conditions are False and condition3 is True
    statement(s)
else:
    # Runs if ALL conditions are False
    statement(s)
```

**Example 1: Grading System**
```python
score = int(input("Enter your score: "))

if score >= 90:
    print("Grade: A+")
elif score >= 85:
    print("Grade: A")
elif score >= 80:
    print("Grade: B+")
elif score >= 75:
    print("Grade: B")
elif score >= 70:
    print("Grade: C+")
elif score >= 60:
    print("Grade: C")
else:
    print("Grade: F")
```

**Example 2: Extended Weekend Check**
```python
day = input("Enter the day: ")

if day == "thu" or day == "fri" or day == "sat":
    print("Have a nice weekend!")
else:
    print("Have a nice day!")
```

**Example 3: Temperature Description**
```python
temp = float(input("Enter temperature in Celsius: "))

if temp >= 40:
    print("Extremely hot!")
elif temp >= 30:
    print("Hot")
elif temp >= 20:
    print("Warm")
elif temp >= 10:
    print("Cool")
else:
    print("Cold!")
```

---

## 🔑 Key Differences

### if vs elif vs else

```python
# Using multiple if statements (ALL are checked)
if score >= 90:
    print("Excellent!")
if score >= 60:
    print("Passed!")      # This ALSO runs if score >= 90!
if score < 60:
    print("Failed!")

# Using elif (only ONE runs)
if score >= 90:
    print("Excellent!")
elif score >= 60:
    print("Passed!")      # Only runs if score < 90
else:
    print("Failed!")      # Only runs if score < 60
```

**Remember:** 
- `elif` and `else` are only checked if previous conditions were False
- Multiple `if` statements are independent and all get checked

---

## 💡 Indentation is Critical!

Python uses **indentation** (spaces/tabs) to group code:

✅ **Correct:**
```python
if age >= 18:
    print("You can vote")      # Indented - inside if
    print("You are an adult")  # Indented - inside if
print("Program done")          # Not indented - outside if
```

❌ **Wrong:**
```python
if age >= 18:
print("You can vote")          # Error! Not indented
    print("You are an adult")  # Inconsistent indentation
```

**Rule:** All code in the same block must have the same indentation level!

---

## 📝 Practice Examples

### Example 1: Positive, Negative, or Zero
```python
number = int(input("Enter a number: "))

if number > 0:
    print("The number is positive")
elif number < 0:
    print("The number is negative")
else:
    print("The number is zero")
```

### Example 2: Largest of Three Numbers
```python
a = int(input("Enter first number: "))
b = int(input("Enter second number: "))
c = int(input("Enter third number: "))

if a >= b and a >= c:
    print("Largest is:", a)
elif b >= a and b >= c:
    print("Largest is:", b)
else:
    print("Largest is:", c)
```

### Example 3: Login System
```python
username = input("Enter username: ")
password = input("Enter password: ")

if username == "admin" and password == "12345":
    print("Login successful!")
else:
    print("Invalid username or password")
```

### Example 4: Discount Calculator
```python
price = float(input("Enter price: "))

if price >= 1000:
    discount = price * 0.20      # 20% discount
    print("20% discount applied!")
elif price >= 500:
    discount = price * 0.10      # 10% discount
    print("10% discount applied!")
else:
    discount = 0
    print("No discount")

final_price = price - discount
print(f"Final price: {final_price}")
```

---

## 🎯 Key Takeaways

✅ **Variables** are named storage locations in memory  
✅ Use **mnemonic names** to make code readable  
✅ **Comparison operators** return True or False  
✅ **Logical operators** (and, or, not) combine conditions  
✅ **Order of operations** matters - use parentheses when unsure  
✅ **if** runs code only if condition is True  
✅ **if-else** runs one block or the other  
✅ **if-elif-else** handles multiple conditions (only one runs)  
✅ **Indentation** is required and must be consistent  
✅ Use `==` for comparison, `=` for assignment

---

## 🚀 Quick Reference

### Decision Making Cheat Sheet:

```python
# One condition
if condition:
    do_something()

# Two options
if condition:
    do_this()
else:
    do_that()

# Multiple options
if condition1:
    do_first()
elif condition2:
    do_second()
elif condition3:
    do_third()
else:
    do_default()
```

### Common Patterns:

```python
# Check if even
if number % 2 == 0:

# Check if in range
if 0 <= score <= 100:

# Check multiple values
if day in ["thu", "fri", "sat"]:

# Check both conditions
if age >= 18 and has_license:

# Check either condition
if is_weekend or is_holiday:
```

---

**Practice makes perfect! Try writing programs with different conditions! 💪**
