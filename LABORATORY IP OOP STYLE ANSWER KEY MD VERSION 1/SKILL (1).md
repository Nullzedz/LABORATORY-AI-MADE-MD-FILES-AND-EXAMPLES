---
name: cpp-oop-solver
description: "Use this skill whenever you are given a C++ OOP programming problem — from a PDF, image, or text — and must produce working, compilable code. Always outputs three files that mirror the PointADT pattern: a header (.h), an implementation file (Imp.cpp), and a client/main file (main.cpp). Covers class design, inheritance, encapsulation, constructors/destructors, method implementation, and composition. Triggers: any C++ OOP problem, lab sheet, assignment, or exam question asking you to design and implement a class or class hierarchy."
license: Proprietary. LICENSE.txt has complete terms
---

# C++ OOP Problem Solver

## Overview

This skill solves C++ Object-Oriented Programming problems by always producing
**three files** in the PointADT format:

| File | Role | Naming Convention |
|------|------|-------------------|
| `ClassName.h` | Header — class declaration only | `point.h`, `line.h` |
| `ClassNameImp.cpp` | Implementation — method bodies only | `pointImp.cpp`, `lineImp.cpp` |
| `main.cpp` | Client — tests every method declared in the header | `main.cpp` |

Never collapse all code into one file unless the problem explicitly says so.

---

## Step 1 — Read and Analyse the Problem

Before writing a single line of code, extract these facts from the problem statement:

```
1. Class name(s)
2. Data members (name + type + access: private/protected/public)
3. Every method signature (return type, name, parameters)
4. Constructors required (default, parameterised, copy)
5. Destructor needed?
6. Inheritance? (base class → derived class)
7. Composition? (class holds another class as a member)
8. Any special logic (formulas, conditions, output format)
```

Write this list out mentally before touching any file.

---

## Step 2 — Write the Header File (`ClassName.h`)

### Rules
- Always wrap in an include guard using the class name in ALL_CAPS.
- List `public:` members first (constructors, destructor, setters, getters, other methods).
- List `private:` (or `protected:` for base classes) data members last.
- `#include` any dependency headers at the top (e.g. `#include "point.h"` inside `line.h`).
- **No method bodies here** — declarations only.

### Template

```cpp
#ifndef CLASSNAME_H_INCLUDED
#define CLASSNAME_H_INCLUDED

// Include dependencies if needed
// #include "OtherClass.h"

class ClassName
{
public:
    ClassName();                        // default constructor
    ClassName(Type param1, ...);        // parameterised constructor
    void   setSomething(Type val);      // setter
    Type   getSomething();              // getter
    void   print();                     // display method
    ~ClassName();                       // destructor

private:
    Type memberOne;
    Type memberTwo;
};

#endif // CLASSNAME_H_INCLUDED
```

### Inheritance variant

```cpp
#ifndef DERIVED_H_INCLUDED
#define DERIVED_H_INCLUDED

#include "Base.h"

class Derived : public Base
{
public:
    Derived();
    Derived(Type baseParam, Type derivedParam);
    void   setExtra(Type val);
    Type   getExtra();
    void   print();          // override base print
    ~Derived();

private:
    Type extraMember;
};

#endif // DERIVED_H_INCLUDED
```

### Composition variant (class holds another class as a member)

```cpp
#ifndef CONTAINER_H_INCLUDED
#define CONTAINER_H_INCLUDED

#include "Part.h"

class Container
{
public:
    Container();
    void setPartData(Type a, Type b);
    Part getPart();
    void print();
    ~Container();

private:
    Part partMember;   // composition — Part object lives inside Container
};

#endif // CONTAINER_H_INCLUDED
```

---

## Step 3 — Write the Implementation File (`ClassNameImp.cpp`)

### Rules
- `#include "ClassName.h"` at the top (and `<iostream>`, `<cmath>` as needed).
- `using namespace std;`
- Every method declared in the header **must** have a body here.
- Prefix every method with `ClassName::`.
- Default constructors initialise all data members to zero/empty.
- `print()` uses `cout` — match the exact output format the problem demands.
- Destructor body is empty `{}` unless dynamic memory is involved.

### Template

```cpp
#include "ClassName.h"
#include <iostream>
using namespace std;

// --- Constructors ---
ClassName::ClassName()
{
    memberOne = 0;
    memberTwo = 0;
}

ClassName::ClassName(Type param1, Type param2)
{
    memberOne = param1;
    memberTwo = param2;
}

// --- Setters ---
void ClassName::setSomething(Type val)
{
    memberOne = val;
}

// --- Getters ---
Type ClassName::getSomething()
{
    return memberOne;
}

// --- Other methods ---
void ClassName::print()
{
    cout << "memberOne:" << memberOne << " memberTwo:" << memberTwo;
}

// --- Destructor ---
ClassName::~ClassName()
{
}
```

### Inheritance variant — calling the base constructor

```cpp
#include "Derived.h"
#include <iostream>
using namespace std;

Derived::Derived()
{
    extraMember = 0;
}

// Use initialiser list to pass args up to the base constructor
Derived::Derived(Type baseParam, Type derivedParam)
    : Base(baseParam)
{
    extraMember = derivedParam;
}

void Derived::setExtra(Type val)
{
    extraMember = val;
}

Type Derived::getExtra()
{
    return extraMember;
}

// Call base print first, then add own data
void Derived::print()
{
    Base::print();
    cout << " extra:" << extraMember;
}

Derived::~Derived()
{
}
```

### Composition variant — delegating to the member object

```cpp
#include "Container.h"
#include <iostream>
using namespace std;

Container::Container()
{
    // partMember default-constructs automatically
    partMember.setA(0);
    partMember.setB(0);
}

void Container::setPartData(Type a, Type b)
{
    partMember.setA(a);
    partMember.setB(b);
}

Part Container::getPart()
{
    return partMember;
}

void Container::print()
{
    partMember.print();
}

Container::~Container()
{
}
```

---

## Step 4 — Write the Client File (`main.cpp`)

### Rules
- `#include` every header used.
- `using namespace std;`
- Create at least one object of each class.
- Call **every** method at least once — setter, getter, print, parameterised constructor.
- Use `cout << endl;` between object outputs for readability.
- Comment each block so it is clear which class/feature is being tested.

### Template

```cpp
#include <iostream>
#include "ClassName.h"
// #include "DerivedClass.h"   // add if using inheritance
// #include "OtherClass.h"     // add if using composition

using namespace std;

int main()
{
    // --- Test default constructor ---
    ClassName obj1;
    obj1.print();
    cout << endl;

    // --- Test setters ---
    obj1.setSomething(42);
    obj1.print();
    cout << endl;

    // --- Test parameterised constructor ---
    ClassName obj2(10, 20);
    obj2.print();
    cout << endl;

    // --- Test getters ---
    cout << obj2.getSomething() << endl;

    // --- Test derived/composed class (uncomment when needed) ---
    /*
    DerivedClass d1;
    d1.print();
    cout << endl;
    d1.setExtra(99);
    d1.print();
    cout << endl;
    */

    return 0;
}
```

---

## Step 5 — Output Checklist

Before presenting the solution, verify every item:

- [ ] Header has include guard (`#ifndef` / `#define` / `#endif`)
- [ ] All methods declared in header are implemented in `Imp.cpp`
- [ ] No method bodies inside the header file
- [ ] `main.cpp` includes all required headers
- [ ] Every declared method is called at least once in `main.cpp`
- [ ] Inheritance uses `: public Base` in header and initialiser list in `Imp.cpp`
- [ ] `print()` output format matches exactly what the problem specifies
- [ ] Destructor exists in both header and implementation

---

## Real-World Example — PointADT

This is the canonical reference. Every solution produced by this skill
must follow this exact structure.

### `point.h`

```cpp
#ifndef POINT_H_INCLUDED
#define POINT_H_INCLUDED

class point
{
public:
    point();
    point(double varX);
    void   setX(double);
    void   setY(double);
    double getX();
    double getY();
    void   print();
    ~point();

private:
    double x;
    double y;
};

#endif // POINT_H_INCLUDED
```

### `pointImp.cpp`

```cpp
#include "point.h"
#include <iostream>
using namespace std;

point::point()
{
    x = 0;
    y = 0;
}

point::point(double varX)
{
    x = varX;
    y = 0;
}

void point::setX(double varX) { x = varX; }
void point::setY(double varY) { y = varY; }

double point::getX() { return x; }
double point::getY() { return y; }

void point::print()
{
    cout << "x:" << x << " y:" << y;
}

point::~point() {}
```

### `main.cpp` (client side)

```cpp
#include <iostream>
#include "point.h"
#include "point3D.h"
#include "line.h"
using namespace std;

int main()
{
    // Test point
    point p1;
    p1.setX(10);
    p1.setY(5);
    p1.print();
    cout << endl;

    // Test point3D (derived)
    point3D p2;
    p2.setX(3);
    p2.setY(5);
    p2.setZ(7);
    p2.print();
    cout << endl;

    // Test line (composition)
    line l;
    l.setStartPt(1, 2);
    l.setEndPt(13, 8);
    cout << l.distance() << endl;
    cout << l.angle()    << endl;

    return 0;
}
```

---

## Common Pitfalls

| Mistake | Fix |
|---------|-----|
| Putting method bodies in the `.h` file | Move all bodies to `Imp.cpp` |
| Forgetting to call `Base::print()` in derived `print()` | Always delegate up first |
| Missing `#include "Base.h"` inside derived header | Add at top of derived `.h` |
| Initialising base member in derived constructor body | Use initialiser list: `: Base(param)` |
| Forgetting `cout << endl` between prints in main | Add after every `print()` call |
| Include guard name clashes | Use full filename: `POINT3D_H_INCLUDED` |

---

## Formula Reference (for geometry problems)

```cpp
#include <cmath>

// Distance between two points
double dist = sqrt(pow(x2 - x1, 2) + pow(y2 - y1, 2));

// Angle of a line in degrees
double angle = atan((y2 - y1) / (x2 - x1)) * 57.2958;
```

Always `#include <cmath>` in the implementation file that uses these.
