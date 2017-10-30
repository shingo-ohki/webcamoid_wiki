**I progress**

Webcamoid follow more or less Qt [coding style](https://wiki.qt.io/Qt_Coding_Style) and [conventions](https://wiki.qt.io/Coding_Conventions) with some extra rules.

# Coding Style

### Indentation

- Use spaces for indenting.
- Use 4 spaces per indent.

### Declaring variables

- Declare one variable per line.
- Use descriptive names for variables.
- Use camelCase for variable names, with first letter lower case.
- Use short names only for counters, temporal variables, and where the context is clear.

```
// 'i' is a counter.
for (int i = 0; i < array.size(); i += 2) {
    auto tmp = array[i];     // 'tmp' is a temporal variable.
    array[i] = array[i + 1];
    array[i + 1] = tmp;
}

// It's clear here that 'x' and 'y' are defining points.
for (int y = 0; y < image.height(); y++)
    for (int x = 0; x < image.width(); x++)
        image.setPixel(x, y, qRgb(255, 0, 0));
```

- Declare and initialize variables near to usage.

```
// WRONG!
int i;

// Many lines of unrelated code comes here.

for (i = 0; i < array.size(); i += 2) {
    // Use 'i'
}


// OK.
for (int i = 0; i < array.size(); i += 2) {
    // Use 'i'
}
```

### Whitespace

- Don't use white space between '*' or '&' and a variable name.

```
// WRONG!
int x = 0;
int * y = & x;

// OK
int x = 0;
int *y = &x;
```
- Surround '*' and '&' with one white space if it is surrounded with keywords.

```
// WRONG!
const char*const str = "";

// OK
const char * const str = "";
```

- One space before and after assignment.

```
// WRONG!
int a=0;

// OK
int a = 0;
```

- The exception to previous rule are default values in functions and methods parameters. No space before and after assignment.

```
// WRONG!
int doSomething(int x, const char *y = NULL);

// OK
int doSomething(int x, const char *y=NULL);
```

- Surround binary and math operators with spaces.

```
// WRONG!
int c = a+b;
bool c = a||b;

// OK
int c = a + b;
bool c = a || b;
```

- One statement per line.

```
// WRONG!
auto tmp = array[i]; array[i] = array[i + 1]; array[i + 1] = tmp;

// OK
auto tmp = array[i];
array[i] = array[i + 1];
array[i + 1] = tmp;
```

### Braces

- Opening curly brace goes in the same line of the statement, the closing brace goes in the same column of it's corresponding statement.
- for if-else if-else block codes, the closing curly brace goes in the same line of the next statement.
- One space before the opening curly brace and it's statement.
- One space after the closing curly brace and the next statement.

```
// WRONG!
if (a < b)
{
}
else if (a > b)
{
}
else
{
}

// OK
if (a < b) {
} else if (a > b) {
} else {
}
```

- In functions, methods, classes and structs, the opening and curly braces goes in the same column of the statement.

```
// WRONG!
class MyClass {
};

void doSomething() {
}

// OK
class MyClass
{
};

void doSomething() 
{
}
```

- Use braces if the body of a code block is empty.
- Don't use braces if a code block has only one statement.
- The exception to the previous rule is in if-else if-else code block, when at least one of the statements has more than one child statement.

```
// WRONG!
for (i = 0; i < 10; i++); // The body is empty.

if (a > 0) {
    doSomething(); // Only one statement.
}

// 'else' has curly braces, 'if' has not. Not symmetric.
if (a < 0)
    doSomething();
else {
    doSomethingElse();
    doSomethingMore();
}


// OK
for (i = 0; i < 10; i++) {
}

if (a > 0)
    doSomething(); // Only one statement.

if (a < 0) {
    doSomething();
} else {
    doSomethingElse();
    doSomethingMore();
}
```

- Use curly braces if the statement is divided into multiple lines, even when the statement body has only one child statement.

```
// WRONG!
if (a > 0
    && isValid()
    && ok)
    doSomething();

// OK
if (a > 0
    && isValid()
    && ok) {
    doSomething();
}
```

### Parentheses

### Jump statements (break, continue, return, and goto)

### Line breaks

### Maps and lists

### Classes and structs

### Blocks of code, loops and conditionals

### Functions and methods

# Coding Conventions

### C++ features

### Including headers

### Casting

### Compiler/Platform specific issues

### Aesthetics

### Things to avoid

### Conventions for public header files

### Conventions for C++11 usage

### auto Keyword
