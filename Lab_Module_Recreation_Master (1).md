# Laboratory Module Recreation Master File
## C++ Programming Laboratory Series — Institutional Style Guide & Reconstruction Templates

> **Purpose:** This document captures the complete structural, pedagogical, and formatting blueprint of the C++ laboratory series modeled on Exercise 4. Use it to recreate any new exercise by supplying only the topic. The included Python generator script produces a correctly formatted PDF with no external reference needed.

---

# PART 1 — CANONICAL FORMAT (Exercise 4 Standard)

The Exercise 4 PDF is the canonical formatting reference for all procedural exercises in this series. Every rule below is derived directly from that document. Any new exercise generated from this file must be indistinguishable in structure and tone from Exercise 4.

---

## 1.1 Page Layout

| Property | Value |
|---|---|
| Page size | US Letter |
| Left / Right margin | 1.2 inches |
| Top / Bottom margin | 1.1 inches |
| Font — body | Helvetica, 11 pt, leading 16 |
| Font — headings | Helvetica-Bold, 11 pt |
| Font — title line 1 | Helvetica-Bold, 13 pt |
| Font — title line 2 | Helvetica-Bold, 11 pt |
| Font — code | Courier, 10 pt, leading 14 |
| Text color | Black throughout |
| Background | White, no color accents |

**No decorative elements.** No banners, no colored boxes, no horizontal rules, no tables, no icons. Plain black text on white paper.

---

## 1.2 Document Section Order

Every exercise contains exactly these four sections, in this order, with no additions:

```
1. Exercise Number + Title       <- two lines, no blank line between them
2. Introduction:                 <- heading with colon
3. Learning Outcomes:            <- heading with colon, immediately followed by bullets
4. Problem Description:          <- heading with colon, immediately followed by function specs
   [closing line]                <- "Call all the functions created in function main()."
```

Nothing else appears. No conclusion, no grading rubric, no references section, no file structure table, no implementation notes, no step-by-step procedure list.

---

## 1.3 Title Block

```
Exercise [N]
[Topic Category]: [Specific Problem Name]
```

- Exercise number is on its own line, bold, 13 pt.
- Subtitle is on the very next line, bold, 11 pt — no blank line between them.
- Subtitle uses Title Case.
- A colon separates the topic category from the problem name.
- No period at the end.

**Examples:**
```
Exercise 4
Static Arrays I: Goldbach's Conjecture in Array

Exercise 8
Applying Pointers: Simple Memory Box Simulation
```

---

## 1.4 Introduction Section

**Heading:** `Introduction:` — Helvetica-Bold 11 pt, colon included.

**Length:** 2–3 short paragraphs. Never one sentence only. Never longer than half a page.

**Pattern:**
```
Paragraph 1 — Name and define the concept. State the real-world or mathematical motivation.
              No code yet.
Paragraph 2 — Show the essential syntax or formula in a code block. One or two lines only.
              Follow with one sentence explaining it.
Paragraph 3 — [Optional] One additional note or context sentence. May include a second
              code block if a second syntax form is needed (e.g., delete after new).
```

**Tone rules:**
- Formal academic prose. No contractions.
- Third person in paragraphs 1 and 3. The word "you" does not appear in the introduction.
- Present tense throughout.
- The concept is named in the very first sentence.

**What is never in the introduction:**
- Function prototypes.
- Step-by-step instructions.
- Learning outcomes.
- File names.
- Any mention of what the student "will do."

**Voice model (Exercise 4):**
> Goldbach's conjecture (named after German mathematician Christian Goldbach on June 7, 1742) is a problem which states that any even positive integer greater than four (4) can be expressed as the sum of two odd prime integers.

**Voice model (pointer syntax topic):**
> Pointers are a data type in which the content is not a numerical value but rather the memory address of another variable. When declaring and initializing a pointer, follow the syntax below:
> ```cpp
> datatype* pointerName = new datatype;
> ```

---

## 1.5 Learning Outcomes Section

**Heading:** `Learning Outcomes:` — Helvetica-Bold 11 pt, colon included, no blank line before bullets.

**Format:** Bullet list using the ▪ character (Unicode 25AA). Each bullet is one sentence.

**Count:** Exactly 2 bullets for procedural exercises. No more, no fewer.

**Each bullet:**
- Begins with an imperative verb: Implement, Apply, Create, Compute, Demonstrate, Read, Write.
- States a concrete, measurable task — not a vague goal.
- Does not describe *how* to accomplish the task.

**Examples (Exercise 4):**
```
▪ Implement an initialization of the array with random natural numbers
▪ Implement a function to print the Goldbach's pair of an even natural number greater than 4 in array.
```

**Anti-pattern (never use):**
```
▪ Understand how pointers work in C++       <- too vague
▪ Learn to use the new keyword              <- not measurable
```

---

## 1.6 Problem Description Section

**Heading:** `Problem Description:` — Helvetica-Bold 11 pt, colon included.

**Content:** Function specifications only. No numbered steps. No file names. No prose between specs.

**Count:** 3–5 function specifications. Exercise 4 has exactly 4.

**Each specification follows this exact format:**

```
/* [One or two sentence description: what the function receives, what it does,
   what it returns or outputs. Behavior only — never implementation.] */
returnType functionName(paramType paramName, ...);
```

**Rules for the comment:**
- Block comment `/* */` always. Never `//` on the same line as the prototype.
- One or two sentences maximum.
- States what the function does, what it receives, and what it returns or prints.
- Uses present tense: "Determines", "Initializes", "Prints", "Returns", "Computes".
- Never says "loop through", "use a for loop", "check each element" — behavior only.
- Parameter names in the comment match the parameter names in the prototype.

**Rules for the prototype:**
- Standard C++ syntax.
- Parameter names are always included (not just types).
- Array parameters written as `int x[]` not `int* x` unless pointers are the topic.

**Closing line (mandatory, always last):**
```
Call all the functions created in function main().
```
This line appears as plain body text after the last function spec. No heading, no bullet.

---

## 1.7 Scaffolding Rule

**This series gives students the *what*, never the *how*.**

The function specification tells the student the signature and the observable behavior. It does not tell them which algorithm to use, which loop structure to use, or how to handle edge cases.

**Permitted in a spec:**
- What the function receives (parameters and types).
- What the function returns or outputs.
- Which other functions it must call (e.g., "Using the functions isPrime and isEven").

**Never permitted in a spec:**
- Algorithm names (Bubble Sort, Linear Search, etc.).
- Loop or conditional structure hints.
- Variable name suggestions for the implementation.
- Sub-bullets or numbered sub-steps under a spec.

---

# PART 2 — TOPIC EXPANSION GUIDE

## 2.1 Curriculum Sequence

| Exercise | Topic | Key New Concept |
|---|---|---|
| Ex 4 | Static Arrays + Math | Array init, bool functions |
| Ex 5 | Structs + File I/O | `struct`, `ifstream`/`ofstream` |
| Ex 6 | Classes (encapsulation) | `class`, private members |
| Ex 7 | Inheritance | Derived classes |
| Ex 8 | Pointers + Virtual Functions | `new`/`delete`, `virtual` |
| Ex 9 | Function Templates | `template <typename T>` |
| Ex 10 | Class Templates | Template class |
| Ex 11 | Exception Handling | `try`/`catch`/`throw` |
| Ex 12 | STL Vectors | `std::vector`, iterators |

## 2.2 Introduction Sentence Openers by Topic Type

**Mathematical / algorithmic topic:**
> `[Concept]` ([attribution if applicable]) is a [one-sentence definition]. Take for example: [concrete illustration].

**Programming concept / syntax topic:**
> `[Concept]` are [definition of what they are and what distinguishes them from prior concepts]. When [using / declaring / initializing] a `[concept]`, follow the syntax below:

**Data / file I/O topic:**
> Until this point, the programs that have been created deal only with [prior approach]. A program may also [new capability]. For this exercise, [specific behavior or source].

**OOP / abstraction topic:**
> As a program's code base grows in size, so does its complexity. When the program is considered as a single entity composed of autonomous sub-entities, that complexity can be simplified. In C++, `[concept]` is the mechanism by which [benefit] is achieved.

---

# PART 3 — FUNCTION COMMENT TEMPLATES

Fill in the bracketed fields. Use present tense. One or two sentences only.

```cpp
/* Initializes [data structure] of size s with [content description]. */

/* Determines if [condition]. Returns [true value] if [condition], [false value] otherwise. */

/* Computes and returns the [quantity] of [object or dataset]. */

/* Prints [content] to standard output [in what format, if notable]. */

/* Prints the [result] of element(s) in [data structure] (if there are any).
   Using the functions [helperFn1] and [helperFn2]. */

/* Reads data from [source] and stores it in [destination]. */

/* Writes [content] to a file named "[filename.ext]". */

/* Sets the value of [member] to the passed parameter. */

/* Returns the value of [member]. */

/* Dynamically allocates [data structure] of size s. Returns the pointer. */

/* Releases the memory allocated for [pointer] and sets it to null. */
```

---

# PART 4 — QUICK REFERENCE CHECKLIST

Before finalizing any generated exercise, verify every item below.

### Structure
- [ ] Exercise number alone on line 1; subtitle on line 2, no blank line between
- [ ] Exactly four sections: Introduction, Learning Outcomes, Problem Description, closing line
- [ ] No numbered steps, no file structure table, no implementation notes
- [ ] Closing line reads: "Call all the functions created in function main()."

### Introduction
- [ ] 2–3 paragraphs only
- [ ] Concept named and defined in the first sentence
- [ ] Syntax or formula shown in a code block before the procedure section
- [ ] No function prototypes, no "you will", no step instructions

### Learning Outcomes
- [ ] Exactly 2 bullets for procedural exercises
- [ ] Each bullet begins with an imperative verb
- [ ] Each outcome is concrete and measurable
- [ ] Bullets use ▪ character

### Problem Description
- [ ] 3–5 function specifications
- [ ] Each spec has a block comment above the prototype — never inline
- [ ] Comment describes behavior only — no algorithm hints
- [ ] Closing line "Call all the functions..." appears after the last spec

### Tone
- [ ] No contractions anywhere
- [ ] "you" does not appear in the introduction
- [ ] Present tense for all function descriptions
- [ ] Academic formal register throughout

---

# PART 5 — PYTHON PDF GENERATOR

## 5.1 How to Use

This script generates a correctly formatted exercise PDF from a single topic input. To create a new exercise:

1. Open the script below.
2. Fill in only the `EXERCISE CONFIGURATION` block at the top.
3. Run the script. The PDF is written to `OUTPUT_PATH`.

No other files, references, or templates are needed. The generator enforces all layout and style rules automatically.

---

## 5.2 Configuration Fields

| Field | Type | Description |
|---|---|---|
| `EXERCISE_NUMBER` | int | The exercise number, e.g. `8` |
| `EXERCISE_TITLE` | str | Full subtitle string, e.g. `"Applying Pointers: Simple Memory Box Simulation"` |
| `OUTPUT_PATH` | str | Output filename, e.g. `"Exercise_8.pdf"` |
| `INTRO_PARAGRAPHS` | list of str | 2–3 paragraph strings. No markdown. No code inside. |
| `INTRO_CODE_BLOCKS` | list of (int, str) | Each tuple: (index of paragraph after which to insert, code string) |
| `OUTCOMES` | list of str | Exactly 2 bullet strings. No leading symbol needed. |
| `FUNCTIONS` | list of (str, str) | Each tuple: (comment text without delimiters, prototype string with semicolon) |

---

## 5.3 Generator Script

```python
# ============================================================
# C++ Lab Exercise PDF Generator
# Produces Exercise 4-style PDFs from topic input only.
# Requires: pip install reportlab
# ============================================================

from reportlab.lib.pagesizes import letter
from reportlab.lib.styles import ParagraphStyle
from reportlab.lib.units import inch
from reportlab.lib import colors
from reportlab.platypus import SimpleDocTemplate, Paragraph, Spacer, Preformatted

# ============================================================
# EXERCISE CONFIGURATION — edit only this block
# ============================================================

EXERCISE_NUMBER = 8
EXERCISE_TITLE  = "Applying Pointers: Simple Memory Box Simulation"
OUTPUT_PATH     = "Exercise_8_Pointers.pdf"

INTRO_PARAGRAPHS = [
    ("Pointers are a data type in which the content is not a numerical value but rather "
     "the memory address of another variable. When declaring and initializing a pointer, "
     "follow the syntax below:"),

    ("A pointer must be released after use to avoid memory leaks. "
     "To deallocate a single pointer:"),

    ("In this exercise, pointers are used to dynamically allocate and manage a collection "
     "of integer values referred to as a memory box. The student will implement functions "
     "that operate on this dynamically allocated array."),
]

# (insert_after_paragraph_index, code_string)
INTRO_CODE_BLOCKS = [
    (0, "datatype* pointerName = new datatype;"),
    (1, "delete pointerName;"),
]

OUTCOMES = [
    "Apply pointer syntax to dynamically allocate and deallocate memory.",
    "Implement functions that operate on a pointer-based integer array.",
]

# (comment_text, prototype_string)
FUNCTIONS = [
    (
        "Dynamically allocates an integer array of size s,\n"
        "   initializes each element to 0, returns the pointer.",
        "int* createBox(int s);"
    ),
    (
        "Fills the array x of size s with random integers\n"
        "   between 1 and 100.",
        "void fillBox(int* x, int s);"
    ),
    (
        "Determines if integer n is odd.\n"
        "   Returns true if odd, false otherwise.",
        "bool isOdd(int n);"
    ),
    (
        "Prints all odd elements found in array x of size s.\n"
        "   Uses the function isOdd.",
        "void printOddElements(int* x, int s);"
    ),
    (
        "Releases the memory allocated for array x\n"
        "   and sets the pointer to null.",
        "void destroyBox(int*& x);"
    ),
]

# ============================================================
# GENERATOR — do not edit below this line
# ============================================================

BLACK = colors.black

sTitle1  = ParagraphStyle("T1", fontName="Helvetica-Bold", fontSize=13,
                           leading=18, textColor=BLACK, spaceAfter=2)
sTitle2  = ParagraphStyle("T2", fontName="Helvetica-Bold", fontSize=11,
                           leading=16, textColor=BLACK, spaceAfter=10)
sHeading = ParagraphStyle("H",  fontName="Helvetica-Bold", fontSize=11,
                           leading=15, textColor=BLACK, spaceBefore=10, spaceAfter=4)
sBody    = ParagraphStyle("B",  fontName="Helvetica",      fontSize=11,
                           leading=16, textColor=BLACK, spaceAfter=6)
sBullet  = ParagraphStyle("BL", fontName="Helvetica",      fontSize=11,
                           leading=16, textColor=BLACK, leftIndent=18, spaceAfter=4)
sCode    = ParagraphStyle("C",  fontName="Courier",        fontSize=10,
                           leading=14, textColor=BLACK, leftIndent=18, spaceAfter=2)

def make_pdf(output_path):
    doc = SimpleDocTemplate(
        output_path, pagesize=letter,
        leftMargin=1.2*inch, rightMargin=1.2*inch,
        topMargin=1.1*inch,  bottomMargin=1.1*inch,
    )
    story = []

    # Title
    story.append(Paragraph(f"Exercise {EXERCISE_NUMBER}", sTitle1))
    story.append(Paragraph(EXERCISE_TITLE, sTitle2))

    # Introduction
    story.append(Paragraph("Introduction:", sHeading))
    code_after = {}
    for idx, code_str in INTRO_CODE_BLOCKS:
        code_after.setdefault(idx, []).append(code_str)
    for i, para_text in enumerate(INTRO_PARAGRAPHS):
        story.append(Paragraph(para_text, sBody))
        if i in code_after:
            for code_str in code_after[i]:
                story.append(Preformatted(code_str, sCode))
                story.append(Spacer(1, 4))

    # Learning Outcomes
    story.append(Paragraph("Learning Outcomes:", sHeading))
    for outcome in OUTCOMES:
        story.append(Paragraph(f"\u25aa {outcome}", sBullet))

    # Problem Description
    story.append(Paragraph("Problem Description:", sHeading))
    for comment, prototype in FUNCTIONS:
        story.append(Preformatted(f"/* {comment} */\n{prototype}", sCode))
        story.append(Spacer(1, 6))

    # Closing line
    story.append(Spacer(1, 4))
    story.append(Paragraph("Call all the functions created in function main().", sBody))

    doc.build(story)
    print(f"PDF written to: {output_path}")

make_pdf(OUTPUT_PATH)
```

---

## 5.4 Worked Example — New Topic: STL Vectors

To generate Exercise 12 on STL Vectors, replace the configuration block with:

```python
EXERCISE_NUMBER = 12
EXERCISE_TITLE  = "STL Vectors: Student Grade Roster"
OUTPUT_PATH     = "Exercise_12_Vectors.pdf"

INTRO_PARAGRAPHS = [
    ("The Standard Template Library (STL) provides a set of generic container classes "
     "that manage collections of objects. Among these, the vector is a dynamically resizable "
     "sequence container that handles its own memory allocation and deallocation automatically."),

    ("A vector is declared and elements are appended using the following syntax:"),

    ("Unlike static arrays, a vector grows as elements are added and its current size is "
     "always accessible through the size member function."),
]

INTRO_CODE_BLOCKS = [
    (1, "std::vector<datatype> vectorName;\nvectorName.push_back(value);"),
]

OUTCOMES = [
    "Implement a vector-based roster to store and retrieve student grade records.",
    "Apply STL vector member functions to compute and display grade statistics.",
]

FUNCTIONS = [
    (
        "Fills vector grades with n grade values entered by the user.",
        "void fillGrades(std::vector<int>& grades, int n);"
    ),
    (
        "Determines if integer g is a passing grade (greater than or equal to 60).\n"
        "   Returns true if passing, false otherwise.",
        "bool isPassing(int g);"
    ),
    (
        "Computes and returns the average of all values in vector grades.",
        "double computeAverage(const std::vector<int>& grades);"
    ),
    (
        "Prints all failing grades found in vector grades.\n"
        "   Uses the function isPassing.",
        "void printFailingGrades(const std::vector<int>& grades);"
    ),
]
```

Run the script — the output is a complete, correctly formatted Exercise 12 PDF.

---

> **Document Status:** Revised to Exercise 4 canonical standard. All scaffolding, numbered steps, file structure tables, and color formatting have been removed from both the style rules and the generator. The Python script produces compliant PDFs from topic input alone, with no external reference needed.
