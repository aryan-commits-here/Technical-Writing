# Source Code Documentation with Doxygen

## 1. What is Doxygen?

**Doxygen** is an automated tool used to generate clean documentation directly from comments written inside your source code.

In computer science projects, writing a separate documentation manual often means the manual gets outdated whenever the code changes. With Doxygen, you write special comment blocks right above your functions and classes in your code (in C, C++, Java, or Python). Doxygen reads these comments and generates a full **HTML website** and a **PDF / LaTeX manual** automatically.

---

## 2. Doxygen Comment Styles

To let Doxygen know a comment is meant for documentation (and not just an ordinary comment), we use special comment blocks:

### Standard Block Style
```cpp
/**
 * @brief Brief summary of what this function does.
 */
```

### Single Line Style
```cpp
/// Brief summary using three slashes
```

---

## 3. Important Tags We Learned

Doxygen uses tags that start with `@` (or `\`) to categorize information:

| Tag | What It Does |
|---|---|
| `@file` | Documents the source file itself (required for global functions). |
| `@brief` | A quick, one-line explanation of what a function or class does. |
| `@author` | Name of the author who wrote the code. |
| `@date` | Date when the file was created or edited. |
| `@param` | Explains an input parameter taken by a function. |
| `@return` | Explains what value the function returns. |
| `@note` | Adds a helpful note or tip for someone reading the documentation. |
| `@warning` | Warns about potential issues or errors if used incorrectly. |

---

## 4. Code Example with Doxygen Comments

Here is a simple C++ program showing how Doxygen tags are written above a function:

```cpp
/**
 * @file math_utils.cpp
 * @brief Simple utility functions for basic math operations.
 * @author Aryan Sharma
 * @date 2026-11-12
 */

#include <iostream>

/**
 * @brief Calculates the factorial of a given positive integer.
 * 
 * This function uses a simple loop to calculate n! (n factorial).
 * 
 * @param n A non-negative integer whose factorial is needed.
 * @return The factorial of the number n.
 * 
 * @note If n is 0 or 1, the function returns 1.
 * @warning Passing negative numbers will cause incorrect results.
 */
long long calculateFactorial(int n) {
    if (n <= 1) {
        return 1;
    }
    long long result = 1;
    for (int i = 2; i <= n; i++) {
        result *= i;
    }
    return result;
}

int main() {
    int num = 5;
    std::cout << "Factorial of " << num << " is " << calculateFactorial(num) << std::endl;
    return 0;
}
```

---

## 5. How to Run Doxygen

To generate documentation from your source code:

1. **Create the configuration file**:
   Open terminal and run:
   ```bash
   doxygen -g
   ```
   This creates a file named `Doxyfile` which has settings for your documentation project.

2. **Basic settings in `Doxyfile`**:
   - `PROJECT_NAME = "My Project"`
   - `INPUT = .` (tells Doxygen to scan the current directory for code files)
   - `GENERATE_HTML = YES` (generates the web version)
   - `GENERATE_LATEX = YES` (generates the LaTeX version)

3. **Generate the documentation**:
   Run:
   ```bash
   doxygen Doxyfile
   ```

4. **View the results**:
   - Doxygen creates an `html/` folder. Open `html/index.html` in your browser to view your browsable documentation site.
   - It also creates a `latex/` folder if you want to compile a PDF manual.
