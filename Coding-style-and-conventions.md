Webcamoid follow more or less Qt [coding style](https://wiki.qt.io/Qt_Coding_Style) and [conventions](https://wiki.qt.io/Coding_Conventions) with some extra rules.

### Indentation

- Use spaces for indenting.
- Use 4 spaces per indent.

### Line breaks

- Keep your code lines bellow the 80 characters limit, and define the logic in small chunks when possible.
- When splitting long lines, commas goes at the end of the line, operators goes at beginning of the line.

```
void doSomething(int a,
                 int b,
                 int c,
                 int d,
                 int e,
                 int f);

int sum = a
        + b
        + c
        + d
        + e
        + f;
```

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

// It's clear here that 'x' and 'y' are defining points coordinates.
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

- Use parentheses to group expressions.

```
// WRONG!
if (a && b || c && d)

// OK
if ((a && b) || (c && d))
```
- One space between opening parenthesis and operator or keyword, no space after.
- One space between closing parenthesis and next operator or keyword, no space before.
- Neighbor opening or closing parentheses goes together.

```
// WRONG!
if( ( a < b )&&( c > d ) )

// OK
if ((a < b) && (c > d))
```

- No spaces after or before in parentheses when declaring or defining a function or method.

```
// WRONG!
void doSomething ( int a );

// OK
void doSomething(int a);
```

### Switch statements

- 'switch' and 'case' statements, goes in the same column.

### Jump statements (break, continue, return, and goto)

- Do not put 'else' after jump statements

```
// Wrong
if (thisOrThat)
    return;
else
    somethingElse();

// Correct
if (thisOrThat)
    return;

somethingElse();
```

### Maps and arrays

- When creating an array or map, and it's initializing values doesn't fit under the line limit, the opening brace goes in the same line of the declaration, the first value goes indented in the next line, followed by next values, and the closing brace in the same column of the declaration.

```
QStringList a = {
    "foo",
    "bar",
    "baz"
};

QVariantMap a = {
    {"foo", 0},
    {"bar", 1},
    {"baz", 2}
};
```

### Classes and structs

- Use descriptive names for classes and structs.
- Use CamelCase for classes and structs names, with first letter upper case.
- When initializing values in constructors, if there are more than one initialization, put the initialization code indented bellow the constructor.

```
MyClass::MyClass(int a, int b, int c):
    m_a(a),
    m_b(b),
    m_c(c)
{
    // Body of the constructor.
}
```

### Blocks of code, loops and conditionals

A block of code is code belonging to a loop, conditional or any code surrounded by curly braces and defined in multiple lines, for example a 'for' or 'while' loop, an if-else if-else, etc..

- Put a while line before and after a code block.

```
// WRONG!
int sum = 0;
QList<int> values = {1, 3, 5, 7, 9};
for (auto &value: values)
    sum += value;
qDebug() << "sum =" << sum;

// OK
int sum = 0;
QList<int> values = {1, 3, 5, 7, 9};

for (auto &value: values)
    sum += value;

qDebug() << "sum =" << sum;
```

### Functions and methods

- Commas in functions and methods parameters, doesn't have spaces before, and have one space after.

```
// WRONG!
doDomething(a,b,c);

// OK
doDomething(a, b, c);
```

### Including headers

- Add one blank line between copyright header and include lines, and one blank line between include lines and code.
- Library headers must be included in the following order: standard library headers, system libraries headers, Qt headers, Webcamoid headers, 3rd party libraries headers, local headers.
- Local headers must be surrounded by "" and there must be one blank between local headers and libraries headers.

### Casting

- Avoid C type casting, and use C++ style.

```
// WRONG!
int b = (int) b;
auto dataOfTypeB = (char *) dataOfTypeA;

// OK
int b = int(b);
auto dataOfTypeB = reinterpret_cast<char *>(dataOfTypeA);
```

### C++ features

- Don't use C++ exceptions.
- Feel free to use any new C++ feature supported by all compilers supported by the project, if it make the code easier to understand and maintain.
