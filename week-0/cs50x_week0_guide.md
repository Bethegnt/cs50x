# CS50x Week 0: Comprehensive Revision Guide
## Scratch and Computational Thinking

---

## 1. Introduction to Computer Science

### What Computer Science Actually Is

Computer science is **fundamentally about problem-solving**, not just programming. It's the study of computational approaches to solving problems systematically and efficiently.

**Key Understanding:**
- Programming is a *tool* of computer science, not its definition
- CS involves: algorithm design, data organization, efficiency analysis, and creative problem-solving
- You're learning to think computationally, not just memorize syntax

### Problem-Solving as the Core of CS

Every computer science challenge boils down to:
1. Understanding the problem clearly
2. Breaking it into manageable pieces
3. Designing a solution strategy
4. Implementing that strategy
5. Testing and refining

**Real-World Analogy:** Like a chef approaching a new recipe - understand what you're making, gather ingredients (inputs), follow steps (process), create the dish (output).

### Why CS50 Starts with Scratch

David Malan's philosophy centers on **lowering the barrier to entry**:

- **Visual blocks** eliminate syntax errors (no missing semicolons!)
- Focus on *logic* rather than memorizing keywords
- Immediate visual feedback makes debugging intuitive
- Drag-and-drop reduces frustration for beginners
- The concepts (loops, variables, functions) are identical to "real" programming languages

**Important:** Scratch is not "baby programming" - it's used by MIT researchers for prototyping and teaching algorithmic thinking at all levels.

### David Malan's Philosophy

- **Start with engagement:** Make programming fun and creative first
- **Concepts over syntax:** Logic remains the same across all languages
- **Iterative learning:** Build confidence before adding complexity
- **Community learning:** Share projects, learn from peers

---

## 2. Computational Thinking

### Breaking Down Complex Problems

**Decomposition** is the process of taking large, overwhelming problems and dividing them into smaller, solvable sub-problems.

**Example: Making a Scratch Game**
- Large problem: "Create a maze game"
- Broken down:
  - Player movement system
  - Wall collision detection
  - Goal reaching condition
  - Score tracking
  - Level progression

### Thinking Algorithmically and Systematically

An **algorithmic approach** means creating clear, ordered steps that always work:

**Bad approach:** "Move the sprite around somehow until it reaches the goal"
**Algorithmic approach:**
1. When right arrow pressed, move sprite 10 steps right
2. After each move, check if touching wall
3. If touching wall, move back 10 steps
4. If touching goal, display "You win!"

### Pattern Recognition

Identifying similarities across different problems allows reusing solutions.

**Example in Scratch:**
- Moving a player with arrow keys → Same pattern for any sprite
- Counting score → Same pattern for counting lives, time, coins
- Collision detection → Works for walls, enemies, items

### Abstraction in Thinking

Focusing on **what** something does, not **how** it does it internally.

**Example:** Using a "jump" custom block
- You don't need to know the physics calculation each time
- Just use "jump" whenever needed
- The complexity is hidden inside the block

### How to Approach Problems Methodically

**The CS50 Problem-Solving Framework:**
1. **Understand:** What exactly is being asked?
2. **Plan:** Sketch out the logic before coding
3. **Divide:** Break into smaller sub-problems
4. **Conquer:** Solve each piece independently
5. **Test:** Check each component works
6. **Integrate:** Combine pieces together
7. **Debug:** Fix issues systematically

---

## 3. Problem-Solving Framework: Input → Process → Output

### The Universal Model

Every computer program, from Scratch to Google's search engine, follows this pattern:

**INPUT** → **PROCESS** → **OUTPUT**

### Real-World Examples

**Calculator:**
- Input: Numbers and operation (5, +, 3)
- Process: Mathematical computation
- Output: Result (8)

**Social Media Post:**
- Input: Text, images, user clicks "post"
- Process: Store data, notify followers, update feed
- Output: Post appears on timelines

**Scratch Cat Movement:**
- Input: Right arrow key pressed
- Process: Change x-coordinate by 10
- Output: Cat appears in new position

**Traffic Light:**
- Input: Timer reaches threshold, sensor detects cars
- Process: Logic to determine next light state
- Output: Change light color, signal to cars

### How Every Program Follows This Pattern

Even complex programs are just chains of Input→Process→Output:

**Example: Simple Scratch Game**
```
Input: Player presses spacebar
Process: Check if sprite is on ground
         If yes, change y by 50 (jump)
         Play jump sound
Output: Sprite moves upward
        Sound plays from speakers
```

### Practice: Identifying Inputs and Outputs

**Daily Life Examples:**
- **Microwave:** Input = time setting, start button | Output = heated food, beep
- **Login System:** Input = username, password | Output = access granted/denied message
- **Thermostat:** Input = temperature sensor reading, target temp | Output = heater on/off signal

---

## 4. Number Systems and Representation

### Unary System (Base-1)

The simplest counting system: one symbol repeated.

**How it works:**
- 1 = |
- 2 = ||
- 3 = |||
- 5 = |||||

**When/Why it's used:**
- Tally marks for counting
- Prison wall calendars in movies
- Very intuitive but impractical for large numbers

**Problem:** Representing 100 requires 100 symbols!

### Binary System (Base-2)

The language of computers: only 0s and 1s.

**Why Computers Use Binary:**
- Electrical signals: ON (1) or OFF (0)
- Transistors have two states
- Easy to transmit reliably (just two voltage levels)
- Simple circuit design

**How Binary Works:**
Each position represents a power of 2:

```
Position: 128  64  32  16   8   4   2   1
Binary:    1   0   1   0   0   1   1   0
```

This reads as: (1×128) + (0×64) + (1×32) + (0×16) + (0×8) + (1×4) + (1×2) + (0×1) = **166**

**Converting Decimal to Binary:**

Convert 13 to binary:
- 13 ÷ 2 = 6 remainder **1**
- 6 ÷ 2 = 3 remainder **0**
- 3 ÷ 2 = 1 remainder **1**
- 1 ÷ 2 = 0 remainder **1**

Read remainders from bottom to top: **1101**

**Verification:** (1×8) + (1×4) + (0×2) + (1×1) = 13 ✓

### Decimal System (Base-10)

Our everyday counting system: digits 0-9.

Each position is a power of 10:
```
1000s  100s  10s  1s
  2     4     3   7
```
= (2×1000) + (4×100) + (3×10) + (7×1) = 2437

**Why humans use decimal:** We have 10 fingers!

### Practice Conversions

**Binary to Decimal:**
- 1010 = (1×8) + (0×4) + (1×2) + (0×1) = **10**
- 1111 = (1×8) + (1×4) + (1×2) + (1×1) = **15**
- 10000 = (1×16) = **16**

**Decimal to Binary:**
- 7 = 111 (4+2+1)
- 20 = 10100 (16+4)
- 31 = 11111 (16+8+4+2+1)

---

## 5. Character Encoding

### ASCII (American Standard Code for Information Interchange)

A system mapping characters to numbers so computers can store text.

**Key ASCII Values to Remember:**
- **A** = 65, **B** = 66, **C** = 67... **Z** = 90
- **a** = 97, **b** = 98, **c** = 99... **z** = 122
- **0** = 48, **1** = 49... **9** = 57
- **space** = 32
- **!** = 33

**Pattern:** Capital letters come before lowercase (A=65, a=97, difference of 32)

**How Computers Store Text:**
When you type "Hi":
- Computer stores: 72 105
- 72 (binary: 01001000) = H
- 105 (binary: 01101001) = i

### Unicode

**The Problem with ASCII:** Only 128 characters - no emojis, Chinese characters, Arabic script, etc.

**Unicode Solution:**
- Millions of possible characters
- Includes every written language
- Emojis: 😂 = U+1F602
- Supports global communication

**Example:**
- ASCII can store "Hello"
- Unicode can store "Hello" + "你好" + "مرحبا" + "😊"

### Practical Examples

**In Scratch:**
When you use the "ask" block and someone types their name:
- Scratch receives it as text
- Internally stored as numbers (Unicode values)
- Displayed back to you as characters

**Email Address Validation:**
Checking if "@" symbol (ASCII 64) exists in entered text.

---

## 6. Color Representation

### RGB System: The Language of Digital Color

Every pixel on your screen displays colors by mixing Red, Green, and Blue light.

**How It Works:**
- Each color channel: 0 (off) to 255 (maximum brightness)
- Format: RGB(red, green, blue)
- Total possible colors: 256 × 256 × 256 = **16.7 million colors**

### RGB Examples

**Pure Colors:**
- **Red:** RGB(255, 0, 0) - only red at max, others off
- **Green:** RGB(0, 255, 0)
- **Blue:** RGB(0, 0, 255)

**Mixed Colors:**
- **Yellow:** RGB(255, 255, 0) - red + green
- **Cyan:** RGB(0, 255, 255) - green + blue
- **Magenta:** RGB(255, 0, 255) - red + blue

**Neutrals:**
- **White:** RGB(255, 255, 255) - all colors at maximum
- **Black:** RGB(0, 0, 0) - all colors off
- **Gray:** RGB(128, 128, 128) - all colors at half

**Custom Colors:**
- **Orange:** RGB(255, 165, 0)
- **Purple:** RGB(128, 0, 128)
- **Pink:** RGB(255, 192, 203)

### How Pixels and Screens Work

Your screen is a grid of millions of tiny pixels. Each pixel contains three sub-pixels:
- One red LED
- One green LED  
- One blue LED

When you set RGB(100, 200, 150):
- Red LED glows at 39% brightness (100/255)
- Green LED glows at 78% brightness (200/255)
- Blue LED glows at 59% brightness (150/255)
- Your eye sees the mixed result

### In Scratch

While Scratch uses simplified color pickers, understanding RGB helps:
- **Pen color:** Set with RGB values in extensions
- **Graphic effects:** Color effect shifts hue
- **Costume editing:** Paint editor uses RGB concepts

---

## 7. Abstraction

### Definition: Hiding Complexity

**Abstraction** means hiding the complex implementation details and exposing only what's necessary.

**Core Principle:** You don't need to know *how* something works internally to *use* it effectively.

### Real-World Examples

**Car Dashboard:**
- **Abstraction shown:** Speedometer, fuel gauge, warning lights
- **Hidden complexity:** Engine combustion, fuel injection systems, electronic control units
- **Why:** Driver only needs to know speed and fuel level, not how the engine converts gasoline to motion

**Smartphone Interface:**
- **Abstraction shown:** "Send" button for email
- **Hidden complexity:** Network protocols, DNS lookups, server routing, encryption
- **Why:** User wants to send a message, not understand TCP/IP

**Restaurant Menu:**
- **Abstraction shown:** "Pasta Carbonara"
- **Hidden complexity:** Recipe steps, ingredient preparation, cooking techniques
- **Why:** Diner wants food, not cooking instructions

### How Scratch Itself Is Abstraction

**"Move 10 steps" Block:**
- **What you see:** Simple drag-and-drop block
- **Hidden underneath:**
  - Trigonometry calculations (cos/sin for direction)
  - Coordinate system updates (x and y values)
  - Screen rendering refresh
  - Collision boundary recalculation

**Why this matters:** You can make the cat move without understanding trigonometry!

### Layers of Abstraction in Computing

**From Highest to Lowest:**

1. **Scratch Blocks** ← You work here!
   - "Say Hello for 2 seconds"

2. **High-Level Languages (C, Python)**
   - `printf("Hello");`

3. **Assembly Language**
   - `MOV AX, message` / `CALL print`

4. **Machine Code (Binary)**
   - `01001000 01100101 01101100...`

5. **Electrical Signals**
   - Voltage high/low in circuits

**Key Insight:** Each layer abstracts away the layer below it. You benefit from all layers without thinking about them.

### Creating Abstraction in Scratch

**Custom Blocks = Your Own Abstractions**

Instead of repeating:
```
Change x by 10
If on edge, bounce
Change costume
Play sound
```

Create custom block called "move player" containing all of the above. Now you just use "move player" everywhere!

**Benefits:**
- Code is more readable
- Changes made in one place affect all uses
- Easier to debug and maintain

---

## 8. Algorithms

### Definition

An **algorithm** is a step-by-step procedure for solving a problem or accomplishing a task.

**Key Characteristics:**
- **Finite:** Must eventually end
- **Definite:** Each step is clear and unambiguous
- **Input:** Takes zero or more inputs
- **Output:** Produces at least one output
- **Effective:** Steps must be basic enough to be executed

### Everyday Algorithms

**Recipe for Making Tea:**
1. Fill kettle with water
2. Turn on kettle
3. Wait for water to boil
4. Place tea bag in cup
5. Pour hot water into cup
6. Wait 3 minutes
7. Remove tea bag
8. Add milk/sugar if desired
9. Stir and serve

**IKEA Furniture Assembly:**
1. Unpack all pieces
2. Identify parts using diagram
3. Sort screws and hardware
4. Follow step-by-step instructions
5. Connect piece A to piece B
6. Continue until complete

**Morning Routine:**
1. Alarm rings → wake up
2. Brush teeth
3. Shower
4. Get dressed
5. Eat breakfast
6. Leave for work/school

### Phone Book Search Example (From CS50 Lecture)

**Problem:** Find "Mike Smith" in a phone book with 1000 pages.

**Algorithm 1: Linear Search (Page by Page)**
```
1. Start at page 1
2. Check if Mike Smith is on this page
3. If yes, done!
4. If no, go to next page
5. Repeat until found
```
- **Worst case:** Check all 1000 pages
- **Speed:** Slow but guaranteed to work

**Algorithm 2: Binary Search (Divide and Conquer)**
```
1. Open to middle of book (page 500)
2. Is Mike Smith before or after this page?
3. If before, ignore pages 501-1000
4. If after, ignore pages 1-500
5. Repeat with remaining half
6. Continue halving until found
```
- **Worst case:** About 10 checks (log₂ 1000)
- **Speed:** Much faster!

**Key Lesson:** Different algorithms solve the same problem at different speeds.

### Efficiency and Correctness

**Two Critical Qualities:**

1. **Correctness:** Does it give the right answer?
2. **Efficiency:** How fast does it run? How much memory does it use?

**Trade-offs:**
- Sometimes simple but slow is better (if data is small)
- Sometimes complex but fast is necessary (for large data)
- Readability also matters for maintenance

**Bad Algorithm Example:**
Finding largest number by checking every possible number from 1 to infinity → correct in theory but never finishes!

**Good Algorithm Example:**
Finding largest number by checking each number once, keeping track of the current maximum → fast and correct.

---

## 9. Running Time and Efficiency

### How to Measure Algorithm Speed

We measure efficiency by **counting operations** (steps), not actual seconds.

**Why?** Because:
- Different computers run at different speeds
- The same code runs differently on phone vs. supercomputer
- Operations count stays consistent regardless of hardware

### Linear Search vs Binary Search

**Linear Search Example:** Finding your friend in a line of 100 people.
- Check person 1: "Are you Sarah?" No.
- Check person 2: "Are you Sarah?" No.
- Check person 3: "Are you Sarah?" No.
- Continue...
- **Worst case:** 100 checks
- **Pattern:** n items = n checks maximum

**Binary Search Example:** Finding a word in a sorted dictionary.
- Open to middle
- Word comes before/after?
- Open to middle of correct half
- Repeat
- **Worst case:** log₂ n checks
- **For 100 items:** Only 7 checks maximum!

### Big O Notation (Conceptual Introduction)

**Big O** describes how algorithm speed grows as data size increases.

**Common Patterns:**

**O(n) - Linear Time:**
- Speed grows directly with data size
- 10 items = 10 steps
- 1000 items = 1000 steps
- Example: Linear search, going through a list

**O(log n) - Logarithmic Time:**
- Speed grows very slowly
- 1000 items = 10 steps
- 1,000,000 items = 20 steps
- Example: Binary search

**O(n²) - Quadratic Time:**
- Speed grows with square of data size
- 10 items = 100 steps
- 100 items = 10,000 steps
- Example: Comparing every item with every other item

**Visualization:**
```
Items:    10      100     1,000    10,000
O(log n): 3       7       10       13        ← Fast!
O(n):     10      100     1,000    10,000    ← Okay
O(n²):    100     10,000  1M       100M      ← Slow!
```

### Why Efficiency Matters

**In Scratch:**
- Inefficient game = laggy, unresponsive
- Checking collision 1000 times per second vs. only when needed

**In Real World:**
- Google searching billions of web pages in milliseconds
- GPS calculating route among millions of possibilities
- Video streaming without buffering

**Example:** Loading 1 million Instagram posts
- Bad algorithm: 5 minutes of loading
- Good algorithm: 2 seconds

---

## 10. Pseudocode

### What Is Pseudocode?

**Pseudocode** is a way to plan your program using structured English (or any language) before writing actual code.

**Purpose:**
- Bridge between human thinking and computer code
- Plan logic without worrying about syntax
- Communicate algorithms to others
- Catch logical errors before coding

### Characteristics

- Looks like code but reads like English
- Uses common programming structures (if, while, for)
- Indentation shows structure
- No strict syntax rules

### Phone Book Algorithm in Pseudocode

**From CS50 Lecture:**

```
1  Pick up phone book
2  Open to middle of phone book
3  Look at page
4  If person is on page
5      Call person
6  Else if person is earlier in book
7      Open to middle of left half of book
8      Go back to line 3
9  Else if person is later in book
10     Open to middle of right half of book
11     Go back to line 3
12 Else
13     Quit
```

**Notice:**
- Clear steps anyone can follow
- Uses "if/else" logic
- "Go back to line X" = loop concept
- Not actual code, but close enough to translate easily

### Planning a Scratch Game with Pseudocode

**Game Concept:** Simple catching game

**Pseudocode:**
```
When game starts:
    Set score to 0
    Set lives to 3
    
Forever:
    Move falling object down
    If object touches bottom:
        Decrease lives by 1
        Reset object to top
        If lives = 0:
            Say "Game Over"
            Stop all
            
When player moves mouse:
    Set paddle x to mouse x position
    
If falling object touches paddle:
    Increase score by 1
    Play catch sound
    Reset object to top with random x position
```

**Benefit:** You can spot issues (e.g., "what if two objects touch at once?") before building anything!

### Converting Pseudocode to Scratch

**Pseudocode:**
```
If score is greater than 10:
    Say "You win!"
    Play victory sound
```

**Scratch Blocks:**
- "If [score > 10] then"
- "Say [You win!] for 2 seconds"
- "Play sound [victory] until done"

---

## 11. Scratch Programming - Functions

### What Functions Are

**Functions** are reusable blocks of code that perform specific actions. Think of them as **verbs** in programming.

**Real-World Analogy:** A vending machine button
- You press B4
- Don't need to know: mechanical arms, inventory tracking, payment processing
- Just get: your snack

### Built-In Scratch Functions

**Motion Blocks:**
- `move (10) steps` - moves sprite forward
- `turn (15) degrees` - rotates sprite
- `go to x: (0) y: (0)` - teleports to coordinates
- `glide (1) secs to x: (0) y: (0)` - smooth movement

**Looks Blocks:**
- `say [Hello!] for (2) seconds` - speech bubble
- `show` / `hide` - visibility toggle
- `switch costume to [costume1]` - change appearance
- `change size by (10)` - grow/shrink

**Sound Blocks:**
- `play sound [meow] until done` - plays completely
- `start sound [meow]` - plays in background
- `change volume by (-10)` - adjusts loudness

**Event Blocks:**
- `when green flag clicked` - program start trigger
- `when [space] key pressed` - keyboard input

### Creating Custom Blocks (Define Function)

**When to Create Custom Functions:**
- Code used multiple times
- Complex sequence you want to simplify
- Organizing code into logical pieces

**How to Create:**
1. Go to "My Blocks" category
2. Click "Make a Block"
3. Name it (e.g., "reset game")
4. Add code underneath "define reset game"

**Example: Reset Game Function**

```
define reset game
    go to x: (0) y: (0)
    set [score] to (0)
    set [lives] to (3)
    show
    say [Ready?] for (2) seconds
```

**Usage:**
Now anywhere you need to reset, just use: `reset game` block!

**Benefits:**
- Write once, use many times
- Change in one place affects all uses
- Code easier to read: "reset game" is clearer than 5 separate blocks

### Functions with Inputs (Coming up in Arguments section)

**Preview:** Functions become more powerful with inputs:
- `jump with height (50)` - customizable jump
- `move player direction [right]` - flexible movement

---

## 12. Scratch Programming - Arguments and Return Values

### Arguments: Inputs to Functions

**Arguments** are values you pass into a function to customize its behavior.

**Analogy:** Ordering coffee
- Function: "make coffee"
- Arguments: size (large), milk (oat), shots (2)
- Each argument changes the result

### Scratch Examples with Arguments

**Say Block:**
```
say [Hello!] for (2) seconds
```
- Arguments: "Hello!" (what to say), 2 (how long)
- Try: `say [Welcome] for (5) seconds` - different arguments, different result

**Move Block:**
```
move (10) steps
```
- Argument: 10 (how far to move)
- Change to 50: `move (50) steps` - sprite moves 5x farther

**Glide Block:**
```
glide (1) secs to x: (100) y: (50)
```
- Arguments: 1 (duration), 100 (x position), 50 (y position)

### Custom Blocks with Arguments

**Creating a Custom Block with Inputs:**

1. Make a Block called "jump"
2. Add input: "height" (number)
3. Define:
```
define jump (height)
    change y by (height)
    wait (0.1) seconds
    change y by ((height) * (-1))
```

**Usage:**
- `jump (50)` - small jump
- `jump (100)` - big jump
- `jump (height_variable)` - dynamic jump based on power-up

### Return Values: Outputs from Functions

**Return values** are results that functions give back to you.

**Analogy:** ATM machine
- Input: card, PIN, withdrawal amount
- Process: verify, deduct from account
- Return: cash bills (the "return value")

### Scratch Blocks That Return Values

**Sensing Blocks (Boolean Returns):**
```
<touching [sprite]?>
<key [space] pressed?>
<mouse down?>
```
- Return: true or false
- Used in conditional statements

**Operator Blocks:**
```
((5) + (3))
((score) * (2))
(join [Hello ] [World])
```
- Return: calculated result
- Can be used as arguments to other blocks

**Variable Blocks:**
```
(score)
(lives)
(player_speed)
```
- Return: current value of the variable

### Using Return Values

**Example: Conditional with Return Value**
```
if <(score) > (10)> then
    say [Great job!] for (2) seconds
end
```
- `(score)` returns the score value
- `> (10)` compares and returns true/false
- `if` block uses that true/false to decide

**Example: Calculation with Return Value**
```
set [total] to ((price) * (quantity))
```
- `(price)` returns price value
- `(quantity)` returns quantity value
- Multiplication returns result
- Result stored in `total`

### Common Mistake

**Confusing Arguments and Return Values:**
- **Argument:** What you give TO the function
- **Return value:** What you get BACK FROM the function

Example: `say [score] for (2) seconds`
- Arguments going IN: "score" text, 2 seconds duration
- Return value coming OUT: none (this function displays but doesn't return data)

Example: `(length of [hello])`
- Argument going IN: "hello" text
- Return value coming OUT: 5 (the length)

---

## 13. Scratch Programming - Variables

### What Variables Are

**Variables** are named containers that store values which can change during program execution.

**Analogy:** Think of variables as labeled boxes:
- Box labeled "score" holds a number
- You can look at what's inside (read)
- You can change what's inside (write)
- The label stays the same, but contents change

### Creating Variables in Scratch

**Steps:**
1. Go to "Variables" category
2. Click "Make a Variable"
3. Name it descriptively: `score`, `lives`, `player_speed`
4. Choose scope: "For all sprites" or "For this sprite only"

### Common Variable Types in Games

**Score Variables:**
```
set [score] to (0)          ← Start at zero
change [score] by (1)       ← Increment (collecting coin)
change [score] by (10)      ← Bigger reward (defeating enemy)
```

**Lives/Health Variables:**
```
set [lives] to (3)          ← Start with 3 lives
change [lives] by (-1)      ← Lose a life (hit by enemy)
if <(lives) < (1)>                  ← Less than
<(answer) = (42)>                 ← Equal to
```

**Examples in Context:**

**Collision Detection:**
```
if <touching [enemy]?> then       ← Boolean: true if touching
    change [lives] by (-1)
    say [Ouch!] for (1) seconds
end
```

**Score Checking:**
```
if <(score) > (100)> then         ← Boolean: true if score exceeds 100
    say [You win!] for (2) seconds
    stop [all]
end
```

**Key Press Detection:**
```
if <key [right arrow] pressed?> then    ← Boolean: true when pressed
    change x by (10)
end
```

### Combining Conditions with Logical Operators

**AND Block:** Both conditions must be true
```
<<(score) > (50)> and <(lives) > (0)>>
```
- True only if score > 50 AND lives > 0
- Both must be true

**OR Block:** At least one condition must be true
```
<<key [left arrow] pressed?> or <key [a] pressed?>>
```
- True if either left arrow OR 'a' is pressed
- Either/both can be true

**NOT Block:** Reverses true/false
```
<not <touching [edge]?>>
```
- True when NOT touching edge
- False when touching edge

### Practical Examples

**Game Win Condition:**
```
if <<(score) > (100)> and <(time) > (0)>> then
    broadcast [victory]
end
```
- Must have score above 100 AND time remaining

**Movement Controls:**
```
if <<key [up arrow] pressed?> and <not <touching [wall]?>>> then
    change y by (10)
end
```
- Move up if up arrow pressed AND not touching wall

**Power-Up Check:**
```
if <<touching [powerup]?> or <(invincible) = (1)>> then
    set [can_break_blocks] to (1)
end
```
- Can break blocks if touching power-up OR already invincible

### Truth Tables (Understanding AND/OR)

**AND Truth Table:**
```
Condition A | Condition B | Result
------------|-------------|-------
   True     |    True     |  True
   True     |    False    |  False
   False    |    True     |  False
   False    |    False    |  False
```
**Both must be true!**

**OR Truth Table:**
```
Condition A | Condition B | Result
------------|-------------|-------
   True     |    True     |  True
   True     |    False    |  True
   False    |    True     |  True
   False    |    False    |  False
```
**At least one must be true!**

### Common Beginner Mistakes

❌ **Mistake: Checking equality with assignment**
```
if <set [score] to (10)> then    ← Wrong! This is assignment, not comparison
```
✅ **Correct:**
```
if <(score) = (10)> then         ← Right! This compares
```

❌ **Mistake: Confusing > and <**
```
if <(lives) > (0)> then          ← "lives greater than 0"
    say [Game Over]               ← Wrong logic! Still have lives!
```
✅ **Correct:**
```
if <(lives) < (1)> then          ← "lives less than 1" (i.e., zero)
    say [Game Over]
```

---

## 15. Scratch Programming - Conditionals

### If-Then Blocks: Basic Decision Making

**Conditionals** allow your program to make decisions and execute different code based on conditions.

**Structure:**
```
if <condition> then
    ← Code runs only if condition is true
end
```

**Real-World Analogy:** 
"If it's raining, then take an umbrella"
- Check condition: Is it raining?
- If yes: Take umbrella
- If no: Do nothing (skip the action)

### Scratch If-Then Examples

**Boundary Detection:**
```
if <touching [edge]?> then
    turn (180) degrees           ← Reverse direction
end
```

**Collision with Enemy:**
```
if <touching [enemy]?> then
    change [lives] by (-1)
    go to x: (0) y: (0)          ← Reset position
    wait (1) seconds              ← Brief invincibility
end
```

**Score Milestone:**
```
if <(score) = (50)> then
    say [Halfway there!] for (2) seconds
    play sound [cheer]
end
```

### If-Then-Else Blocks: Alternative Paths

**Structure:**
```
if <condition> then
    ← Code if condition is TRUE
else
    ← Code if condition is FALSE
end
```

**Real-World Analogy:**
"If you have money, buy coffee; otherwise, drink water"
- Always does one thing or the other
- Never skips both
- Never does both

### Scratch If-Then-Else Examples

**Game Over or Continue:**
```
if <(lives) < (1)> then
    say [Game Over!] for (2) seconds
    stop [all]
else
    say [Keep going!] for (1) seconds
end
```

**Door Lock System:**
```
if <(has_key) = (1)> then
    broadcast [door opens]
    play sound [unlock]
else
    say [You need a key!] for (2) seconds
    play sound [locked]
end
```

**Difficulty Adjustment:**
```
if <(score) > (100)> then
    set [enemy_speed] to (8)     ← Hard mode
else
    set [enemy_speed] to (5)     ← Normal mode
end
```

### Nested Conditionals: Complex Logic

**Nested** means putting conditionals inside other conditionals for multi-level decisions.

**Example: Grading System**
```
if <(score) > (90)> then
    say [Grade: A] for (2) seconds
else
    if <(score) > (80)> then
        say [Grade: B] for (2) seconds
    else
        if <(score) > (70)> then
            say [Grade: C] for (2) seconds
        else
            say [Grade: F] for (2) seconds
        end
    end
end
```

**Example: Movement with Multiple Checks**
```
if <key [right arrow] pressed?> then
    if <not <touching [wall]?>> then
        change x by (10)          ← Only move if no wall
    else
        play sound [bump]         ← Hit wall sound
    end
end
```

**Example: Advanced Game Logic**
```
if <touching [finish line]?> then
    if <(collected_coins) = (10)> then
        say [Perfect! Bonus points!] for (2) seconds
        change [score] by (100)
    else
        say [You finished!] for (2) seconds
        change [score] by (50)
    end
    broadcast [level complete]
end
```

### Real-World Analogy Examples

**ATM Machine Logic:**
```
If card is valid:
    If PIN is correct:
        If balance >= withdrawal amount:
            Dispense cash
        Else:
            Show "Insufficient funds"
    Else:
        Show "Wrong PIN"
Else:
    Show "Invalid card"
```

**Traffic Light System:**
```
If pedestrian button pressed:
    If no cars detected:
        Change to walk signal immediately
    Else:
        Wait for current cycle to finish
        Then change to walk signal
Else:
    Continue normal traffic cycle
```

### Best Practices

**✅ Good: Clear and Logical**
```
if <(lives) > (0)> then
    ← Game continues
else
    ← Game over sequence
end
```

**❌ Bad: Confusing Double Negative**
```
if <not <not <(lives) > (0)>>> then  ← Too complex!
    ← Hard to understand
end
```

**✅ Good: Organized Nesting**
```
if <key [space] pressed?> then
    if <(on_ground) = (1)> then
        ← Jump logic here
    end
end
```

**❌ Bad: Too Many Nested Levels**
```
if <...> then
    if <...> then
        if <...> then
            if <...> then
                if <...> then     ← Too deep! Hard to read
```
**Tip:** More than 3 levels of nesting = consider restructuring

---

## 16. Scratch Programming - Loops

### Why Loops Matter

**Loops** let you repeat code without copying/pasting, following the DRY principle (Don't Repeat Yourself).

**Without Loops (Bad):**
```
move (10) steps
move (10) steps
move (10) steps
move (10) steps
move (10) steps
```

**With Loop (Good):**
```
repeat (5)
    move (10) steps
end
```

### Forever Loops: Continuous Execution

**Structure:**
```
forever
    ← Code repeats endlessly until program stops
end
```

**When to Use:**
- Main game loop
- Continuous animation
- Constant checking (collisions, keyboard input)

**Examples:**

**Game Main Loop:**
```
when green flag clicked
forever
    if <key [right arrow] pressed?> then
        change x by (5)
    end
    if <key [left arrow] pressed?> then
        change x by (-5)
    end
    if <touching [enemy]?> then
        change [lives] by (-1)
    end
end
```

**Continuous Animation:**
```
forever
    next costume                 ← Cycle through costumes
    wait (0.1) seconds           ← Animation speed
end
```

**Following Mouse:**
```
forever
    point towards [mouse-pointer]
    move (3) steps
end
```

### Repeat Loops: Fixed Iterations

**Structure:**
```
repeat (number)
    ← Code executes exactly 'number' times
end
```

**When to Use:**
- Known number of repetitions
- Drawing shapes
- Playing sequence of notes

**Examples:**

**Draw a Square:**
```
repeat (4)
    move (100) steps
    turn (90) degrees
end
```

**Countdown Timer:**
```
set [time] to (10)
repeat (10)
    say (time) for (1) seconds
    change [time] by (-1)
end
say [Time's up!] for (2) seconds
```

**Spawn Multiple Enemies:**
```
repeat (5)
    create clone of [enemy]
    wait (0.5) seconds
end
```

### Repeat Until Loops: Condition-Based Repetition

**Structure:**
```
repeat until <condition>
    ← Code repeats until condition becomes TRUE
end
```

**When to Use:**
- Unknown number of repetitions
- Waiting for specific event
- Searching/scanning until found

**Examples:**

**Move Until Hitting Wall:**
```
repeat until <touching [edge]?>
    move (5) steps
end
```

**Falling Object:**
```
repeat until <<touching [ground]?> or <touching [player]?>>
    change y by (-5)             ← Gravity
    wait (0.05) seconds
end
```

**Password System:**
```
repeat until <(answer) = [secret123]>
    ask [Enter password:] and wait
end
say [Access granted!] for (2) seconds
```

**Level Loading:**
```
set [loaded] to (0)
repeat until <(loaded) = (1)>
    ← Loading animation
    wait (0.1) seconds
    if <all assets ready> then
        set [loaded] to (1)
    end
end
```

### Choosing the Right Loop Type

| Loop Type | Use When... | Example |
|-----------|-------------|---------|
| **Forever** | Needs to run continuously | Game main loop, animation |
| **Repeat (n)** | Know exact repetitions | Draw shape, countdown |
| **Repeat Until** | Wait for condition | Move until collision |

### Avoiding Infinite Loops

**Infinite Loop Problem:**
```
repeat until <(score) > (100)>
    say [Waiting...] for (1) seconds
    ← BUG: Never changes score!
    ← Loop never ends!
end
```

**Fixed Version:**
```
repeat until <(score) > (100)>
    say [Waiting...] for (1) seconds
    change [score] by (1)        ← Now score increases!
end
```

**Another Dangerous Example:**
```
repeat until <touching [edge]?>
    ← BUG: No movement code!
    ← Never reaches edge = infinite loop!
end
```

**Fixed:**
```
repeat until <touching [edge]?>
    move (5) steps               ← Now sprite moves toward edge
end
```

### Loop Best Practices

**✅ Include wait blocks in forever loops:**
```
forever
    move (5) steps
    wait (0.03) seconds          ← Prevents lag
end
```
**Why?** Without wait, loop runs thousands of times per second, causing lag.

**✅ Have exit conditions for repeat until:**
```
repeat until <<touching [goal]?> or <(time) < (1)>>
    ← Can exit if goal reached OR time runs out
end
```

**❌ Avoid forever inside forever (usually):**
```
forever
    forever                      ← Inner loop never exits
        move (10) steps          ← Outer loop never continues
    end
end
```

---

## 17. Scratch Programming - Events

### What Are Events?

**Events** are triggers that start scripts running. They answer: "When should this code execute?"

**Event-Driven Programming:** Code waits for events to happen, then responds.

**Real-World Analogy:** Doorbell
- Event: Someone presses button
- Response: Bell rings, you answer door
- Program waits until event occurs

### When Green Flag Clicked

**The Main Start Event:**
```
when green flag clicked
    ← Program entry point
    ← Usually contains initialization
```

**Common Uses:**

**Initialize Variables:**
```
when green flag clicked
set [score] to (0)
set [lives] to (3)
set [level] to (1)
go to x: (0) y: (0)
show
```

**Start Main Game Loop:**
```
when green flag clicked
forever
    ← Main game logic here
end
```

**Multiple Green Flag Scripts:**
Different sprites can have their own green flag scripts that all run simultaneously:

**Player Sprite:**
```
when green flag clicked
forever
    if <key [right arrow] pressed?> then
        change x by (5)
    end
end
```

**Enemy Sprite:**
```
when green flag clicked
forever
    move (3) steps
    if <touching [edge]?> then
        turn (180) degrees
    end
end
```

### When Key Pressed

**Keyboard Input Events:**
```
when [space] key pressed
    ← Runs when space is pressed
```

**Examples:**

**Jump Control:**
```
when [space] key pressed
if <(on_ground) = (1)> then
    change y by (50)
    set [on_ground] to (0)
end
```

**Shooting:**
```
when [space] key pressed
create clone of [bullet]
play sound [shoot]
```

**Pause Game:**
```
when [p] key pressed
if <(paused) = (0)> then
    set [paused] to (1)
    say [PAUSED] for (999) seconds
else
    set [paused] to (0)
end
```

**Multiple Key Events:**
```
when [right arrow] key pressed
point in direction (90)
move (10) steps

when [left arrow] key pressed
point in direction (-90)
move (10) steps

when [up arrow] key pressed
point in direction (0)
move (10) steps
```

### When Sprite Clicked

**Mouse Interaction Event:**
```
when this sprite clicked
    ← Runs when user clicks this sprite
```

**Examples:**

**Interactive Button:**
```
when this sprite clicked
broadcast [start game]
hide
```

**Collectible Item:**
```
when this sprite clicked
change [score] by (10)
play sound [collect]
hide
```

**Character Selection:**
```
when this sprite clicked
set [player_character] to [knight]
say [Knight selected!] for (2) seconds
```

**Whack-a-Mole Game:**
```
when this sprite clicked
change [score] by (1)
play sound [hit]
hide
wait (pick random (1) to (3)) seconds
show
```

### When Backdrop Changes

**Scene Transition Event:**
```
when backdrop switches to [level2]
    ← Runs when backdrop changes to "level2"
```

**Examples:**

**Level Setup:**
```
when backdrop switches to [forest]
go to x: (-200) y: (0)
set [enemy_count] to (5)
play sound [forest music] until done
```

**Story Progression:**
```
when backdrop switches to [castle]
say [Finally, the castle!] for (3) seconds
wait (2) seconds
switch costume to [knight armor]
```

**Menu System:**
```
when backdrop switches to [main menu]
show
go to x: (0) y: (0)

when backdrop switches to [game screen]
hide
```

### Custom Events with Broadcast

**Creating Your Own Events:**

**Broadcasting (Sending Event):**
```
when green flag clicked
wait (3) seconds
broadcast [start countdown]
```

**Receiving:**
```
when I receive [start countdown]
repeat (3)
    say (timer) for (1) seconds
    change [timer] by (-1)
end
say [GO!] for (1) seconds
```

**Why Use Broadcast?**
- Coordinate multiple sprites
- Organize complex interactions
- Create modular, maintainable code

**Example: Game Start Sequence**

**Director Sprite:**
```
when green flag clicked
say [Get ready!] for (2) seconds
broadcast [spawn enemies]
wait (1) seconds
broadcast [start player]
broadcast [start music]
```

**Enemy Sprite:**
```
when I receive [spawn enemies]
show
forever
    move (3) steps
end
```

**Player Sprite:**
```
when I receive [start player]
go to x: (0) y: (-150)
set [can_move] to (1)
```

### Event-Driven Programming Concept

**Traditional Sequential Programming:**
```
Step 1
Step 2
Step 3
Done
```

**Event-Driven Programming:**
```
Wait for events...
    Event A happens → Run handler A
    Event B happens → Run handler B
    Event A happens again → Run handler A again
Continue waiting forever...
```

**Benefits:**
- More interactive and responsive
- Easier to handle user input
- Natural for games and animations
- Modular code organization

---

## 18. Scratch Programming - Threads

### What Are Threads?

**Threads** are independent sequences of execution running at the same time (parallel execution).

**In Scratch:** Multiple scripts can run simultaneously without waiting for each other.

**Real-World Analogy:** Orchestra
- Violins play their part
- Drums play their part
- Piano plays its part
- All at the same time, coordinated by the conductor

### Multiple Scripts Running Simultaneously

**Example: Game with Multiple Threads**

**Thread 1 - Player Movement:**
```
when green flag clicked
forever
    if <key [right arrow] pressed?> then
        change x by (5)
    end
    if <key [left arrow] pressed?> then
        change x by (-5)
    end
end
```

**Thread 2 - Player Animation:**
```
when green flag clicked
forever
    next costume
    wait (0.1) seconds
end
```

**Thread 3 - Collision Checking:**
```
when green flag clicked
forever
    if <touching [enemy]?> then
        change [lives] by (-1)
        go to x: (0) y: (0)
    end
end
```

**All three run at the same time!**
- Player moves while animating while checking collisions
- No waiting between scripts

### Parallel Execution in Scratch

**Single Sprite, Multiple Scripts:**

**Walking Animation:**
```
when green flag clicked
forever
    if <(moving) = (1)> then
        next costume
        wait (0.1) seconds
    end
end
```

**Gravity System:**
```
when green flag clicked
forever
    if <not <touching [ground]?>> then
        change y by (-5)         ← Falling
    end
    wait (0.03) seconds
end
```

**Both run independently!**

### Coordinating Multiple Sprites

**Example: Synchronized Animation**

**Spotlight Sprite:**
```
when green flag clicked
forever
    glide (1) secs to x: ([x position] of [dancer]) y: (150)
end
```

**Dancer Sprite:**
```
when green flag clicked
forever
    glide (2) secs to x: (-100) y: (0)
    glide (2) secs to x: (100) y: (0)
end
```

**Spotlight follows dancer automatically!**

### Using Broadcast for Coordination

**Example: Boss Battle**

**Player Sprite:**
```
when I receive [boss defeated]
say [Victory!] for (2) seconds
change [score] by (1000)
```

**Boss Sprite:**
```
when green flag clicked
forever
    if <(health) < (1)> then
        broadcast [boss defeated]
        hide
        stop [other scripts in sprite]
    end
end
```

**Music Sprite:**
```
when I receive [boss defeated]
stop all sounds
play sound [victory music]
```

**All sprites respond to the broadcast simultaneously!**

### Real-World Examples (Multitasking)

**Smartphone:**
- Thread 1: Playing music
- Thread 2: Receiving notifications
- Thread 3: Updating weather widget
- Thread 4: Checking for emails
- All happening "at once"

**Video Game:**
- Thread 1: Player input processing
- Thread 2: Enemy AI
- Thread 3: Physics simulation
- Thread 4: Sound effects
- Thread 5: Music playback
- Thread 6: Particle effects

**Human Multitasking:**
- Walking while talking on phone
- Driving while listening to radio
- Cooking while watching timer

### Common Threading Patterns

**Independent Actions:**
```
Sprite 1: Moves left and right
Sprite 2: Moves up and down
Sprite 3: Spins in place
← All happening simultaneously
```

**Producer-Consumer:**
```
Producer thread: Creates clones every 2 seconds
Consumer thread: Clones move and delete themselves
```

**Background Tasks:**
```
Main thread: Player gameplay
Background thread: Timer counts down
Background thread: Enemies spawn periodically
```

### Avoiding Threading Conflicts

**Problem: Race Condition**
```
Thread 1:
change [score] by (1)       ← Reading score at same time
                            
Thread 2:
change [score] by (1)       ← Reading score at same time
```
*Scratch handles this safely automatically!*

**Problem: Conflicting Commands**
```
Thread 1:
forever
    go to x: (0) y: (0)     ← Trying to move sprite here

Thread 2:
forever
    go to x: (100) y: (100) ← And also here!
```
*Result:* Sprite jitters between positions (usually bad!)

**Solution:** Only one thread should control sprite position

---

## 19. Design Principles

### DRY: Don't Repeat Yourself

**Bad Example - Repetitive Code:**
```
when green flag clicked
move (10) steps
turn (90) degrees
move (10) steps
turn (90) degrees
move (10) steps
turn (90) degrees
move (10) steps
turn (90) degrees
```

**Good Example - Using Loop:**
```
when green flag clicked
repeat (4)
    move (10) steps
    turn (90) degrees
end
```

**Benefits:**
- Less code to write
- Easier to modify (change once, affects all)
- Fewer bugs
- More readable

**Custom Block Example:**

**Before (Repetitive):**
```
← Reset code in 5 different places
go to x: (0) y: (0)
set [score] to (0)
set [lives] to (3)
show
```

**After (DRY with Custom Block):**
```
define reset game
    go to x: (0) y: (0)
    set [score] to (0)
    set [lives] to (3)
    show

← Now just use "reset game" block everywhere!
```

### Code Organization and Readability

**Messy Code (Hard to Understand):**
```
when green flag clicked
forever
if<key[space]pressed?>then
if<(y)<(50)>then
changeyby(20)
endif
endif
if<touching[enemy]?>then
changexby(-10)
change[score]by(-1)
endif
end
```

**Organized Code (Easy to Understand):**
```
when green flag clicked
forever
    ← Handle jumping
    if <key [space] pressed?> then
        if <(y) < (50)> then     ← Only if below jump height
            change y by (20)
        end
    end
    
    ← Handle enemy collision
    if <touching [enemy]?> then
        change x by (-10)         ← Knockback
        change [score] by (-1)    ← Penalty
    end
end
```

**Organization Tips:**
- Group related code together
- Use comments (via say blocks during testing)
- One responsibility per script when possible
- Name variables descriptively: `player_speed` not `s`

### Planning Before Coding

**The Planning Process:**

**1. Define the Goal:**
- "Create a catching game where items fall and player moves left/right to catch them"

**2. Break Down Features:**
- Player movement (keyboard)
- Falling objects (gravity)
- Collision detection
- Score system
- Game over condition

**3. Sketch/Pseudocode:**
```
When game starts:
    Set score to 0
    Show player at bottom
    
Forever:
    If left arrow: move player left
    If right arrow: move player right
    
Falling object:
Forever:
        Fall down
    If touching player: add score, reset position
    If touching bottom: game over
```

**4. Build Incrementally** (see next section)

**5. Test Each Feature**

**6. Refine and Polish**

### Iterative Development and Testing

**Don't try to build everything at once!**

**Iteration 1: Basic Movement**
```
when green flag clicked
forever
    if <key [right arrow] pressed?> then
        change x by (5)
    end
end
```
**Test:** Does player move right? ✓

**Iteration 2: Add Left Movement**
```
when green flag clicked
forever
    if <key [right arrow] pressed?> then
        change x by (5)
    end
    if <key [left arrow] pressed?> then
        change x by (-5)
    end
end
```
**Test:** Both directions work? ✓

**Iteration 3: Add Boundaries**
```
when green flag clicked
forever
    if <key [right arrow] pressed?> then
        if <(x position) < (220)> then
            change x by (5)
        end
    end
    if <key [left arrow] pressed?> then
        if <(x position) > (-220)> then
            change x by (-5)
        end
    end
end
```
**Test:** Player stops at edges? ✓

**Continue adding features one at a time!**

### Code Review Checklist

Before submitting/sharing your project:

**✅ Functionality:**
- Does it work as intended?
- Tested all features?
- No game-breaking bugs?

**✅ Code Quality:**
- Used loops instead of repetition?
- Created custom blocks for repeated code?
- Variables named clearly?

**✅ User Experience:**
- Clear instructions?
- Appropriate difficulty?
- Good visual/audio feedback?

**✅ Efficiency:**
- No unnecessary forever loops?
- Includes wait blocks to prevent lag?
- Clones deleted when no longer needed?

---

## 20. Problem Set 0 Requirements

### Minimum Requirements Checklist

**Your project MUST have:**

✅ **At least 2 sprites**
- One cannot be the default Scratch cat (unless significantly modified)
- Can have more than 2!

✅ **At least 3 scripts total**
- Scripts = stacks of blocks starting with event blocks
- Can be spread across sprites or on one sprite

✅ **At least 1 conditional (if-then or if-then-else)**
- Decision-making logic
- Example: if touching edge, if key pressed

✅ **At least 1 loop**
- Forever, repeat, or repeat until
- Code that executes multiple times

✅ **At least 1 variable**
- Stores changing data
- Example: score, lives, level

✅ **At least 1 sound**
- Play sound, start sound
- Can be built-in or recorded

**Important:** Project should be **more complex** than lecture examples!

### Project Idea Categories

**Games:**
- Maze navigator
- Catching game
- Pong/paddle game
- Simple platformer
- Whack-a-mole
- Memory matching
- Quiz game

**Interactive Stories:**
- Choose-your-own-adventure
- Animated tale with user choices
- Character dialogue system
- Branching narrative

**Animations:**
- Music video
- Short film
- Dance sequence
- Nature scene with interactions

**Interactive Art:**
- Drawing program
- Music maker
- Kaleidoscope
- Particle effects

**Simulations:**
- Aquarium
- Space scene
- Weather simulation
- Traffic system

### Sample Project Breakdown

**Project Idea: Simple Catching Game**

**Requirements Check:**
- ✅ 2 sprites: Player basket, Falling apple
- ✅ 3 scripts: Player movement, apple falling, score display
- ✅ 1 conditional: if touching player
- ✅ 1 loop: forever (for falling and checking)
- ✅ 1 variable: score
- ✅ 1 sound: catch sound

**Exceeding Minimums (Better Grade):**
- Multiple falling objects
- Lives system
- Increasing difficulty
- Game over screen
- Background music
- Visual effects

### Tips for Success

**Start Simple:**
- Get basic version working first
- Add features incrementally
- Test frequently

**Add Complexity Gradually:**
- Basic → Add scoring → Add lives → Add levels
- Each addition makes project stronger

**Polish Matters:**
- Instructions for user
- Visual feedback (sounds, effects)
- Smooth gameplay
- No obvious bugs

**Be Creative:**
- Unique twist on simple concept > poorly executed complex idea
- Personal interests make better projects
- Don't just copy lecture examples

---

## 21. Common Scratch Patterns

### Player Movement Controls

**Arrow Key Movement (4 directions):**
```
when green flag clicked
forever
    if <key [right arrow] pressed?> then
        change x by (5)
    end
    if <key [left arrow] pressed?> then
        change x by (-5)
    end
    if <key [up arrow] pressed?> then
        change y by (5)
    end
    if <key [down arrow] pressed?> then
        change y by (-5)
    end
end
```

**Smooth Movement with Variable:**
```
when green flag clicked
set [speed] to (5)
forever
    if <key [right arrow] pressed?> then
        change x by (speed)
    end
    ← etc for other directions
end
```

**Point and Move (Rotation-based):**
```
when green flag clicked
forever
    if <key [left arrow] pressed?> then
        turn (-5) degrees
    end
    if <key [right arrow] pressed?> then
        turn (5) degrees
    end
    if <key [up arrow] pressed?> then
        move (5) steps
    end
end
```

### Collision Detection Patterns

**Wall Collision (Stop Movement):**
```
when green flag clicked
forever
    if <key [right arrow] pressed?> then
        change x by (5)
        if <touching [wall]?> then
            change x by (-5)      ← Undo movement
        end
    end
end
```

**Edge Bounce:**
```
when green flag clicked
forever
    move (5) steps
    if on edge, bounce
end
```

**Enemy Collision with Knockback:**
```
when green flag clicked
forever
    if <touching [enemy]?> then
        change [lives] by (-1)
        change x by (-20)         ← Knockback
        repeat (10)               ← Brief invincibility flash
            change [ghost] effect by (25)
            wait (0.1) seconds
            change [ghost] effect by (-25)
            wait (0.1) seconds
        end
    end
end
```

**Collectible Item Detection:**
```
when green flag clicked
forever
    if <touching [coin]?> then
        change [score] by (10)
        play sound [collect]
        broadcast [coin collected]  ← Tell coin to hide
    end
end
```

### Score Counting System

**Basic Score Increment:**
```
when green flag clicked
set [score] to (0)              ← Initialize

when I receive [collect coin]
change [score] by (10)          ← Increment
```

**Score with Combo System:**
```
when I receive [hit enemy]
change [combo] by (1)
set [points] to ((combo) * (10))
change [score] by (points)
say (join [+ ] (points)) for (1) seconds
```

**High Score Tracking:**
```
when green flag clicked
if <(score) > (high_score)> then
    set [high_score] to (score)
    say [New High Score!] for (2) seconds
end
```

### Lives/Health System

**Basic Lives:**
```
when green flag clicked
set [lives] to (3)

when I receive [take damage]
change [lives] by (-1)
if <(lives) < (1)> then
    broadcast [game over]
end
```

**Health Bar (0-100):**
```
when green flag clicked
set [health] to (100)

when I receive [take damage]
change [health] by (-10)
if <(health) < (1)> then
    broadcast [player died]
end

when I receive [collect health pack]
change [health] by (25)
if <(health) > (100)> then
    set [health] to (100)       ← Cap at maximum
end
```

**Lives Display with Sprites:**
```
← Heart sprite clones for each life
when I start as a clone
show
set x to ((lives) * (30))       ← Position based on life number

when I receive [lose life]
if <(clone_id) = (lives)> then  ← If this is the last heart
    delete this clone
end
```

### Win/Lose Conditions

**Win Condition (Reach Goal):**
```
when green flag clicked
forever
    if <touching [goal]?> then
        say [You Win!] for (2) seconds
        broadcast [victory]
        stop [all]
    end
end
```

**Lose Condition (No Lives):**
```
when green flag clicked
forever
    if <(lives) < (1)> then
        say [Game Over!] for (2) seconds
        broadcast [game over]
        stop [all]
    end
end
```

**Time-Based Win/Lose:**
```
when green flag clicked
set [time] to (60)
repeat until <(time) < (1)>
    wait (1) seconds
    change [time] by (-1)
end

if <(score) > (50)> then
    say [You Win!] for (2) seconds
else
    say [Not enough points!] for (2) seconds
end
```

**Collection Goal:**
```
when green flag clicked
set [coins_collected] to (0)
set [total_coins] to (10)

forever
    if <(coins_collected) = (total_coins)> then
        say [All coins collected!] for (2) seconds
        broadcast [level complete]
    end
end
```

### Animation with Costume Changes

**Walking Animation:**
```
when green flag clicked
forever
    if <<key [right arrow] pressed?> or <key [left arrow] pressed?>> then
        next costume
        wait (0.1) seconds
    else
        switch costume to [standing]
    end
end
```

**Idle Animation Loop:**
```
when green flag clicked
forever
    switch costume to [idle1]
    wait (0.5) seconds
    switch costume to [idle2]
    wait (0.5) seconds
end
```

**Direction-Based Costumes:**
```
when green flag clicked
forever
    if <key [right arrow] pressed?> then
        switch costume to [walk right]
        change x by (5)
    end
    if <key [left arrow] pressed?> then
        switch costume to [walk left]
        change x by (-5)
    end
end
```

---

## 22. Debugging and Testing

### Common Scratch Mistakes and Fixes

**Mistake 1: Sprite Disappears**
```
Problem: Sprite goes off screen and can't find it

Solution:
when green flag clicked
go to x: (0) y: (0)            ← Always start at known position
```

**Mistake 2: Infinite Loop Freezing**
```
Problem:
forever
    change [score] by (1)       ← No wait block!
end
← Runs millions of times per second, causes lag

Solution:
forever
    change [score] by (1)
    wait (0.03) seconds         ← Add wait
end
```

**Mistake 3: Collision Not Detecting**
```
Problem: if <touching [enemy]?> not working

Possible causes:
- Sprites on different layers
- Collision checking in wrong sprite
- Sprite names don't match exactly

Solution:
- Check spelling of sprite names
- Put collision code in BOTH sprites
- Make sure sprites are visible (not hidden)
```

**Mistake 4: Variable Not Updating**
```
Problem:
set [score] to (10)             ← Later...
change [score] by (1)           ← Shows 11, then...
set [score] to (10)             ← Back to 10!

Solution: Don't keep resetting! Only set to initial value once at start
```

**Mistake 5: Broadcast Not Received**
```
Problem: Broadcasting [start game] but nothing happens

Checks:
- Spelling must match EXACTLY: [start game] ≠ [Start Game]
- Receiving sprite must be listening: "when I receive [start game]"
- Script might be under wrong sprite
```

**Mistake 6: Event Not Triggering**
```
Problem:
when [space] key pressed
    ← Code here never runs

Possible issues:
- Game running but sprite is hidden
- Another script already handling that key
- Event block not at top of stack

Solution: Only event blocks can be at the top of scripts
```

### Testing Each Feature Incrementally

**Good Testing Workflow:**

**Step 1: Test Basic Movement**
```
when green flag clicked
forever
    if <key [right arrow] pressed?> then
        change x by (5)
    end
end
```
**Test:** Press right arrow. Does sprite move? ✓

**Step 2: Add and Test Left**
```
← Add left arrow code
```
**Test:** Both directions work independently? ✓

**Step 3: Add and Test Boundaries**
```
← Add edge detection
```
**Test:** Sprite stops at edges? ✓

**Step 4: Add and Test Collision**
```
← Add wall collision
```
**Test:** Sprite can't go through walls? ✓

**Continue one feature at a time!**

**Bad Testing Approach (Don't Do This):**
- Build entire game
- Click green flag
- Nothing works
- No idea where problem is
- Give up in frustration

### Using Say Blocks for Debugging

**Debugging Variable Values:**
```
when green flag clicked
forever
    say (join [Score: ] (score))  ← Shows current score
    wait (0.5) seconds
end
```

**Debugging Conditionals:**
```
if <touching [enemy]?> then
    say [Collision detected!] for (1) seconds  ← Confirms condition is true
    change [lives] by (-1)
end
```

**Debugging Position:**
```
when green flag clicked
forever
    say (join (join [X: ] (x position)) (join [ Y: ] (y position)))
    wait (0.5) seconds
end
```

**Debugging Broadcasts:**
```
when I receive [game over]
say [Game over received!] for (1) seconds  ← Confirms broadcast works
← Rest of game over code
```

**Remove Debug Code Before Submitting!**

### Checking Variable Values During Execution

**Variable Display Options:**

**Normal Display:**
- Check box next to variable name
- Shows: `score: 45`

**Large Display:**
- Right-click variable on stage
- Select "large readout"
- Shows just the number in big text

**Slider:**
- Right-click variable
- Select "slider"
- Allows manual adjustment for testing

**Manual Testing Technique:**
```
1. Show important variables (score, lives, level)
2. Run game
3. Watch variables change in real-time
4. Pause and inspect when something goes wrong
```

### Common Logic Errors

**Off-By-One Error:**
```
Wrong:
repeat (10)
    ← Runs 10 times, but array has indices 0-9
    set [value] to (item (counter) of [list])
end

Correct:
set [counter] to (1)
repeat (10)
    set [value] to (item (counter) of [list])
    change [counter] by (1)
end
```

**Wrong Comparison Operator:**
```
Wrong:
if <(lives) > (0)> then        ← Still true when lives = 1
    say [Game Over]            ← Game over too early!
end

Correct:
if <(lives) < (1)> then        ← True only when lives = 0
    say [Game Over]
end
```

**Missing Reset:**
```
Wrong:
when green flag clicked
← Doesn't reset score from last game!
forever
    ← Game code
end

Correct:
when green flag clicked
set [score] to (0)             ← Always reset!
set [lives] to (3)
forever
    ← Game code
end
```

### Debugging Checklist

When something doesn't work:

✅ **Are all sprites visible?** (Not hidden accidentally)
✅ **Are variable names spelled correctly?**
✅ **Do broadcast names match exactly?**
✅ **Are there wait blocks in forever loops?**
✅ **Is the code under the right sprite?**
✅ **Are costumes/sounds loaded properly?**
✅ **Did you reset variables at game start?**
✅ **Are coordinates reasonable?** (Stage is -240 to 240 x, -180 to 180 y)
✅ **Is the logic correct?** (Right comparison operators, etc.)

---

## 23. Transition to Week 1

### How Scratch Concepts Translate to C Programming

**The good news:** Everything you learned in Scratch applies to C!

**Scratch → C Translations:**

**Variables:**
```
Scratch: set [score] to (0)
C:       int score = 0;
```

**Conditionals:**
```
Scratch: if <(score) > (10)> then
C:       if (score > 10) {
```

**Loops:**
```
Scratch: repeat (10)
C:       for (int i = 0; i < 10; i++) {

Scratch: forever
C:       while (true) {

Scratch: repeat until <condition>
C:       while (!condition) {
```

**Functions:**
```
Scratch: define jump
C:       void jump() {
```

**Boolean Expressions:**
```
Scratch: <(x) > (10)>
C:       x > 10

Scratch: <<condition1> and <condition2>>
C:       (condition1 && condition2)
```

### Why Visual Blocks Are Easier to Start With

**Benefits of Scratch:**

**No Syntax Errors:**
- Can't forget semicolons (don't exist!)
- Can't misspell keywords (drag-and-drop)
- Can't have mismatched brackets
- Blocks physically fit together or they don't

**Immediate Visual Feedback:**
- See sprites move instantly
- Hear sounds play
- Watch variables change
- Visual debugging is natural

**Focus on Logic:**
- Spend mental energy on WHAT to do
- Not HOW to type it correctly
- Learn problem-solving first
- Syntax comes later

**Lower Frustration:**
- Beginners spend 80% of time on syntax errors in text languages
- Scratch eliminates that barrier
- Build confidence before adding complexity

### What Stays the Same (Logic & Algorithms)

**These Concepts Are Universal:**

**Problem-Solving Approach:**
- Break problems into smaller pieces ← Same!
- Think algorithmically ← Same!
- Test incrementally ← Same!

**Programming Logic:**
- If-then-else decisions ← Same logic!
- Loops for repetition ← Same concept!
- Variables for storage ← Same purpose!
- Functions for organization ← Same idea!

**Computational Thinking:**
- Pattern recognition ← Same!
- Abstraction ← Same!
- Input → Process → Output ← Same!

**Example: Same Algorithm, Different Languages**

**Scratch (Counting to 10):**
```
set [counter] to (1)
repeat until <(counter) > (10)>
    say (counter) for (1) seconds
    change [counter] by (1)
end
```

**C (Counting to 10):**
```c
int counter = 1;
while (counter <= 10) {
    printf("%i\n", counter);
    counter++;
}
```

**Same logic, different appearance!**

### What Changes (Syntax & Text-Based Coding)

**New Challenges in C:**

**Syntax Matters:**
- Semicolons at the end of statements
- Curly braces for blocks
- Parentheses for conditions
- Spelling must be exact

**Data Types:**
```
int score = 0;              ← Must declare type
float average = 85.5;       ← Different types for different data
char grade = 'A';           ← Single character
string name = "Alice";      ← Text
```

**Text-Based = More Typing:**
- No drag-and-drop
- Must remember function names
- Must type everything exactly

**Compilation:**
- Scratch runs immediately
- C must be compiled first: `make program`
- Compiler finds errors before running

**No Visual Stage:**
- Output is text in terminal
- No sprites moving around (unless you make graphics)
- Different kind of feedback

### Preparing for Week 1

**You're Already Prepared!**

You now understand:
✅ Variables and data storage
✅ Conditional logic (if/else)
✅ Loops (while, for)
✅ Functions
✅ Boolean expressions
✅ Algorithm design
✅ Debugging mindset
✅ Incremental development

**What to Expect:**
- Learning C syntax (like learning grammar for a language you already speak)
- Terminal/command line interface
- Text-based input/output
- More precision required
- Same problem-solving skills!

**Tips for Success:**
- Don't panic about syntax errors (everyone gets them)
- Focus on the logic (you already know this!)
- Compare C code to Scratch concepts
- Test frequently (same as Scratch)
- Ask for help early
- Remember: syntax is just notation for ideas you already understand

**Mindset Shift:**
```
Scratch: "I'm learning to program"
C:       "I'm learning a new way to express what I already know"
```

---

## Practice Challenges

### Challenge 1: Number Systems
Convert these decimal numbers to binary:
- 25 = ?
- 64 = ?
- 100 = ?

<details>
<summary>Answers</summary>

- 25 = 11001 (16+8+1)
- 64 = 1000000 (just 64)
- 100 = 1100100 (64+32+4)
</details>

### Challenge 2: Algorithm Efficiency
Which is faster for finding a name in a sorted list of 1000 names?
A) Linear search
B) Binary search

<details>
<summary>Answer</summary>

B) Binary search - approximately 10 checks vs. up to 1000 checks for linear search
</details>

### Challenge 3: Debugging Logic
What's wrong with this pseudocode?
```
set score to 0
forever:
    if score > 10:
        say "You win!"
        stop all
```

<details>
<summary>Answer</summary>

Score never increases! Need to add: "change score by 1" inside the loop, or connect score to actual game actions.
</details>

### Challenge 4: Design Pattern
Design a simple jumping mechanic using pseudocode. Include:
- Jumping only when on ground
- Gravity bringing player back down

<details>
<summary>Sample Solution</summary>

```
when space key pressed:
    if on_ground = 1:
        set on_ground to 0
        set jump_velocity to 20
        
forever:
    change y by jump_velocity
    change jump_velocity by -2  (gravity)
    if touching ground:
        set on_ground to 1
        set jump_velocity to 0
```
</details>

---

## Quick Reference Guide

### Scratch Block Categories

**Motion:** move, turn, go to, glide, point in direction
**Looks:** say, show/hide, switch costume, change size
**Sound:** play sound, start sound, change volume
**Events:** when green flag, when key pressed, when sprite clicked, broadcast
**Control:** if-then, if-then-else, repeat, forever, repeat until, wait
**Sensing:** touching?, key pressed?, mouse position, ask and wait
**Operators:** +, -, *, /, <, >, =, and, or, not, join, random
**Variables:** set, change, show, hide
**My Blocks:** Custom function definitions

### Key Vocabulary

- **Algorithm:** Step-by-step instructions to solve a problem
- **Argument:** Input value passed to a function
- **Abstraction:** Hiding complexity, showing only essentials
- **Boolean:** True or false value
- **Bug:** Error in code
- **Conditional:** If-then decision making
- **Function:** Reusable block of code
- **Loop:** Repeating code multiple times
- **Variable:** Named storage for changing values
- **Event:** Trigger that starts code execution
- **Thread:** Independent script running simultaneously

### Problem Set 0 Checklist

Before submitting:
- [ ] At least 2 sprites (one not default cat)
- [ ] At least 3 scripts
- [ ] At least 1 conditional
- [ ] At least 1 loop
- [ ] At least 1 variable
- [ ] At least 1 sound
- [ ] More complex than lecture examples
- [ ] Tested thoroughly
- [ ] Instructions clear for user
- [ ] No game-breaking bugs

---