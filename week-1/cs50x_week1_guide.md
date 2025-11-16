# CS50x Week 1: Complete Revision Guide - C Programming

## Introduction to Week 1

Week 1 of CS50x marks your transition from visual programming (Scratch) to **C programming** – a powerful, low-level language that gives you direct control over computer memory and operations. This week lays the critical foundation for everything that follows in CS50. You'll learn how computers actually execute your code, how to work with different types of data, how to make decisions and repeat actions, and how to break problems into smaller, manageable functions. Unlike Scratch's drag-and-drop blocks, C requires precise syntax and understanding of how data flows through your program. Mastering Week 1 means you'll be comfortable reading, writing, and debugging basic C programs – skills essential for all future problem sets.

---

## 1. Complete Topic Coverage

### 1.1 The Compilation Process

**What is it?**
- The process of converting human-readable source code into machine code (binary) that computers can execute.

**Key Concepts:**

- **Source Code** → The C code you write (e.g., `hello.c`)
  - Written in text files with `.c` extension
  - Humans can read and understand it
  - Computers cannot execute it directly

- **Machine Code** → Binary instructions (0s and 1s) that the CPU understands
  - Looks like: `01101000 01100101 01101100 01101100 01101111`
  - Only computers can "read" this
  - Specific to the computer's architecture

**Real-Life Analogy:**
Think of source code as a recipe written in English, and machine code as the neural signals your brain sends to your hands. You can read the recipe, but your hands need specific electrical impulses to actually cook. Compilation is like translating that recipe into those precise signals.

**The Compilation Steps:**

1. **Preprocessing** → Handles directives starting with `#` (like `#include`)
2. **Compiling** → Converts C code to assembly language
3. **Assembling** → Converts assembly to machine code (object code)
4. **Linking** → Combines your code with library code (like `printf`) into final executable

**Commands in CS50:**

```c
// Using clang (the actual compiler)
clang hello.c                    // Creates a.out
clang -o hello hello.c           // Creates 'hello' executable
clang -o hello hello.c -lcs50    // Links CS50 library

// Using make (simpler, recommended in CS50)
make hello                       // Automatically compiles hello.c → hello
```

**Key Points:**
- `clang` is the compiler CS50 uses
- `make` is a tool that simplifies the compilation command
- `-o` flag specifies the output filename
- `-lcs50` links the CS50 library for functions like `get_int()`

**Common Mistakes:**
- Forgetting to recompile after changing code
- Trying to run `.c` file directly (`./hello.c` won't work!)
- Not linking CS50 library when using CS50 functions

---

### 1.2 printf and Output Formatting

**What is it?**
- A function to display output to the terminal/console
- Stands for "print formatted"

**Basic Syntax:**

```c
#include <stdio.h>

printf("Hello, world\n");
```

**Format Specifiers:**

| Specifier | Data Type | Example |
|-----------|-----------|---------|
| `%s` | String | `printf("%s", "hello")` |
| `%i` or `%d` | Integer | `printf("%i", 42)` |
| `%f` | Float/Double | `printf("%f", 3.14)` |
| `%c` | Character | `printf("%c", 'A')` |
| `%li` | Long integer | `printf("%li", 1000000L)` |

**Escape Sequences:**

```c
\n   // Newline (moves to next line)
\t   // Tab (horizontal spacing)
\"   // Double quote character
\\   // Backslash character
```

**Examples:**

```c
#include <stdio.h>

int main(void)
{
    // Basic printing
    printf("Hello, world\n");
    
    // Using format specifiers
    int age = 20;
    printf("I am %i years old\n", age);
    
    // Multiple placeholders
    string name = "Alice";
    int score = 95;
    printf("%s scored %i points\n", name, score);
    
    // Floating point with precision
    float pi = 3.14159;
    printf("Pi is %.2f\n", pi);  // Output: Pi is 3.14
    
    // Using escape sequences
    printf("She said, \"Hello!\"\n");
    printf("Line 1\nLine 2\n");
}
```

**Real-Life Analogy:**
Think of `printf` like filling in a Mad Libs story. The format string is your template with blanks (`%i`, `%s`), and you provide the actual words/numbers to fill those blanks.

**Common Mistakes:**
- Forgetting `\n` at the end (output won't move to next line)
- Mismatching format specifier with data type (`%s` for an integer)
- Wrong number of placeholders vs. arguments

---

### 1.3 Variables and Data Types

**What are variables?**
- Named containers that store data in memory
- Must declare type before using

**Why data types matter:**
- Tell computer how much memory to allocate
- Determine what operations are valid
- Affect precision and range of values

**Core Data Types in CS50 Week 1:**

#### `int` - Integer
- Whole numbers (no decimals)
- Range: approximately -2 billion to +2 billion
- Uses 4 bytes (32 bits) of memory

```c
int age = 20;
int temperature = -5;
int students = 150;
```

#### `float` - Floating Point
- Numbers with decimals
- ~6-7 digits of precision
- Uses 4 bytes

```c
float price = 9.99;
float gpa = 3.75;
float temperature = 98.6;
```

#### `double` - Double Precision Float
- More precise decimals
- ~15-16 digits of precision
- Uses 8 bytes

```c
double pi = 3.14159265358979;
double distance = 384400.5;  // Distance to moon in km
```

#### `char` - Character
- Single character
- Enclosed in single quotes
- Uses 1 byte

```c
char grade = 'A';
char initial = 'J';
char symbol = '$';
```

#### `bool` - Boolean
- Only two values: `true` or `false`
- Requires `#include <stdbool.h>` or CS50 library
- Uses 1 byte

```c
bool is_student = true;
bool is_raining = false;
```

#### `string` - String (CS50)
- Sequence of characters
- Defined in CS50 library (`#include <cs50.h>`)
- Enclosed in double quotes

```c
string name = "David";
string message = "Hello, world";
```

**Variable Declaration Syntax:**

```c
// Pattern: type name = value;
int x = 10;
float y = 3.14;
char c = 'A';

// Can declare without initializing
int z;        // Contains garbage value!
z = 20;       // Now it has a value

// Can declare multiple variables of same type
int a = 1, b = 2, c = 3;
```

**Real-Life Analogy:**
Variables are like labeled boxes. The **type** tells you what kind of items the box can hold (shoes, books, liquids), the **name** is the label on the box, and the **value** is what's currently inside.

**Common Mistakes:**
- Using variable before declaring it
- Forgetting semicolon after declaration
- Trying to store wrong type (`int x = "hello";` won't work!)
- Not initializing variables (they contain random garbage values)

---

### 1.4 Arithmetic Operations and Type Casting

**Basic Operators:**

```c
+   // Addition
-   // Subtraction
*   // Multiplication
/   // Division
%   // Modulo (remainder)
```

**Examples:**

```c
int a = 10, b = 3;

int sum = a + b;           // 13
int diff = a - b;          // 7
int product = a * b;       // 30
int quotient = a / b;      // 3 (integer division!)
int remainder = a % b;     // 1 (10 ÷ 3 = 3 remainder 1)

// Shorthand operators
int x = 5;
x = x + 1;    // Same as: x += 1;  or  x++;
x = x - 1;    // Same as: x -= 1;  or  x--;
x = x * 2;    // Same as: x *= 2;
```

**Integer Division Problem:**

```c
int x = 5;
int y = 2;
int result = x / y;        // result = 2 (not 2.5!)

// Why? Both are integers, so result is truncated
```

**Type Casting - The Solution:**

Type casting tells the compiler to temporarily treat a value as a different type.

```c
int x = 5;
int y = 2;

// Cast one operand to float
float result = (float) x / y;     // 2.5 ✓
// or
float result = x / (float) y;     // 2.5 ✓

// Both operands become float through promotion
float result = (float) x / (float) y;  // 2.5 ✓
```

**Real-Life Analogy:**
Integer division is like splitting pizzas among friends. If you have 5 pizzas and 2 people, each gets 2 whole pizzas (remainder of 1 left over). Type casting is like saying "cut those pizzas into slices first, then divide evenly" – now you can get 2.5 pizzas per person.

**Important Rules:**

1. **Integer ÷ Integer = Integer** (fractional part is lost)
2. **Float ÷ Integer = Float** (or vice versa)
3. **Float ÷ Float = Float**

**Practical Example:**

```c
// Calculating average
int score1 = 85, score2 = 90, score3 = 78;
int sum = score1 + score2 + score3;  // 253

// Wrong way
int avg = sum / 3;                   // 84 (should be 84.33...)

// Right way
float avg = (float) sum / 3;         // 84.333333
printf("Average: %.2f\n", avg);      // Average: 84.33
```

**Common Mistakes:**
- Forgetting to cast when doing division with integers
- Casting the result instead of operands: `(float) (x / y)` ← Wrong!
- Using `%` with floats (only works with integers)

---

### 1.5 Conditionals (if, else if, else)

**What are conditionals?**
- Allow your program to make decisions
- Execute different code based on conditions

**Basic Syntax:**

```c
if (condition)
{
    // Code runs if condition is true
}
```

**Comparison Operators:**

```c
==    // Equal to
!=    // Not equal to
>     // Greater than
<     // Less than
>=    // Greater than or equal to
<=    // Less than or equal to
```

**Logical Operators:**

```c
&&    // AND (both conditions must be true)
||    // OR (at least one condition must be true)
!     // NOT (negates/inverts condition)
```

**Full Conditional Structure:**

```c
#include <stdio.h>
#include <cs50.h>

int main(void)
{
    int score = get_int("Enter your score: ");
    
    if (score >= 90)
    {
        printf("Grade: A\n");
    }
    else if (score >= 80)
    {
        printf("Grade: B\n");
    }
    else if (score >= 70)
    {
        printf("Grade: C\n");
    }
    else if (score >= 60)
    {
        printf("Grade: D\n");
    }
    else
    {
        printf("Grade: F\n");
    }
}
```

**Multiple Conditions:**

```c
// AND example (both must be true)
int age = 20;
bool has_license = true;

if (age >= 18 && has_license)
{
    printf("You can drive!\n");
}

// OR example (at least one must be true)
char grade = 'A';

if (grade == 'A' || grade == 'B')
{
    printf("Great job!\n");
}

// NOT example (inverts condition)
bool is_raining = false;

if (!is_raining)
{
    printf("Let's go outside!\n");
}
```

**Nested Conditionals:**

```c
int age = get_int("Age: ");
bool has_ticket = get_string("Have ticket? (yes/no): ")[0] == 'y';

if (age >= 18)
{
    if (has_ticket)
    {
        printf("Welcome to the concert!\n");
    }
    else
    {
        printf("You need a ticket!\n");
    }
}
else
{
    printf("Sorry, adults only.\n");
}
```

**Real-Life Analogy:**
Conditionals are like a flowchart or decision tree. Think of a bouncer at a club: "IF you're over 21 AND have an ID, you can enter. ELSE IF you're with a member, you can enter. ELSE, you can't enter."

**Common Mistakes:**
- Using `=` instead of `==` for comparison (`if (x = 5)` assigns, doesn't compare!)
- Forgetting curly braces for multi-line blocks
- Wrong logic with AND/OR: `if (x == 1 || 2)` doesn't work (use `x == 1 || x == 2`)
- Comparing strings with `==` (use `strcmp()` instead)

---

### 1.6 Loops (for, while, do-while)

**What are loops?**
- Allow you to repeat code multiple times
- Avoid writing the same code over and over

---

#### While Loop

**Structure:**
```c
while (condition)
{
    // Code repeats as long as condition is true
}
```

**Example:**

```c
// Print numbers 1 to 5
int i = 1;
while (i <= 5)
{
    printf("%i\n", i);
    i++;
}
// Output: 1 2 3 4 5
```

**Real-Life Analogy:**
"While you're still hungry, keep eating." The loop continues as long as the condition (hungry) is true.

---

#### Do-While Loop

**Structure:**
```c
do
{
    // Code runs at least once, then checks condition
}
while (condition);
```

**Example:**

```c
// Keep asking until valid input
int n;
do
{
    n = get_int("Enter positive number: ");
}
while (n <= 0);
```

**Key Difference from While:**
- `while`: checks condition first (might never run)
- `do-while`: runs code first, then checks (runs at least once)

---

#### For Loop

**Structure:**
```c
for (initialization; condition; update)
{
    // Code repeats while condition is true
}
```

**Breakdown:**
1. **Initialization**: `int i = 0` (runs once at start)
2. **Condition**: `i < 10` (checked before each iteration)
3. **Update**: `i++` (runs after each iteration)

**Example:**

```c
// Print numbers 0 to 4
for (int i = 0; i < 5; i++)
{
    printf("%i\n", i);
}
```

**Common Patterns:**

```c
// Counting up
for (int i = 0; i < 10; i++)
{
    printf("%i ", i);  // 0 1 2 3 4 5 6 7 8 9
}

// Counting down
for (int i = 10; i > 0; i--)
{
    printf("%i ", i);  // 10 9 8 7 6 5 4 3 2 1
}

// Step by 2
for (int i = 0; i < 10; i += 2)
{
    printf("%i ", i);  // 0 2 4 6 8
}

// Nested loops (for grid/table)
for (int i = 0; i < 3; i++)
{
    for (int j = 0; j < 3; j++)
    {
        printf("(%i,%i) ", i, j);
    }
    printf("\n");
}
// Output:
// (0,0) (0,1) (0,2)
// (1,0) (1,1) (1,2)
// (2,0) (2,1) (2,2)
```

**CS50 Style Examples:**

```c
// Mario pyramid (half)
int height = 4;
for (int i = 0; i < height; i++)
{
    // Print spaces
    for (int j = 0; j < height - i - 1; j++)
    {
        printf(" ");
    }
    // Print hashes
    for (int j = 0; j < i + 1; j++)
    {
        printf("#");
    }
    printf("\n");
}
// Output:
//    #
//   ##
//  ###
// ####
```

**Real-Life Analogy:**
A `for` loop is like following a recipe: "For each of the 12 cupcakes, add frosting." You know exactly how many times you'll repeat the action.

**Which Loop to Use?**
- **for**: When you know how many iterations you need
- **while**: When you don't know how many times (e.g., until user enters valid input)
- **do-while**: When you need to run code at least once before checking condition

**Common Mistakes:**
- Off-by-one errors: `for (int i = 0; i <= 5; i++)` runs 6 times, not 5!
- Infinite loops: forgetting to update loop variable
- Using `i` outside loop scope in C (it only exists inside the loop)
- Confusing `i++` (after) vs `++i` (before) – usually doesn't matter in for loops

---

### 1.7 Functions

**What are functions?**
- Reusable blocks of code that perform specific tasks
- Help organize code and avoid repetition
- Can take inputs (parameters) and return outputs

**Why use functions?**
- **Abstraction**: Hide complex details
- **Reusability**: Write once, use many times
- **Organization**: Break large problems into smaller pieces
- **Debugging**: Easier to test and fix isolated pieces

**Basic Function Anatomy:**

```c
return_type function_name(parameter_type parameter_name)
{
    // Code to execute
    return value;  // Must match return_type
}
```

**Function Declaration vs Definition:**

```c
#include <stdio.h>

// DECLARATION (prototype) - tells compiler function exists
int add(int a, int b);

int main(void)
{
    int result = add(5, 3);
    printf("Result: %i\n", result);  // 8
}

// DEFINITION (implementation) - actual code
int add(int a, int b)
{
    return a + b;
}
```

**Why declare before main?**
- C reads code top-to-bottom
- If you call a function before defining it, compiler doesn't know it exists
- Declaration (prototype) at top tells compiler "trust me, this function exists"

**Examples:**

```c
// Function with no parameters, no return value
void greet(void)
{
    printf("Hello, world!\n");
}

// Function with parameters, returns value
int square(int n)
{
    return n * n;
}

// Function with multiple parameters
int max(int a, int b)
{
    if (a > b)
    {
        return a;
    }
    else
    {
        return b;
    }
}

// Using the functions
int main(void)
{
    greet();                    // Hello, world!
    
    int x = square(5);          // x = 25
    printf("%i\n", x);
    
    int larger = max(10, 7);    // larger = 10
    printf("%i\n", larger);
}
```

**Return Types:**

```c
void    // Returns nothing
int     // Returns integer
float   // Returns floating point
bool    // Returns true/false
char    // Returns character
string  // Returns string (CS50)
```

**Void Functions:**

```c
// Prints but doesn't return anything
void print_triangle(int height)
{
    for (int i = 0; i < height; i++)
    {
        for (int j = 0; j <= i; j++)
        {
            printf("#");
        }
        printf("\n");
    }
    // No return statement needed
}
```

**Practical Example - CS50 Style:**

```c
#include <cs50.h>
#include <stdio.h>

// Function prototypes
bool is_valid_height(int n);
void print_row(int spaces, int hashes);
void print_pyramid(int height);

int main(void)
{
    int height;
    do
    {
        height = get_int("Height: ");
    }
    while (!is_valid_height(height));
    
    print_pyramid(height);
}

// Check if height is valid (1-8)
bool is_valid_height(int n)
{
    return n >= 1 && n <= 8;
}

// Print one row of pyramid
void print_row(int spaces, int hashes)
{
    for (int i = 0; i < spaces; i++)
    {
        printf(" ");
    }
    for (int i = 0; i < hashes; i++)
    {
        printf("#");
    }
    printf("\n");
}

// Print entire pyramid
void print_pyramid(int height)
{
    for (int i = 0; i < height; i++)
    {
        print_row(height - i - 1, i + 1);
    }
}
```

**Real-Life Analogy:**
Functions are like appliances. A microwave (function) takes input (food + time), processes it internally (you don't need to know how), and gives you output (heated food). You can use it many times without understanding the complex electronics inside.

**Common Mistakes:**
- Forgetting to declare function before `main()`
- Mismatching return type (function says `int` but returns `float`)
- Forgetting `return` statement in non-void function
- Trying to use variables from inside function outside it (scope issue)
- Wrong number or type of arguments when calling function

---

### 1.8 Arrays and Strings

#### Arrays

**What is an array?**
- Collection of values of the **same type**
- Stored in contiguous memory locations
- Access elements using index (starting at 0)

**Declaration and Initialization:**

```c
// Declare array with size
int numbers[5];

// Declare and initialize
int scores[3] = {85, 90, 78};

// Compiler infers size from values
int ages[] = {18, 21, 19, 22};  // Size is 4

// Individual assignment
numbers[0] = 10;
numbers[1] = 20;
numbers[2] = 30;
numbers[3] = 40;
numbers[4] = 50;
```

**Accessing Array Elements:**

```c
int scores[3] = {85, 90, 78};

printf("%i\n", scores[0]);  // 85
printf("%i\n", scores[1]);  // 90
printf("%i\n", scores[2]);  // 78

// Modify element
scores[1] = 95;
printf("%i\n", scores[1]);  // 95
```

**Array Index Visualization:**

```
scores array:
Index:   [0]  [1]  [2]
Value:    85   90   78
```

**Looping Through Arrays:**

```c
int numbers[5] = {10, 20, 30, 40, 50};

// Using for loop (most common)
for (int i = 0; i < 5; i++)
{
    printf("%i ", numbers[i]);
}
// Output: 10 20 30 40 50

// Calculate average
int sum = 0;
for (int i = 0; i < 5; i++)
{
    sum += numbers[i];
}
float average = (float) sum / 5;
```

**Important Array Rules:**
1. **Arrays have fixed size** (can't grow/shrink)
2. **Indices start at 0** (first element is `array[0]`)
3. **No bounds checking** in C! Accessing `array[10]` when size is 5 = undefined behavior
4. **Arrays are passed by reference** to functions (changes inside function affect original)

---

#### Strings

**What is a string?**
- Array of characters
- Ends with special `\0` (null terminator) character
- In CS50, use `string` type (defined in cs50.h)

**Behind the Scenes:**

```c
string name = "Hi!";

// Actually stored as:
// ['H']['i']['!']['\0']
//   0    1    2    3
```

**String Declaration:**

```c
#include <cs50.h>

// Using CS50's string type
string name = "Alice";
string message = "Hello, world";

// Or using char array (traditional C)
char name[] = "Alice";
char message[50] = "Hello";  // Can hold up to 49 chars + '\0'
```

**Accessing Characters in String:**

```c
string word = "Hello";

printf("%c\n", word[0]);  // H
printf("%c\n", word[1]);  // e
printf("%c\n", word[2]);  // l
printf("%c\n", word[3]);  // l
printf("%c\n", word[4]);  // o

// Loop through string
for (int i = 0; word[i] != '\0'; i++)
{
    printf("%c", word[i]);
}
```

**String Length:**

```c
#include <string.h>

string name = "David";
int length = strlen(name);  // 5
```

**Common String Operations:**

```c
#include <string.h>
#include <ctype.h>

// Length
int len = strlen("Hello");  // 5

// Compare strings (returns 0 if equal)
if (strcmp("hello", "hello") == 0)
{
    printf("Strings are equal\n");
}

// Convert character to uppercase
char c = 'a';
char upper = toupper(c);  // 'A'

// Convert character to lowercase
char c = 'A';
char lower = tolower(c);  // 'a'
```

**Example - Convert String to Uppercase:**

```c
#include <cs50.h>
#include <stdio.h>
#include <string.h>
#include <ctype.h>

int main(void)
{
    string text = get_string("Before: ");
    printf("After:  ");
    
    for (int i = 0, n = strlen(text); i < n; i++)
    {
        printf("%c", toupper(text[i]));
    }
    printf("\n");
}

// Input: hello
// Output: HELLO
```

**The Null Terminator (`\0`):**

```c
// Why it matters:
char name[6] = "Alice";  // Actually stored: ['A']['l']['i']['c']['e']['\0']

// Functions like strlen() and printf() use \0 to know where string ends
```

**Real-Life Analogy:**
An array is like a row of lockers, numbered 0, 1, 2, etc. Each locker holds one item of the same type. A string is a row of lockers specifically for letters, with a special "END" sign at the last locker so you know where the word stops.

**Common Mistakes:**
- Accessing index out of bounds (e.g., `array[5]` when size is 5)
- Forgetting arrays start at 0 (last element is `size - 1`, not `size`)
- Comparing strings with `==` (use `strcmp()` instead)
- Forgetting to `#include <string.h>` for string functions
- Not leaving room for `\0` in char arrays (`char word[5] = "Hello"` needs 6 spaces!)

---

### 1.9 User Input Methods

#### CS50 Library Functions

**Why use CS50 functions?**
- Simpler and safer than standard C input
- Handle errors and validation automatically
- Perfect for beginners

**Available Functions:**

```c
#include <cs50.h>

int get_int("Prompt: ");       // Get integer
float get_float("Prompt: ");   // Get float
double get_double("Prompt: "); // Get double
char get_char("Prompt: ");     // Get single character
string get_string("Prompt: "); // Get string
long get_long("Prompt: ");     // Get long integer
```

**Examples:**

```c
#include <cs50.h>
#include <stdio.h>

int main(void)
{
    // Get integer
    int age = get_int("Enter your age: ");
    printf("You are %i years old\n", age);
    
    // Get string
    string name = get_string("Enter your name: ");
    printf("Hello, %s!\n", name);
    
    // Get float
    float price = get_float("Enter price: ");
    printf("Price: $%.2f\n", price);
    
    // Get character
    char grade = get_char("Enter grade: ");
    printf("You got a %c\n", grade);
}
```

**Input Validation with CS50:**

```c
// get_int automatically rejects invalid input
int n = get_int("Enter positive number: ");
// If user types "hello" or "abc", it will re-prompt

// For custom validation, use a loop
int height;
do
{
    height = get_int("Height: ");
}
while (height < 1 || height > 8);
```

---

#### scanf (Standard C Input)

**What is scanf?**
- Standard C function for reading input
- More complex but more flexible than CS50 functions
- Requires `#include <stdio.h>`

**Basic Syntax:**

```c
scanf("format_specifier", &variable);
```

**The `&` Operator:**
- Means "address of"
- scanf needs the memory address to store input
- **NOT needed for strings!** (strings are already addresses)

**Examples:**

```c
#include <stdio.h>

int main(void)
{
    // Read integer
    int age;
    printf("Enter age: ");
    scanf("%i", &age);  // Note the &
    
    // Read float
    float price;
    printf("Enter price: ");
    scanf("%f", &price);
    
    // Read character
    char grade;
    printf("Enter grade: ");
    scanf(" %c", &grade);  // Space before %c to skip whitespace
    
    // Read string (be careful with size!)
    char name[50];
    printf("Enter name: ");
    scanf("%49s", name);  // No & for string! Also limit to 49 chars
}
```

**scanf Issues and Solutions:**

```c
// Problem: scanf leaves newline in buffer
int age;
char grade;
scanf("%i", &age);
scanf("%c", &grade);  // Will read the newline, not the character!

// Solution 1: Add space before %c
scanf(" %c", &grade);  // Space consumes leftover whitespace

// Solution 2: Clear input buffer
int c;
while ((c = getchar()) != '\n' && c != EOF);
```

**Why CS50 Functions Are Recommended:**

| Aspect | CS50 Functions | scanf |
|--------|----------------|-------|
| Error handling | Automatic | Manual |
| Buffer issues | None | Common |
| Ease of use | Very easy | Tricky |
| Beginner-friendly | Yes | No |

**Real-Life Analogy:**
CS50's `get_int()` is like ordering from a menu with clear options – you can't order something invalid. `scanf()` is like a blank order form where you can write anything, including gibberish, and it's your job to validate it.

**Common Mistakes:**
- Forgetting `&` operator for non-string types
- Not limiting string size in scanf (buffer overflow risk!)
- Not handling scanf return value (tells you if input was successful)
- Leaving newlines in buffer causing unexpected behavior

---

### 1.10 Command-Line Arguments

**What are command-line arguments?**
- Values passed to your program when you run it from terminal
- Allow programs to accept input without prompting
- Used in many CS50 problem sets

**Basic Syntax:**

```c
int main(int argc, string argv[])
{
    // argc = argument count
    // argv = argument vector (array of strings)
}
```

**Understanding argc and argv:**

```bash
# Running program:
./program hello world 123

# Inside program:
# argc = 4
# argv[0] = "./program"
# argv[1] = "hello"
# argv[2] = "world"
# argv[3] = "123"
```

**Key Points:**
- `argc` = number of arguments (including program name)
- `argv[0]` = always the program name
- `argv[1]` onwards = actual arguments passed by user
- All arguments are strings (even numbers!)

**Example 1 - Greeting Program:**

```c
#include <cs50.h>
#include <stdio.h>

int main(int argc, string argv[])
{
    // Check if user provided name
    if (argc == 2)
    {
        printf("Hello, %s\n", argv[1]);
    }
    else
    {
        printf("Usage: ./greet name\n");
    }
}

// Run: ./greet Alice
// Output: Hello, Alice

// Run: ./greet
// Output: Usage: ./greet name
```

**Example 2 - Adding Numbers:**

```c
#include <cs50.h>
#include <stdio.h>
#include <stdlib.h>  // For atoi()

int main(int argc, string argv[])
{
    if (argc != 3)
    {
        printf("Usage: ./add number1 number2\n");
        return 1;  // Exit with error code
    }
    
    // Convert strings to integers
    int num1 = atoi(argv[1]);
    int num2 = atoi(argv[2]);
    
    int sum = num1 + num2;
    printf("%i + %i = %i\n", num1, num2, sum);
    
    return 0;  // Exit successfully
}

// Run: ./add 5 7
// Output: 5 + 7 = 12
```

**Converting String Arguments:**

```c
#include <stdlib.h>

// String to integer
int n = atoi("42");        // 42

// String to long
long l = atol("123456");   // 123456

// String to float
float f = atof("3.14");    // 3.14
```

**Checking Argument Count:**

```c
int main(int argc, string argv[])
{
    // Expect exactly 1 argument (plus program name = 2 total)
    if (argc != 2)
    {
        printf("Error: Expected 1 argument\n");
        return 1;
    }
    
    // Expect at least 1 argument
    if (argc < 2)
    {
        printf("Error: Please provide at least one argument\n");
        return 1;
    }
    
    // Process arguments
    // ...
}
```

**Example 3 - Caesar Cipher (CS50 Style):**

```c
#include <cs50.h>
#include <stdio.h>
#include <stdlib.h>
#include <ctype.h>
#include <string.h>

int main(int argc, string argv[])
{
    // Check for exactly one command-line argument
    if (argc != 2)
    {
        printf("Usage: ./caesar key\n");
        return 1;
    }
    
    // Convert key to integer
    int key = atoi(argv[1]);
    
    // Get plaintext
    string plaintext = get_string("plaintext: ");
    printf("ciphertext: ");
    
    // Encrypt
    for (int i = 0, n = strlen(plaintext); i < n; i++)
    {
        char c = plaintext[i];
        if (isalpha(c))
        {
            // Shift character
            if (isupper(c))
            {
                printf("%c", (c - 'A' + key) % 26 + 'A');
            }
            else
            {
                printf("%c", (c - 'a' + key) % 26 + 'a');
            }
        }
        else
        {
            printf("%c", c);
        }
    }
    printf("\n");
    
    return 0;
}

// Run: ./caesar 13
// Input: HELLO
// Output: URYYB
```

**Real-Life Analogy:**
Command-line arguments are like setting the temperature on your microwave before hitting start. Instead of the microwave asking "What temperature?" while running, you tell it upfront: `./microwave 350 degrees 5 minutes`.

**Common Mistakes:**
- Forgetting `argc` and `argv` in main when you need them
- Accessing `argv[1]` without checking if `argc > 1`
- Treating `argv` numbers as integers (they're strings – must convert!)
- Returning 0 vs 1 (0 = success, non-zero = error)

---

### 1.11 Basic Debugging and Problem-Solving

**CS50's Problem-Solving Approach:**

1. **Understand the problem** - Read carefully, identify inputs/outputs
2. **Pseudocode** - Write solution in plain English first
3. **Implement** - Translate pseudocode to C
4. **Test** - Try different inputs, including edge cases
5. **Debug** - Find and fix errors

---

#### Debugging Techniques

**1. printf Debugging (Most Common):**

```c
// Track variable values
int x = 10;
printf("DEBUG: x = %i\n", x);

// Track program flow
printf("DEBUG: Reached line 25\n");

// Track loop iterations
for (int i = 0; i < 5; i++)
{
    printf("DEBUG: i = %i\n", i);
}
```

**2. Rubber Duck Debugging:**
- Explain your code line-by-line to an imaginary listener (or rubber duck!)
- Forces you to think through logic slowly
- Often reveals the bug just by explaining

**3. Comment Out Code:**

```c
// Comment sections to isolate problem
// calculate_average();  // Disabled temporarily
print_results();
```

**4. Simplify:**
- Start with smallest working version
- Add complexity gradually
- Test after each addition

---

#### Common Errors and Solutions

**Compilation Errors:**

```c
// Missing semicolon
int x = 5  // Error!
int x = 5;  // Fixed

// Undeclared variable
printf("%i", y);  // Error: y not declared
int y = 10;
printf("%i", y);  // Fixed

// Missing return type
add(int a, int b)  // Error!
int add(int a, int b)  // Fixed

// Mismatched types
int x = "hello";  // Error!
string x = "hello";  // Fixed
```

**Runtime Errors:**

```c
// Division by zero
int result = 10 / 0;  // Crash!

// Array out of bounds
int arr[5];
arr[10] = 5;  // Undefined behavior!

// Infinite loop
while (true)
{
    // Never exits!
}

// Using uninitialized variable
int x;
printf("%i", x);  // Garbage value!
```

**Logic Errors:**

```c
// Off-by-one error
for (int i = 0; i <= 5; i++)  // Runs 6 times!
{
    // Should be: i < 5
}

// Wrong operator
if (x = 5)  // Assignment, not comparison!
{
    // Should be: x == 5
}

// Integer division
float avg = 5 / 2;  // avg = 2.0, not 2.5!
// Should be: (float) 5 / 2
```

---

#### Testing Strategies

**1. Test Edge Cases:**

```c
// Test boundaries
test_with(0);      // Minimum
test_with(1);      // Just above minimum
test_with(100);    // Maximum
test_with(99);     // Just below maximum
test_with(-1);     // Below minimum
test_with(101);    // Above maximum
```

**2. Test With Different Data Types:**

```c
// If expecting integer, test:
// - Positive numbers
// - Negative numbers
// - Zero
// - Very large numbers
```

**3. Check50 (CS50 Tool):**

```bash
# Automated testing for CS50 problem sets
check50 cs50/problems/2024/x/mario/less
```

**4. Style50 (CS50 Tool):**

```bash
# Check code style
style50 mario.c
```

---

#### CS50 Debugging Tips

1. **Read error messages carefully** - They tell you exactly what's wrong
2. **Check line numbers** - Error might be on line before indicated line
3. **Use help50** (CS50 tool):
   ```bash
   help50 make mario
   ```
4. **Incremental development** - Write a little, test a little
5. **Compare to examples** - Look at lecture code for patterns
6. **Ask for help** - Use CS50's communities and resources

**Real-Life Analogy:**
Debugging is like being a detective. You gather clues (printf statements), form hypotheses (what might be wrong), test theories (try fixes), and eventually solve the case (find the bug).

---

## 2. Key Example Programs from Week 1

### Example 1: Hello, World

```c
#include <stdio.h>

int main(void)
{
    printf("Hello, world\n");
}
```

**Explanation:**
- `#include <stdio.h>` - Imports standard input/output library
- `int main(void)` - Program entry point, returns integer
- `printf()` - Prints text to console
- `\n` - Newline character
- Compilation: `make hello` or `clang -o hello hello.c`
- Run: `./hello`

---

### Example 2: User Input and Conditionals

```c
#include <cs50.h>
#include <stdio.h>

int main(void)
{
    int age = get_int("What is your age? ");
    
    if (age >= 18)
    {
        printf("You are an adult.\n");
    }
    else
    {
        printf("You are a minor.\n");
    }
}
```

**How it works:**
1. Program prompts user for age
2. Stores input in `age` variable
3. Checks if age >= 18
4. Prints appropriate message based on condition
5. Input: `20` → Output: `You are an adult.`

---

### Example 3: Loops - Mario Pyramid

```c
#include <cs50.h>
#include <stdio.h>

int main(void)
{
    int height;
    do
    {
        height = get_int("Height: ");
    }
    while (height < 1 || height > 8);
    
    for (int i = 0; i < height; i++)
    {
        // Print spaces
        for (int j = 0; j < height - i - 1; j++)
        {
            printf(" ");
        }
        
        // Print hashes
        for (int j = 0; j <= i; j++)
        {
            printf("#");
        }
        
        printf("\n");
    }
}
```

**How it works:**
1. Gets valid height (1-8) using do-while loop
2. For each row (i):
   - Prints (height - i - 1) spaces for right alignment
   - Prints (i + 1) hashes
3. Input: `4` → Output:
```
   #
  ##
 ###
####
```

---

### Example 4: Arrays and Average Calculator

```c
#include <cs50.h>
#include <stdio.h>

const int N = 3;  // Constant for array size

int main(void)
{
    int scores[N];
    
    // Get scores
    for (int i = 0; i < N; i++)
    {
        scores[i] = get_int("Score: ");
    }
    
    // Calculate average
    int sum = 0;
    for (int i = 0; i < N; i++)
    {
        sum += scores[i];
    }
    
    float average = (float) sum / N;
    printf("Average: %.2f\n", average);
}
```

**How it works:**
1. Declares array of 3 integers
2. Loop gets input for each score
3. Second loop sums all scores
4. Calculates average using type casting
5. Input: `85, 90, 78` → Output: `Average: 84.33`

---

### Example 5: String Manipulation

```c
#include <cs50.h>
#include <stdio.h>
#include <string.h>
#include <ctype.h>

int main(void)
{
    string text = get_string("Before: ");
    printf("After:  ");
    
    for (int i = 0, n = strlen(text); i < n; i++)
    {
        if (islower(text[i]))
        {
            printf("%c", toupper(text[i]));
        }
        else
        {
            printf("%c", text[i]);
        }
    }
    printf("\n");
}
```

**How it works:**
1. Gets string from user
2. Loops through each character
3. Converts lowercase letters to uppercase
4. Keeps other characters unchanged
5. Input: `hello!` → Output: `HELLO!`

---

### Example 6: Functions - Modular Design

```c
#include <cs50.h>
#include <stdio.h>

// Function prototypes
int get_positive_int(void);
void print_stars(int n);

int main(void)
{
    int count = get_positive_int();
    print_stars(count);
}

int get_positive_int(void)
{
    int n;
    do
    {
        n = get_int("Positive integer: ");
    }
    while (n < 1);
    return n;
}

void print_stars(int n)
{
    for (int i = 0; i < n; i++)
    {
        printf("*");
    }
    printf("\n");
}
```

**How it works:**
1. `main()` calls `get_positive_int()` to validate input
2. Returns valid positive integer
3. `main()` calls `print_stars()` with that number
4. Prints that many stars
5. Input: `5` → Output: `*****`

---

### Example 7: Command-Line Arguments

```c
#include <cs50.h>
#include <stdio.h>

int main(int argc, string argv[])
{
    if (argc != 2)
    {
        printf("Usage: ./greet name\n");
        return 1;
    }
    
    printf("Hello, %s\n", argv[1]);
    return 0;
}
```

**How it works:**
1. Checks if exactly one argument provided (plus program name = 2 total)
2. If not, prints usage message and exits with error code
3. Otherwise, greets user by name from argument
4. Run: `./greet Alice` → Output: `Hello, Alice`

---

## 3. Practice Problems (10 Questions)

### Problem 1: Temperature Converter
**Difficulty:** Easy

Write a program that converts Celsius to Fahrenheit.
- Prompt user for temperature in Celsius
- Formula: F = (C × 9/5) + 32
- Print result with 1 decimal place

**Hints:**
- Use `get_float()` for input
- Remember type casting for division
- Use `%.1f` to print with 1 decimal

**Solution:**
```c
#include <cs50.h>
#include <stdio.h>

int main(void)
{
    float celsius = get_float("Celsius: ");
    float fahrenheit = (celsius * 9.0 / 5.0) + 32;
    printf("Fahrenheit: %.1f\n", fahrenheit);
}
```

---

### Problem 2: Even or Odd Checker
**Difficulty:** Easy

Write a program that determines if a number is even or odd.
- Prompt user for integer
- Print "Even" or "Odd"

**Hints:**
- Use modulo operator `%`
- If `n % 2 == 0`, number is even

**Solution:**
```c
#include <cs50.h>
#include <stdio.h>

int main(void)
{
    int n = get_int("Enter a number: ");
    
    if (n % 2 == 0)
    {
        printf("Even\n");
    }
    else
    {
        printf("Odd\n");
    }
}
```

---

### Problem 3: Sum of Numbers 1 to N
**Difficulty:** Easy

Write a program that calculates the sum of all numbers from 1 to N.
- Prompt user for positive integer N
- Calculate sum: 1 + 2 + 3 + ... + N
- Print the result

**Hints:**
- Use a for loop
- Initialize sum to 0
- Add each number to sum

**Solution:**
```c
#include <cs50.h>
#include <stdio.h>

int main(void)
{
    int n;
    do
    {
        n = get_int("N: ");
    }
    while (n < 1);
    
    int sum = 0;
    for (int i = 1; i <= n; i++)
    {
        sum += i;
    }
    
    printf("Sum: %i\n", sum);
}
```

---

### Problem 4: Vowel Counter
**Difficulty:** Easy-Medium

Write a program that counts vowels in a string.
- Prompt user for text
- Count a, e, i, o, u (both uppercase and lowercase)
- Print total count

**Hints:**
- Loop through string with `strlen()`
- Use `tolower()` to handle both cases
- Check if character equals 'a', 'e', 'i', 'o', or 'u'

**Solution:**
```c
#include <cs50.h>
#include <stdio.h>
#include <string.h>
#include <ctype.h>

int main(void)
{
    string text = get_string("Text: ");
    int count = 0;
    
    for (int i = 0, n = strlen(text); i < n; i++)
    {
        char c = tolower(text[i]);
        if (c == 'a' || c == 'e' || c == 'i' || c == 'o' || c == 'u')
        {
            count++;
        }
    }
    
    printf("Vowels: %i\n", count);
}
```

---

### Problem 5: Multiplication Table
**Difficulty:** Medium

Write a program that prints a multiplication table for a given number.
- Prompt user for number
- Print table from 1 to 10
- Format: `n x 1 = result`

**Hints:**
- Use for loop from 1 to 10
- Multiply number by loop variable

**Solution:**
```c
#include <cs50.h>
#include <stdio.h>

int main(void)
{
    int n = get_int("Number: ");
    
    for (int i = 1; i <= 10; i++)
    {
        printf("%i x %i = %i\n", n, i, n * i);
    }
}
```

---

### Problem 6: Password Validator
**Difficulty:** Medium

Write a program that validates a password.
- Password must be at least 8 characters
- Must contain at least one digit
- Print "Valid" or "Invalid"

**Hints:**
- Use `strlen()` for length check
- Use `isdigit()` to check for numbers
- Need flag variable for digit check

**Solution:**
```c
#include <cs50.h>
#include <stdio.h>
#include <string.h>
#include <ctype.h>

int main(void)
{
    string password = get_string("Password: ");
    
    // Check length
    if (strlen(password) < 8)
    {
        printf("Invalid\n");
        return 0;
    }
    
    // Check for digit
    bool has_digit = false;
    for (int i = 0, n = strlen(password); i < n; i++)
    {
        if (isdigit(password[i]))
        {
            has_digit = true;
            break;
        }
    }
    
    if (has_digit)
    {
        printf("Valid\n");
    }
    else
    {
        printf("Invalid\n");
    }
}
```

---

### Problem 7: Reverse Array
**Difficulty:** Medium

Write a program that reverses an array.
- Create array of 5 integers
- Get input for each element
- Print array in reverse order

**Hints:**
- Loop from last index to first
- Last index is size - 1

**Solution:**
```c
#include <cs50.h>
#include <stdio.h>

int main(void)
{
    int arr[5];
    
    // Get input
    for (int i = 0; i < 5; i++)
    {
        arr[i] = get_int("Number %i: ", i + 1);
    }
    
    // Print in reverse
    printf("Reversed: ");
    for (int i = 4; i >= 0; i--)
    {
        printf("%i ", arr[i]);
    }
    printf("\n");
}
```

---

### Problem 8: Factorial Calculator
**Difficulty:** Medium

Write a program using a function to calculate factorial.
- Create function `int factorial(int n)`
- Factorial of n = n × (n-1) × (n-2) × ... × 1
- Factorial of 0 = 1

**Hints:**
- Use loop to multiply numbers
- Start with result = 1

**Solution:**
```c
#include <cs50.h>
#include <stdio.h>

int factorial(int n);

int main(void)
{
    int n = get_int("Number: ");
    printf("Factorial: %i\n", factorial(n));
}

int factorial(int n)
{
    int result = 1;
    for (int i = 1; i <= n; i++)
    {
        result *= i;
    }
    return result;
}
```

---

### Problem 9: Find Maximum in Array
**Difficulty:** Medium

Write a function that finds the maximum value in an array.
- Create function `int find_max(int arr[], int size)`
- Test with sample array

**Hints:**
- Assume first element is max
- Compare each element with current max
- Update if larger found

**Solution:**
```c
#include <cs50.h>
#include <stdio.h>

int find_max(int arr[], int size);

int main(void)
{
    int numbers[] = {23, 45, 12, 67, 34};
    int max = find_max(numbers, 5);
    printf("Maximum: %i\n", max);
}

int find_max(int arr[], int size)
{
    int max = arr[0];
    for (int i = 1; i < size; i++)
    {
        if (arr[i] > max)
        {
            max = arr[i];
        }
    }
    return max;
}
```

---

### Problem 10: Command-Line Calculator
**Difficulty:** Medium-Hard

Write a calculator that takes two numbers and operation from command line.
- Usage: `./calc num1 operator num2`
- Support +, -, *, /
- Print result

**Hints:**
- Check `argc == 4`
- Use `atoi()` to convert numbers
- Use `strcmp()` or character check for operator

**Solution:**
```c
#include <cs50.h>
#include <stdio.h>
#include <stdlib.h>
#include <string.h>

int main(int argc, string argv[])
{
    if (argc != 4)
    {
        printf("Usage: ./calc num1 operator num2\n");
        return 1;
    }
    
    int num1 = atoi(argv[1]);
    string op = argv[2];
    int num2 = atoi(argv[3]);
    
    if (strcmp(op, "+") == 0)
    {
        printf("%i\n", num1 + num2);
    }
    else if (strcmp(op, "-") == 0)
    {
        printf("%i\n", num1 - num2);
    }
    else if (strcmp(op, "*") == 0)
    {
        printf("%i\n", num1 * num2);
    }
    else if (strcmp(op, "/") == 0)
    {
        if (num2 != 0)
        {
            printf("%.2f\n", (float) num1 / num2);
        }
        else
        {
            printf("Error: Division by zero\n");
            return 1;
        }
    }
    else
    {
        printf("Error: Invalid operator\n");
        return 1;
    }
    
    return 0;
}
```

---

## 4. Mini-Project: Grade Book System

### Project Goal
Create a simple grade book that stores student scores and calculates statistics.

### Features
1. Store grades for 5 students
2. Calculate and display:
   - Average grade
   - Highest grade
   - Lowest grade
3. Display letter grade for each student
4. Use functions for modular design

### Input/Output Example
```
Enter 5 student scores:
Student 1: 85
Student 2: 92
Student 3: 78
Student 4: 95
Student 5: 88

=== Grade Book ===
Student 1: 85 (B)
Student 2: 92 (A)
Student 3: 78 (C)
Student 4: 95 (A)
Student 5: 88 (B)

Average: 87.60
Highest: 95
Lowest: 78
```

### Implementation

```c
#include <cs50.h>
#include <stdio.h>

// Function prototypes
void get_grades(int grades[], int count);
float calculate_average(int grades[], int count);
int find_max(int grades[], int count);
int find_min(int grades[], int count);
char get_letter_grade(int score);
void display_report(int grades[], int count);

int main(void)
{
    const int STUDENT_COUNT = 5;
    int grades[STUDENT_COUNT];
    
    printf("Enter %i student scores:\n", STUDENT_COUNT);
    get_grades(grades, STUDENT_COUNT);
    
    display_report(grades, STUDENT_COUNT);
}

// Get grades from user
void get_grades(int grades[], int count)
{
    for (int i = 0; i < count; i++)
    {
        do
        {
            grades[i] = get_int("Student %i: ", i + 1);
        }
        while (grades[i] < 0 || grades[i] > 100);
    }
}

// Calculate average
float calculate_average(int grades[], int count)
{
    int sum = 0;
    for (int i = 0; i < count; i++)
    {
        sum += grades[i];
    }
    return (float) sum / count;
}

// Find highest grade
int find_max(int grades[], int count)
{
    int max = grades[0];
    for (int i = 1; i < count; i++)
    {
        if (grades[i] > max)
        {
            max = grades[i];
        }
    }
    return max;
}

// Find lowest grade
int find_min(int grades[], int count)
{
    int min = grades[0];
    for (int i = 1; i < count; i++)
    {
        if (grades[i] < min)
        {
            min = grades[i];
        }
    }
    return min;
}

// Convert numeric grade to letter
char get_letter_grade(int score)
{
    if (score >= 90)
    {
        return 'A';
    }
    else if (score >= 80)
    {
        return 'B';
    }
    else if (score >= 70)
    {
        return 'C';
    }
    else if (score >= 60)
    {
        return 'D';
    }
    else
    {
        return 'F';
    }
}

// Display complete report
void display_report(int grades[], int count)
{
    printf("\n=== Grade Book ===\n");
    
    // Display each student
    for (int i = 0; i < count; i++)
    {
        printf("Student %i: %i (%c)\n", 
               i + 1, grades[i], get_letter_grade(grades[i]));
    }
    
    // Display statistics
    printf("\nAverage: %.2f\n", calculate_average(grades, count));
    printf("Highest: %i\n", find_max(grades, count));
    printf("Lowest: %i\n", find_min(grades, count));
}
```

### How This Project Uses Week 1 Concepts

1. **Arrays** - Storing multiple grades
2. **Loops** - Iterating through grades
3. **Functions** - Modular design for each task
4. **Conditionals** - Determining letter grades
5. **Type Casting** - Calculating float average from int grades
6. **Input Validation** - Ensuring grades are 0-100

### Extension Ideas
- Add student names (using strings)
- Accept variable number of students (command-line argument)
- Save grades to file (Week 4 concept, but good to think about)
- Calculate median and mode

---

## 5. Quick Revision Sheet

### Essential Syntax Reference

#### Variable Declaration
```c
int age = 20;
float price = 9.99;
char grade = 'A';
bool is_valid = true;
string name = "Alice";
```

#### Printf Format Specifiers
```c
%i, %d   // Integer
%f       // Float/double
%c       // Character
%s       // String
%.2f     // Float with 2 decimal places
```

#### Operators
```c
+  -  *  /  %       // Arithmetic
==  !=  >  <  >=  <=  // Comparison
&&  ||  !           // Logical
```

#### Conditionals
```c
if (condition) { }
else if (condition) { }
else { }
```

#### Loops
```c
// For loop
for (int i = 0; i < n; i++) { }

// While loop
while (condition) { }

// Do-while loop
do { } while (condition);
```

#### Functions
```c
return_type name(parameters)
{
    // code
    return value;
}

// Example
int add(int a, int b)
{
    return a + b;
}
```

#### Arrays
```c
int arr[5];                    // Declaration
int arr[3] = {1, 2, 3};       // Initialization
arr[0] = 10;                   // Access/modify
```

#### Strings
```c
string s = "Hello";
strlen(s);                     // Length
strcmp(s1, s2);               // Compare
toupper(c);                   // To uppercase
tolower(c);                   // To lowercase
isalpha(c);                   // Is letter?
isdigit(c);                   // Is digit?
```

#### Input Functions
```c
#include <cs50.h>

get_int("Prompt: ");
get_float("Prompt: ");
get_string("Prompt: ");
get_char("Prompt: ");
```

#### Command-Line Arguments
```c
int main(int argc, string argv[])
{
    // argc = argument count
    // argv[0] = program name
    // argv[1] = first argument
}
```

#### Common Libraries
```c
#include <stdio.h>     // printf, scanf
#include <cs50.h>      // get_int, get_string, etc.
#include <string.h>    // strlen, strcmp
#include <ctype.h>     // toupper, tolower, isalpha, isdigit
#include <stdbool.h>   // bool, true, false
#include <stdlib.h>    // atoi, atof
```

#### Compilation Commands
```bash
make program          # Compile program.c
./program             # Run compiled program
clang -o name file.c  # Compile with clang
check50 cs50/problems/2024/x/problem_name  # Test your code
style50 program.c     # Check code style
help50 make program   # Get help with errors
```

#### Type Casting
```c
float result = (float) x / y;   // Cast integer to float
int num = atoi("123");          // String to integer
float f = atof("3.14");         // String to float
```

#### String Functions Quick Reference
```c
strlen(s)              // Get length
strcmp(s1, s2)         // Compare (0 if equal)
strcpy(dest, src)      // Copy string
strcat(dest, src)      // Concatenate
toupper(c)             // Character to uppercase
tolower(c)             // Character to lowercase
isalpha(c)             // Check if alphabetic
isdigit(c)             // Check if digit
isspace(c)             // Check if whitespace
```

#### Common Patterns

**Input Validation:**
```c
int n;
do
{
    n = get_int("Positive: ");
}
while (n < 1);
```

**Array Traversal:**
```c
for (int i = 0; i < size; i++)
{
    printf("%i\n", arr[i]);
}
```

**String Traversal:**
```c
for (int i = 0, n = strlen(s); i < n; i++)
{
    printf("%c", s[i]);
}
```

**Finding Max/Min:**
```c
int max = arr[0];
for (int i = 1; i < size; i++)
{
    if (arr[i] > max)
    {
        max = arr[i];
    }
}
```

#### Exit Codes
```c
return 0;    // Success
return 1;    // Error/failure
```

#### Memory Sizes (For Reference)
```
bool:    1 byte
char:    1 byte
int:     4 bytes
float:   4 bytes
double:  8 bytes
long:    8 bytes
```

---

## 6. Final Week 1 Summary

### The Essence of Week 1 in Simple Terms:

**Week 1 transforms you from a visual programmer to a text-based programmer.** You learned that C requires precise syntax and explicit instructions for everything. The compilation process converts your human-readable code into machine language. Variables are typed containers for data, and choosing the right type matters. Conditionals let programs make decisions, loops enable repetition without redundancy, and functions organize code into reusable, testable pieces. Arrays store collections of same-type data, and strings are just character arrays ending with '\0'. Understanding these fundamentals deeply is crucial—they're the building blocks for everything else in CS50 and computer science. **Master Week 1, and you're ready for the journey ahead!**

---

## 7. Additional Study Tips & Resources

### Before Moving to Week 2 - Checklist:

**Knowledge Checklist:**
- [ ] Can explain compilation steps (preprocessing → compiling → assembling → linking)
- [ ] Understand difference between declaration and definition
- [ ] Know when to use each data type (int, float, char, bool, string)
- [ ] Can write and debug loops without off-by-one errors
- [ ] Comfortable creating and calling functions with parameters
- [ ] Understand array indexing (starts at 0!)
- [ ] Know how strings are stored (character arrays with '\0')
- [ ] Can handle command-line arguments (argc, argv)
- [ ] Able to debug using printf statements
- [ ] Understand operator precedence and type casting

**Practical Skills:**
- [ ] Complete all Week 1 problem sets (Mario, Cash/Credit)
- [ ] Can write a function without looking at examples
- [ ] Comfortable with nested loops
- [ ] Can manipulate strings (iterate, modify characters)
- [ ] Able to validate user input properly
- [ ] Can read and understand others' C code
- [ ] Know how to use `make`, `./`, and debugging tools

---

### Common Week 1 Misconceptions (IMPORTANT!)

#### ❌ **Misconception 1:** Arrays start at index 1
✅ **Reality:** Arrays start at index 0. An array of size 5 has indices 0-4.

#### ❌ **Misconception 2:** `=` is used for comparison
✅ **Reality:** `=` is assignment. Use `==` for comparison.
```c
if (x = 5)    // WRONG - assigns 5 to x
if (x == 5)   // CORRECT - compares x with 5
```

#### ❌ **Misconception 3:** Integer division gives decimals
✅ **Reality:** `5 / 2` equals `2`, not `2.5`. Use type casting: `(float) 5 / 2`

#### ❌ **Misconception 4:** Strings can be compared with `==`
✅ **Reality:** Use `strcmp(s1, s2) == 0` to check if strings are equal

#### ❌ **Misconception 5:** Variables are automatically initialized to 0
✅ **Reality:** Uninitialized variables contain garbage values!
```c
int x;           // x has random garbage value
printf("%i", x); // Undefined behavior!
```

#### ❌ **Misconception 6:** You can change array size after declaration
✅ **Reality:** Arrays have fixed size in C. Use size from beginning.

#### ❌ **Misconception 7:** `string` is a built-in C type
✅ **Reality:** It's defined in CS50 library. In standard C, use `char[]`

#### ❌ **Misconception 8:** Forgetting `\0` doesn't matter
✅ **Reality:** String functions need `\0` to know where the string ends!

---

### Key Debugging Strategies

#### 1. **Printf Debugging (Your Best Friend)**
```c
printf("DEBUG: x = %i, y = %i\n", x, y);  // Track variables
printf("DEBUG: Reached line 42\n");        // Track execution flow
printf("DEBUG: Loop iteration %i\n", i);   // Track loop progress
```

#### 2. **Rubber Duck Debugging**
- Explain your code line-by-line to someone (or a rubber duck!)
- Forces you to slow down and think through logic
- Often reveals bugs just by explaining

#### 3. **Simplify and Test**
```c
// Instead of writing entire program at once:
// 1. Write main function skeleton
// 2. Add input handling, test it
// 3. Add one feature, test it
// 4. Add next feature, test it
// Build incrementally!
```

#### 4. **Check Boundaries**
```c
// Always test edge cases:
// - Empty input
// - Minimum valid value
// - Maximum valid value
// - Just below minimum
// - Just above maximum
```

#### 5. **Read Error Messages Carefully**
```c
// Error message tells you:
// 1. File name
// 2. Line number (sometimes line before has the error!)
// 3. What went wrong

// Example:
// mario.c:15:5: error: expected ';' before 'printf'
// Means: Line 14 is missing a semicolon!
```

---

### Learning Resources

#### Official CS50 Resources:
- **CS50 Manual Pages**: Type `man function_name` in terminal (e.g., `man printf`)
- **CS50 Documentation**: https://cs50.readthedocs.io/
- **CS50 Reference**: https://cs50.harvard.edu/x/2024/reference/
- **help50**: Type `help50 make program` for beginner-friendly error explanations
- **style50**: Check if your code follows CS50 style guidelines
- **check50**: Automated testing for problem sets

#### Practice Platforms:
- **CS50 Sandbox**: Quick online C compiler (sandbox.cs50.io)
- **Exercism.org**: C programming track with mentor feedback
- **LeetCode Easy Problems**: Focus on array/string manipulation
- **HackerRank C**: Basic C programming challenges

#### Community Support:
- **CS50 Discord**: Real-time help from peers and staff
- **CS50 Subreddit**: r/cs50
- **CS50 Ed Discussion**: Official Q&A platform
- **Stack Overflow**: Search for specific C programming questions

---

### Study Schedule Suggestion (1 Week Plan)

**Day 1: Fundamentals Review**
- Compilation, data types, variables
- Complete problems 1-3 from practice section

**Day 2: Control Flow**
- Conditionals and loops mastery
- Complete problems 4-6 from practice section

**Day 3: Functions & Modular Design**
- Function declaration, definition, scope
- Complete problems 7-9 from practice section

**Day 4: Arrays & Strings**
- Array manipulation, string operations
- Complete problem 10 from practice section

**Day 5: Mini-Project**
- Build the Grade Book System
- Try adding your own features

**Day 6: Problem Set Practice**
- Revisit Mario and Cash/Credit
- Try completing them without hints

**Day 7: Review & Test**
- Go through Quick Revision Sheet
- Explain concepts to someone else
- Take a practice test or build something new

---

### Pro Tips from CS50 Veterans

1. **Don't copy-paste code blindly** - Type it out yourself to build muscle memory
2. **Comment your code** - Helps you think through logic and helps others understand
3. **Start problem sets early** - They take longer than you think
4. **Use meaningful variable names** - `student_count` is better than `x`
5. **Test incrementally** - Don't write 100 lines before testing
6. **Read specifications carefully** - Problem sets have specific requirements
7. **Format your code properly** - Use consistent indentation (style50 helps!)
8. **Don't be afraid to start over** - Sometimes a fresh start with new approach works better
9. **Understand, don't memorize** - Focus on why code works, not just what it does
10. **Ask for help when stuck** - But try debugging yourself first for 30+ minutes

---

### Warning Signs You Need More Practice

If you struggle with these, revisit the corresponding sections:

- ❗ **Can't write a for loop from scratch** → Review section 1.6
- ❗ **Don't understand why type casting is needed** → Review section 1.4
- ❗ **Confused about when to use & in scanf** → Review section 1.9
- ❗ **Can't explain what a function does by reading it** → Review section 1.7
- ❗ **Don't know difference between argc and argv** → Review section 1.10
- ❗ **Still getting compilation errors frequently** → Review section 1.1 & 1.11
- ❗ **Arrays and strings feel mysterious** → Review section 1.8
- ❗ **Can't debug simple logic errors** → Review section 1.11

---

### Next Steps: Preparing for Week 2

**Week 2 Preview:**
Week 2 introduces **arrays in depth**, **algorithms** (searching and sorting), **computational complexity** (Big O notation), and **cryptography basics**. The foundation you built in Week 1 will be crucial!

**Skills to strengthen before Week 2:**
- Array manipulation (you'll do A LOT of this)
- Nested loops (especially for 2D arrays)
- Functions (you'll write many helper functions)
- String operations (many Week 2 problems involve text)
- Command-line arguments (used in Week 2 problem sets)

---

### Motivational Reminders

💡 **"The only way to learn programming is by programming."** - Don't just read, CODE!

💡 **Debugging is normal.** Even experienced programmers spend more time debugging than writing new code.

💡 **Struggle is part of learning.** If it feels hard, you're growing. If it feels easy, you might not be challenging yourself enough.

💡 **CS50 is designed to be challenging.** You're learning college-level computer science. Embrace the difficulty!

💡 **Everyone learns at different speeds.** Don't compare yourself to others. Compare yourself to who you were yesterday.

---

## 8. Bonus: Week 1 Concept Connections Map

### How Week 1 Concepts Connect:

```
COMPILATION
    ↓
    Converts source code to machine code
    ↓
VARIABLES & DATA TYPES
    ↓
    Store values that you can...
    ↓
OPERATORS & EXPRESSIONS
    ↓
    Manipulate and compare, leading to...
    ↓
CONDITIONALS
    ↓
    Make decisions and...
    ↓
LOOPS
    ↓
    Repeat actions efficiently on...
    ↓
ARRAYS & STRINGS
    ↓
    Collections of data processed by...
    ↓
FUNCTIONS
    ↓
    Organized, reusable code blocks
    ↓
COMMAND-LINE ARGUMENTS
    ↓
    External input for flexible programs
    ↓
DEBUGGING
    ↓
    Finding and fixing errors in all of the above!
```

---

## 9. Self-Assessment Quiz (Try Before Looking at Answers!)

**Question 1:** What's the output?
```c
int x = 7;
int y = 2;
printf("%i\n", x / y);
```
<details>
<summary>Answer</summary>
`3` - Integer division truncates the decimal part.
</details>

**Question 2:** What's wrong with this code?
```c
int arr[5];
for (int i = 0; i <= 5; i++)
{
    arr[i] = i;
}
```
<details>
<summary>Answer</summary>
Off-by-one error! Array indices are 0-4, but loop goes to 5. Should be `i < 5`.
</details>

**Question 3:** What's the output?
```c
string s = "Hello";
printf("%c\n", s[1]);
```
<details>
<summary>Answer</summary>
`e` - Second character (index 1) of "Hello".
</details>

**Question 4:** Will this compile?
```c
int main(void)
{
    int x = add(5, 3);
    printf("%i\n", x);
}

int add(int a, int b)
{
    return a + b;
}
```
<details>
<summary>Answer</summary>
No! Function `add` is called before it's declared. Need to add prototype: `int add(int a, int b);` before `main()`.
</details>

**Question 5:** What's the problem?
```c
string password = get_string("Password: ");
if (password == "secret123")
{
    printf("Access granted\n");
}
```
<details>
<summary>Answer</summary>
Can't compare strings with `==`. Use `strcmp(password, "secret123") == 0` instead.
</details>

---

## 10. Final Motivational Message

🎓 **Congratulations on completing your Week 1 revision!**

You've just covered the fundamental building blocks of programming. Every complex program you'll ever write—from web applications to artificial intelligence—relies on these exact concepts. 

**Remember:**
- Variables store information
- Conditionals make decisions  
- Loops create efficiency
- Functions organize complexity
- Arrays handle collections
- Debugging builds resilience

These aren't just programming concepts; they're problem-solving tools that train your brain to think logically and systematically.

**Week 1 is tough because it's teaching you a completely new way of thinking.** But you're doing it! Every error message you encounter, every bug you fix, and every concept you grasp makes you a better programmer.
**The CS50 journey is like climbing a mountain.** Week 1 is learning to walk with proper hiking boots. It feels awkward at first, but soon you'll be running up trails, and eventually scaling peaks you never thought possible.

**Keep coding. Keep debugging. Keep learning.**

**You've got this! 🚀**

---

**Pro Tip:** Bookmark this guide and return to it whenever you need a quick refresher. The Quick Revision Sheet (Section 5) is especially useful right before problem sets!

**Next:** Once you're confident with Week 1, dive into Week 2: Arrays & Algorithms. The adventure continues! 💻

---

*Created with ❤️ for CS50x students worldwide. Happy coding!*