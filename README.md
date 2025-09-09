# C++ Relational/Logical Operators and Conditionals - Tutorial

## Learning Objectives
By the end of this tutorial, you will understand:
- How to use relational operators to compare values
- How to use logical operators to combine conditions
- How to implement decision-making with `if` statements
- How to handle multiple conditions with `if-else` statements
- How to chain conditions with `else if`

---

## Part 1: Relational Operators

Relational operators allow us to compare two values and return a boolean result (`true` or `false`).

### The Six Relational Operators

| Operator | Description | Example | Result |
|----------|-------------|---------|--------|
| `==` | Equal to | `5 == 5` | `true` |
| `!=` | Not equal to | `5 != 3` | `true` |
| `>` | Greater than | `7 > 4` | `true` |
| `<` | Less than | `3 < 8` | `true` |
| `>=` | Greater than or equal | `5 >= 5` | `true` |
| `<=` | Less than or equal | `4 <= 6` | `true` |

### Demo Code: Basic Comparisons

```cpp
#include <iostream>
using namespace std;

int main() {
    int a = 10;
    int b = 5;
    
    cout << "a = " << a << ", b = " << b << endl;
    cout << "a == b: " << (a == b) << endl;  // 0 (false)
    cout << "a != b: " << (a != b) << endl;  // 1 (true)
    cout << "a > b: " << (a > b) << endl;    // 1 (true)
    cout << "a < b: " << (a < b) << endl;    // 0 (false)
    cout << "a >= b: " << (a >= b) << endl;  // 1 (true)
    cout << "a <= b: " << (a <= b) << endl;  // 0 (false)
    
    return 0;
}
```

**Important Note:** In C++, `true` is displayed as `1` and `false` as `0` when printed.

---

## Part 2: Logical Operators

Logical operators allow us to combine multiple boolean expressions.

### The Three Logical Operators

| Operator | Description | Example | Result |
|----------|-------------|---------|--------|
| `&&` | AND (both must be true) | `true && true` | `true` |
| `||` | OR (at least one must be true) | `true || false` | `true` |
| `!` | NOT (reverses the boolean) | `!true` | `false` |

### Truth Tables

**AND Operator (`&&`)**
| A | B | A && B |
|---|---|--------|
| true | true | true |
| true | false | false |
| false | true | false |
| false | false | false |

**OR Operator (`||`)**
| A | B | A || B |
|---|---|--------|
| true | true | true |
| true | false | true |
| false | true | true |
| false | false | false |

### Demo Code: Logical Operations

```cpp
#include <iostream>
using namespace std;

int main() {
    int age = 20;
    int score = 85;
    bool hasLicense = true;
    
    // AND operator
    bool canDrive = (age >= 18) && hasLicense;
    cout << "Can drive: " << canDrive << endl;  // 1 (true)
    
    // OR operator
    bool passes = (score >= 80) || (score >= 70 && age >= 21);
    cout << "Passes: " << passes << endl;  // 1 (true)
    
    // NOT operator
    bool isMinor = !(age >= 18);
    cout << "Is minor: " << isMinor << endl;  // 0 (false)
    
    return 0;
}
```

---

## Part 3: The `if` Statement

The `if` statement executes code only when a condition is true.

### Syntax
```cpp
if (condition) {
    // code to execute if condition is true
}
```

### Demo Code: Simple If Statement

```cpp
#include <iostream>
using namespace std;

int main() {
    int temperature = 75;
    
    if (temperature > 70) {
        cout << "It's warm outside!" << endl;
    }
    
    if (temperature <= 32) {
        cout << "Water freezes at this temperature." << endl;
    }
    
    cout << "Program continues..." << endl;
    
    return 0;
}
```

**Output:**
```
It's warm outside!
Program continues...
```

---

## Part 4: The `if-else` Statement

The `if-else` statement provides an alternative path when the condition is false.

### Syntax
```cpp
if (condition) {
    // code to execute if condition is true
} else {
    // code to execute if condition is false
}
```

### Demo Code: If-Else Statement

```cpp
#include <iostream>
using namespace std;

int main() {
    int number;
    
    cout << "Enter a number: ";
    cin >> number;
    
    if (number % 2 == 0) {
        cout << number << " is even." << endl;
    } else {
        cout << number << " is odd." << endl;
    }
    
    return 0;
}
```

---

## Part 5: Multiple Conditions with `else if`

When you need to check multiple conditions, use `else if`.

### Syntax
```cpp
if (condition1) {
    // code for condition1
} else if (condition2) {
    // code for condition2
} else if (condition3) {
    // code for condition3
} else {
    // code if none of the above conditions are true
}
```

### Demo Code: Grade Calculator

```cpp
#include <iostream>
using namespace std;

int main() {
    int score;
    
    cout << "Enter your test score (0-100): ";
    cin >> score;
    
    if (score >= 90) {
        cout << "Grade: A" << endl;
    } else if (score >= 80) {
        cout << "Grade: B" << endl;
    } else if (score >= 70) {
        cout << "Grade: C" << endl;
    } else if (score >= 60) {
        cout << "Grade: D" << endl;
    } else {
        cout << "Grade: F" << endl;
    }
    
    return 0;
}
```

---

## Part 6: Complex Conditions

You can combine relational and logical operators for sophisticated decision-making.

### Demo Code: Loan Approval System

```cpp
#include <iostream>
using namespace std;

int main() {
    int age, income, creditScore;
    bool hasCollateral;
    
    cout << "Loan Application System" << endl;
    cout << "Enter age: ";
    cin >> age;
    cout << "Enter annual income: ";
    cin >> income;
    cout << "Enter credit score (300-850): ";
    cin >> creditScore;
    cout << "Do you have collateral? (1 for yes, 0 for no): ";
    cin >> hasCollateral;
    
    // Complex approval logic
    if ((age >= 18 && age <= 65) && 
        (income >= 30000) && 
        (creditScore >= 650 || (creditScore >= 600 && hasCollateral))) {
        
        cout << "Loan APPROVED!" << endl;
        
        if (creditScore >= 750) {
            cout << "You qualify for our premium rate!" << endl;
        }
        
    } else {
        cout << "Loan DENIED." << endl;
        
        // Provide specific feedback
        if (age < 18 || age > 65) {
            cout << "Reason: Age requirements not met." << endl;
        }
        if (income < 30000) {
            cout << "Reason: Insufficient income." << endl;
        }
        if (creditScore < 600 || (creditScore < 650 && !hasCollateral)) {
            cout << "Reason: Credit score requirements not met." << endl;
        }
    }
    
    return 0;
}
```

---

## Part 7: Common Mistakes and Best Practices

### Common Mistakes

1. **Using assignment (`=`) instead of comparison (`==`)**
   ```cpp
   // WRONG
   if (x = 5) { ... }  // This assigns 5 to x!
   
   // CORRECT
   if (x == 5) { ... }  // This compares x to 5
   ```

2. **Comparing floating-point numbers directly**
   ```cpp
   // PROBLEMATIC
   double result = 0.1 + 0.2;
   if (result == 0.3) { ... }  // May not work due to precision
   
   // BETTER
   if (abs(result - 0.3) < 0.0001) { ... }
   ```

3. **Unnecessary comparisons with boolean values**
   ```cpp
   // UNNECESSARY
   if (isReady == true) { ... }
   
   // BETTER
   if (isReady) { ... }
   ```

### Best Practices

1. **Use parentheses for clarity**
   ```cpp
   if ((age >= 18) && (score > 75 || hasExperience)) {
       // Clear precedence
   }
   ```

2. **Keep conditions readable**
   ```cpp
   // Instead of complex nested conditions, use variables
   bool isEligibleAge = (age >= 18 && age <= 65);
   bool hasGoodCredit = (creditScore >= 650);
   bool meetsRequirements = isEligibleAge && hasGoodCredit;
   
   if (meetsRequirements) {
       // Process application
   }
   ```

3. **Handle edge cases**
   ```cpp
   if (score >= 0 && score <= 100) {
       // Only process valid scores
       if (score >= 90) {
           cout << "Excellent!" << endl;
       }
   } else {
       cout << "Invalid score entered." << endl;
   }
   ```

---

## Summary

- **Relational operators** (`==`, `!=`, `>`, `<`, `>=`, `<=`) compare values and return boolean results
- **Logical operators** (`&&`, `||`, `!`) combine or modify boolean expressions
- **`if` statements** execute code conditionally
- **`if-else` statements** provide alternative execution paths
- **`else if`** allows multiple condition checking
- Always validate input and handle edge cases
- Use parentheses and meaningful variable names for clarity

Practice these concepts with the accompanying lab assignment to reinforce your understanding!