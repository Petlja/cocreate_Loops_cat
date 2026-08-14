# Conditions and loops

To successfully master the material about encryption, it is necessary to know the basic facts about working with conditions and loops. Conditions and loops are the basic mechanisms that allow computer programs to make decisions and repeat certain actions. Thanks to conditions, a program can react differently depending on the data it receives, while loops enable efficient repetition of the same steps multiple times. These concepts are crucial in encryption, as algorithms for data protection are based on a series of rules, checks, and repeating procedures that ensure information security.

Let's recall some basics! If this area is still unclear to you, go through the lesson on Petlja dedicated exactly to this topic.

Link to Petlja's lesson on loops is [here](https://petlja.org/en/biblioteka/r/lekcije/python-za-svakog/01_karel_eng_02_for)

```{learnmorenote} For teachers

Link to Petlja's lesson on loops: https://petlja.org/en/biblioteka/r/lekcije/python-za-svakog/01_karel_eng_02_for
```

## Conditions

In most modern programming languages, conditional statements are used for decision-making and controlling program flow.

* if
* if-else
* switch-case

Although syntax differs between languages, the basic logic is the same.

### The `if` statement

The `if` statement executes a block of code only if a given condition is true.

```text
if condition then
    statement(s)
```

For example, in C, C++, C#, and Java, if you want to check whether `x` is greater than `0`, the conditional statement can be written like this:

```csharp
int x = 5;
if (x > 0) {
    // ...
}
```

### The `if-else` statement

The `if-else` statement executes one block of code if the condition is true, and another block if it is false.

```text
if condition then
    statement(s)
else
    statement(s)
```

For example, in C, C++, C#, and Java, if you want to check whether `x` is greater than `0` or not, the conditional statement can be written like this:

```csharp
int x = 5;
if (x > 0) {
    // ...
} else {
    // ...
}
```

### The `switch-case` statement

The `switch-case` statement is useful when one same variable is compared with multiple possible values. This construct simplifies code where multiple if-else statements would otherwise be needed.

```text
switch expression do
    case value1:
        statement(s)
    case value2:
        statement(s)
    ...
    default:
        statement(s)
```

For example, in C, C++, C#, and Java, if you want to determine the name of a day based on its ordinal number in the week, the conditional statement can be written like this:

```csharp
int day = 3;
string name = "";
switch (day) {
    case 1:
        name = "Monday";
        break;
    case 2:
        name = "Tuesday";
        break;
    case 3:
        name = "Wednesday";
        break;
    // ...
    default:
        name = "";
        break;
}
```

### Nesting conditions

Conditional statements can be placed inside one another – this is called **nesting**. Nested conditions are often used when we need to check multiple dependent conditions.

## Loops

In most modern programming languages, loops are usually implemented using one of the following constructs:

* `for`,
* `while` (or `while-do`),
* `do-while` (or `repeat-until`),
* `foreach` (or `for-each`).

Although syntax differs between languages, the basic logic is the same.

### The `for` loop

The `for` loop is used when the number of iterations is finite and known in advance.

```text
for variable ← start to end do
    statement(s)
```

For example, in C, C++, C#, and Java, a `for` loop to iterate through numbers from 0 to 9 can be written like this:

```csharp
for (int i = 0; i <= 9; i++) {
    // ...
}
```

### The `while` loop

The `while` loop (or `while-do`) is used when the number of iterations is not known in advance. The condition is checked before each iteration.

```text
while condition do
    statement(s)
```

For example, in C, C++, C#, and Java, a `while` loop to iterate through numbers from 0 to 9 can be written like this:

```csharp
int i = 0;
while (i <= 9) {
    // ...
    i++;
}
```

### The `do-while` loop

The `do-while` loop (or `repeat-until`) also supports an unknown number of iterations, but the condition is checked after each iteration.

```text
repeat
    statement(s)
until condition
```

For example, in C, C++, C#, and Java, a `do-while` loop to iterate through numbers from 0 to 9 can be written like this:

```csharp
int i = 0;
do {
    // ...
    i++;
} while (i <= 9);
```

### The `foreach` loop

The `foreach` loop (or `for-each`) is used to iterate through all elements in a collection or array. This loop simplifies working with collections.

```text
for-each element in collection do
    statement(s)
```

For example, a `for-each` loop to iterate through an array `nums` can be written in C++ like this:

```cpp
int nums[] = { 0, 1, 2, 3, 4, 5, 6, 7, 8, 9 };
for (int i : nums) {
    // ...
}
```

...or in C# like this...

```csharp
int[] nums = { 0, 1, 2, 3, 4, 5, 6, 7, 8, 9 };
foreach (int i in nums) {
    // ...  
}
```

...or in Java like this:

```java
int[] nums = { 0, 1, 2, 3, 4, 5, 6, 7, 8, 9 };
for (int i : nums) {
    // ...   
}
```

### Nesting loops

Loops can also be nested, meaning that one loop is placed inside another. This is common when working with multi-dimensional data, such as traversing rows and columns in a matrix or iterating over a grid in a game. Furthermore, loops and conditions can be freely combined — for example, a loop may contain an `if` statement to process only certain elements, or an `if` statement may contain a loop to perform repeated actions when a condition is true. This ability to mix and nest loops and conditions allows for the creation of complex algorithms while keeping the underlying logic structured.


Different forms of loops will be needed for different forms of encryption you will learn about on the following pages!
