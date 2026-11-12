# LaTeX Basics & Document Structure (latex1)

## 1. What is LaTeX?

LaTeX is a document preparation tool that is widely used for creating academic reports, research papers, and technical documents.

Unlike regular word processors like Microsoft Word or Google Docs where you format text visually (changing font size, margins, and line spaces manually), in LaTeX you write plain text and use code commands to define the structure of your document. The compiler then generates a clean, neatly formatted PDF.

### Why We Use LaTeX
- **Automatic Formatting**: It handles page layout, section numbering, and margins automatically.
- **Consistent Output**: The output looks the same on every operating system.
- **Great for Research Papers**: Most conferences and journals (like IEEE) provide LaTeX templates.
- **Easy Referencing**: Cross-referencing sections, figures, and references is automatic and does not break when you add new content.

---

## 2. Basic Structure of a LaTeX File

Every LaTeX document has two main parts:
1. **The Preamble**: Everything before `\begin{document}`. Here we specify the document type (article, report, etc.) and load any required packages.
2. **The Document Body**: The area between `\begin{document}` and `\end{document}` where we write the actual content.

### Simple Working Example
```latex
\documentclass{article}          % Defines the type of document

% Preamble: Add title, author, date
\title{My First LaTeX Document}
\author{Aryan Sharma}
\date{\today}

\begin{document}

\maketitle                       % Prints the title block

\section{Introduction}
This is a simple paragraph in LaTeX. You just type text normally, 
and LaTeX takes care of line wrapping and spacing.

Leave an empty line to start a new paragraph.

\end{document}
```

---

## 3. Common Document Classes

When starting a document with `\documentclass{...}`, we choose the class based on what we are writing:
- `article`: For short reports, assignments, and research papers.
- `report`: For longer project reports that need chapters.
- `book`: For full-length books with front and back matter.
- `beamer`: For creating presentation slides.

---

## 4. Headings and Sectioning

LaTeX automatically numbers headings for you:

```latex
\section{Main Topic}            % Creates heading: 1. Main Topic
\subsection{Sub-Topic}          % Creates heading: 1.1 Sub-Topic
\subsubsection{Detail}          % Creates heading: 1.1.1 Detail

% If you don't want numbers, add an asterisk (*):
\section*{Unnumbered Heading}
```

---

## 5. Basic Text Formatting

Here are the basic formatting commands used in daily writing:

- **Bold**: `\textbf{bold text}`
- **Italic**: `\textit{italic text}`
- **Underline**: `\underline{underlined text}`
- **Monospace (Code style)**: `\texttt{source code}`
- **Comments**: Any line starting with `%` is a comment and is ignored during compilation.

### Quotation Marks in LaTeX
In LaTeX, typing standard double quotes (`"word"`) can cause formatting errors. Instead, use:
- Two backticks for opening quotes: ` `` `
- Two single quotes for closing quotes: ` '' `
- Example: ` ``Hello World'' `

---

## 6. Creating Lists

LaTeX has simple environments for bullet points and numbered lists:

### Bullet Points (`itemize`)
```latex
\begin{itemize}
    \item First point
    \item Second point
    \item Third point
\end{itemize}
```

### Numbered List (`enumerate`)
```latex
\begin{enumerate}
    \item Step one: Write the draft
    \item Step two: Add references
    \item Step three: Compile to PDF
\end{enumerate}
```

---

## 7. Labels and Cross-Referencing

Instead of manually typing section or page numbers, LaTeX lets you label parts of your document and refer to them dynamically:

- Set a label: `\label{sec:intro}`
- Refer to its number: `\ref{sec:intro}`
- Refer to its page: `\pageref{sec:intro}`

Example:
```latex
\section{System Design} \label{sec:design}
This section explains the system architecture.

% Later in the document:
As discussed in Section \ref{sec:design}, the system consists of three modules.
```
