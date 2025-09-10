# C++ Conditionals Lab Assignment
## Relational/Logical Operators and If-Else Statements

**Estimated Time:** 2-3 hours  
**Points:** 100 points total  
**Due Date:** [Insert your due date]

---

## Lab Objectives
- Practice using relational operators for comparisons
- Implement logical operators to combine conditions
- Create programs using if, if-else, and else-if statements
- Develop problem-solving skills with conditional logic
- Handle user input validation

---

## Pre-Lab Setup Instructions

### Step 1: Create Your Project Structure
1. Create a new folder named `Lab_Conditionals_[YourLastName]`
2. Inside this folder, you'll create separate `.cpp` files for each exercise
3. Make sure you have a C++ compiler ready (Code::Blocks, Visual Studio, g++, etc.)

### Step 2: Template for All Programs
Use this template as the starting point for each program:

```cpp
#include <iostream>
using namespace std;

int main() {
    // Your code goes here
    
    return 0;
}
```

---

## Exercise 1: Number Comparison Tool (15 points)
**File name:** `exercise1_comparison.cpp`

### Requirements
Create a program that compares two numbers entered by the user and displays all possible relationships between them.

### Detailed Instructions

1. **Declare Variables**
   ```cpp
   int num1, num2;
   ```

2. **Get User Input**
   - Prompt the user to enter the first number
   - Store it in `num1`
   - Prompt the user to enter the second number
   - Store it in `num2`

3. **Display All Comparisons**
   Use `cout` statements to show the results of ALL six relational operators:
   - Equal to (`==`)
   - Not equal to (`!=`)
   - Greater than (`>`)
   - Less than (`<`)
   - Greater than or equal (`>=`)
   - Less than or equal (`<=`)

4. **Format Your Output**
   Your output should look like this:
   ```
   Enter first number: 10
   Enter second number: 5
   
   Comparison Results:
   10 == 5 is: 0
   10 != 5 is: 1
   10 > 5 is: 1
   10 < 5 is: 0
   10 >= 5 is: 1
   10 <= 5 is: 0
   ```

### Testing Requirements
Test your program with:
- Two different numbers (e.g., 10 and 5)
- Two equal numbers (e.g., 7 and 7)
- A negative and positive number (e.g., -3 and 8)

---

## Exercise 2: Logical Operators Practice (15 points)
**File name:** `exercise2_logical.cpp`

### Requirements
Create a program that demonstrates logical operators using a student's academic information.

### Detailed Instructions

1. **Declare Variables**
   ```cpp
   int mathScore, englishScore, age;
   bool hasAttendance, isEnrolled;
   ```

2. **Get User Input**
   - Math score (0-100)
   - English score (0-100)
   - Age
   - Has good attendance (enter 1 for true, 0 for false)
   - Is currently enrolled (enter 1 for true, 0 for false)

3. **Create Logical Expressions**
   Calculate and display these boolean results:
   - `passingBoth`: Student passes both subjects (both scores >= 70)
   - `passingEither`: Student passes at least one subject (either score >= 70)
   - `eligibleForAdvanced`: Age >= 16 AND passing both subjects AND has good attendance
   - `needsHelp`: NOT passing both subjects OR NOT enrolled
   - `honorRoll`: Both scores >= 90 AND good attendance AND enrolled

4. **Display Results**
   Show each calculation with explanatory text:
   ```
   Enter math score: 85
   Enter English score: 92
   Enter age: 17
   Has good attendance (1/0): 1
   Is enrolled (1/0): 1
   
   Results:
   Passing both subjects: 1
   Passing at least one subject: 1
   Eligible for advanced classes: 1
   Needs help: 0
   Honor roll student: 1
   ```

---

## Exercise 3: Simple Grade Calculator (20 points)
**File name:** `exercise3_grades.cpp`

### Requirements
Create a program that converts a numerical score to a letter grade using if-else statements.

### Detailed Instructions

1. **Input Validation First**
   - Get the user's score
   - Use an `if` statement to check if the score is between 0 and 100
   - If invalid, display an error message and end the program

2. **Grade Calculation Logic**
   Use `if-else if-else` structure with these criteria:
   - A: 90-100
   - B: 80-89
   - C: 70-79
   - D: 60-69
   - F: 0-59

3. **Enhanced Features**
   Add these additional features:
   - Display "Perfect Score!" for exactly 100
   - Display "Excellent work!" for scores 95-99
   - Display "Good job!" for scores 85-94
   - Display "Needs improvement" for scores below 70

4. **Sample Output**
   ```
   Enter your test score (0-100): 87
   
   Your grade is: B
   Good job!
   ```

### Testing Requirements
Test with: 100, 95, 87, 75, 65, 45, and -5 (invalid)

---

## Exercise 4: Age Category Classifier (15 points)
**File name:** `exercise4_age.cpp`

### Requirements
Create a program that classifies people into age categories and determines eligibility for various activities.

### Detailed Instructions

1. **Get User Input**
   - Prompt for age
   - Validate that age is positive

2. **Age Classification**
   Use nested if-else statements to classify:
   - Infant: 0-2 years
   - Child: 3-12 years
   - Teen: 13-19 years
   - Adult: 20-64 years
   - Senior: 65+ years

3. **Activity Eligibility**
   Based on age, determine eligibility for:
   - Can vote: age >= 18
   - Can drive: age >= 16
   - Can drink alcohol: age >= 21
   - Senior discount: age >= 65
   - Child fare: age <= 12

4. **Output Format**
   ```
   Enter your age: 17
   
   Age Category: Teen
   
   Eligibilities:
   Can vote: No
   Can drive: Yes
   Can drink alcohol: No
   Senior discount: No
   Child fare: No
   ```

---

## Exercise 5: Weather Advisory System (20 points)
**File name:** `exercise5_weather.cpp`

### Requirements
Create a weather advisory system that provides recommendations based on temperature and conditions.

### Detailed Instructions

1. **Input Variables**
   ```cpp
   int temperature;
   char condition; // 'S' for sunny, 'R' for rainy, 'C' for cloudy, 'N' for snowy
   bool isWindy;
   ```

2. **Input Collection**
   - Get temperature in Fahrenheit
   - Get weather condition (single character)
   - Get wind status (1 for windy, 0 for calm)

3. **Advisory Logic**
   Create a complex decision tree:

   **Temperature-based advisories:**
   - Temperature > 90: "Heat warning"
   - Temperature 70-90: "Pleasant weather"
   - Temperature 32-69: "Cool weather"
   - Temperature < 32: "Freezing warning"

   **Condition-specific advice:**
   - Sunny + hot (>85): "Use sunscreen and stay hydrated"
   - Rainy: "Carry an umbrella"
   - Snowy: "Drive carefully and dress warmly"
   - Cloudy + cool (<50): "Light jacket recommended"

   **Wind modifications:**
   - If windy AND temperature < 50: "Wind chill factor - dress extra warm"
   - If windy AND rainy: "Storm warning - stay indoors if possible"

4. **Complex Example Logic**
   ```cpp
   if (temperature > 90) {
       cout << "Heat warning!" << endl;
       if (condition == 'S') {
           cout << "Use sunscreen and stay hydrated!" << endl;
       }
   } else if (temperature >= 70) {
       cout << "Pleasant weather!" << endl;
   }
   // Continue with other conditions...
   
   if (isWindy && temperature < 50) {
       cout << "Wind chill factor - dress extra warm!" << endl;
   }
   ```

5. **Sample Output**
   ```
   Enter temperature (F): 45
   Enter weather condition (S/R/C/N): R
   Is it windy? (1/0): 1
   
   Weather Advisory:
   Cool weather
   Carry an umbrella
   Storm warning - stay indoors if possible
   ```

---

## Exercise 6: Login Security System (15 points)
**File name:** `exercise6_security.cpp`

### Requirements
Create a simple login system with multiple security checks.

### Detailed Instructions

1. **Predefined Credentials**
   ```cpp
   string correctUsername = "admin";
   string correctPassword = "secure123";
   int maxAttempts = 3;
   ```

2. **Login Process**
   - Allow up to 3 login attempts
   - For each attempt, check both username and password
   - Provide specific feedback about what's wrong
   - Track number of failed attempts

3. **Security Logic**
   ```cpp
   int attempts = 0;
   bool loginSuccessful = false;
   
   while (attempts < maxAttempts && !loginSuccessful) {
       // Get username and password
       // Check credentials
       // Provide feedback
       // Update attempts counter
   }
   ```

4. **Success/Failure Handling**
   - If login successful: "Welcome! Access granted."
   - If username wrong: "Invalid username."
   - If password wrong: "Invalid password."
   - If max attempts reached: "Account locked. Too many failed attempts."

5. **Enhanced Features**
   - Count and display remaining attempts
   - Different messages for different failure combinations

---

## Submission Requirements

### README.txt Content
Create a text file with:
```
Student Name: [Your Full Name]
Course: [Course Name and Section]
Assignment: C++ Conditionals Lab
Date Submitted: [Date]

Files Included:
- exercise1_comparison.cpp: Number comparison tool
- exercise2_logical.cpp: Logical operators practice
- exercise3_grades.cpp: Grade calculator
- exercise4_age.cpp: Age category classifier
- exercise5_weather.cpp: Weather advisory system
- exercise6_security.cpp: Login security system

Compilation Instructions:
Each file can be compiled individually using:
g++ -o [output_name] [filename].cpp

Testing Notes:
[Any special notes about testing your programs]

Known Issues:
[Any problems you couldn't solve or areas needing improvement]
```

---

## Grading Rubric

| Category | Points | Criteria |
|----------|--------|----------|
| **Correctness** | 60 pts | Programs produce correct output for all test cases |
| **Code Quality** | 20 pts | Clean, readable code with good variable names |
| **Input Validation** | 10 pts | Proper handling of invalid input |
| **Output Formatting** | 5 pts | Clear, professional output messages |
| **Documentation** | 5 pts | Complete README file and code comments |

### Per Exercise Breakdown
- Exercise 1: 15 points
- Exercise 2: 15 points  
- Exercise 3: 20 points
- Exercise 4: 15 points
- Exercise 5: 20 points
- Exercise 6: 15 points

---

## Helpful Hints

### Debugging Tips
1. **Test incrementally** - Don't write all the code at once
2. **Use cout statements** to check variable values
3. **Test edge cases** like 0, negative numbers, boundary values
4. **Check operator precedence** with parentheses

### Common Issues to Avoid
1. Using `=` instead of `==` for comparison
2. Forgetting to handle invalid input
3. Not using `else if` when conditions are mutually exclusive
4. Forgetting to include necessary header files

### Getting Help
- Review the tutorial material before starting
- Test each section of code before moving to the next
- Use your textbook and course materials
- Ask questions during office hours if stuck
