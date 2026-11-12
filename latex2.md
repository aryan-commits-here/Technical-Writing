# LaTeX Tables, Math, and Figures

## 1. Writing Mathematics in LaTeX

One of the biggest strengths of LaTeX is writing mathematical formulas and equations cleanly.

### Inline Math vs. Display Math
- **Inline Math**: Written inside single dollar signs `$ ... $`. This places the formula inside the flow of a normal sentence without breaking the paragraph.
  - *Example*: `$E = mc^2$` or `Let $x = 5$.`
- **Display Math**: Centered on its own separate line for important equations.
  - *Unnumbered*: `\[ a^2 + b^2 = c^2 \]`
  - *Numbered*: Using the `equation` environment:
    ```latex
    \begin{equation}
        f(x) = ax^2 + bx + c
    \end{equation}
    ```

### Common Math Symbols
To use advanced math symbols and equations, add `\usepackage{amsmath}` to your preamble.

- **Superscript (Powers)**: `x^2`, `e^{i\pi}`
- **Subscript**: `a_1`, `x_{i+1}`
- **Fractions**: `\frac{numerator}{denominator}` $\rightarrow$ `\frac{a + b}{2}`
- **Square Roots**: `\sqrt{x}`, `\sqrt[3]{8}`
- **Greek Letters**: `\alpha`, `\beta`, `\theta`, `\pi`, `\lambda`, `\sigma`
- **Summation & Integrals**: `\sum_{i=1}^{n} i`, `\int_{0}^{1} x \, dx`
- **Inequalities**: `\le` ($\le$), `\ge` ($\ge$), `\neq` ($\neq$)

---

## 2. Creating Tables in LaTeX

Tables in LaTeX are created using the `tabular` environment, usually placed inside a `table` environment so you can add a title and caption.

### Basic Table Syntax
```latex
\begin{table}[h]
\centering
\caption{Student Marks Summary}
\begin{tabular}{|l|c|r|}
    \hline
    \textbf{Name} & \textbf{Subject} & \textbf{Marks} \\
    \hline
    Aryan & Technical Writing & 95 \\
    Rahul & Data Structures & 88 \\
    Priya & Algorithms & 92 \\
    \hline
\end{tabular}
\end{table}
```

### Explanation of Table Commands
- `|l|c|r|`: Specifies column alignments and vertical border lines:
  - `l`: Left-aligned
  - `c`: Centered
  - `r`: Right-aligned
  - `|`: Vertical line between columns
- `&`: Separates one column from the next.
- `\\`: Moves to the next row.
- `\hline`: Draws a horizontal border line.
- `\centering`: Centers the table horizontally on the page.
- `\caption{...}`: Adds a descriptive title above or below the table.

---

## 3. Adding Images and Figures

To insert pictures or screenshots into a LaTeX document, include the `graphicx` package in the preamble:

```latex
\usepackage{graphicx}
```

### Inserting an Image
```latex
\begin{figure}[h]
    \centering
    \includegraphics[width=0.6\textwidth]{diagram.png}
    \caption{System Architecture Diagram}
    \label{fig:architecture}
\end{figure}
```

### Key Options for Images
- `width=0.6\textwidth`: Scales the image to 60% of the page text width. You can also specify exact units like `width=5cm`.
- `\centering`: Centers the picture on the page.
- `[h]`: Placement hint asking LaTeX to put the figure **h**ere if space permits.
- `\caption{...}`: Adds a figure title and automatically generates a figure number (e.g., Figure 1).
- `\label{fig:...}`: Allows referencing the figure in your text using `\ref{fig:architecture}`.

---

## 4. Drawing Simple Graphics & Adding Colors

### The `picture` Environment
LaTeX can also draw basic shapes (like lines, circles, and boxes) directly without needing an external image:
```latex
\setlength{\unitlength}{1mm}
\begin{picture}(50,20)
    \put(5,10){\line(1,0){30}}     % Draws a horizontal line
    \put(20,10){\circle{8}}        % Draws a circle
\end{picture}
```

### Adding Colors with `xcolor`
Include `\usepackage{xcolor}` in the preamble:
- Colored text: `\textcolor{blue}{This is blue text.}`
- Highlight box: `\colorbox{yellow}{Highlighted text}`
