# Presentations with LaTeX Beamer

## 1. What is Beamer?

**Beamer** is a popular LaTeX document class used to create professional presentation slides in PDF format.

Instead of using slide tools like PowerPoint or Google Slides, Beamer lets you write your presentation using standard LaTeX markup. It is widely used in computer science and academia for conference presentations, project defenses, and seminar talks because it handles math formulas, code listings, and citations with the same quality as LaTeX papers.

---

## 2. Basic Structure of a Beamer Presentation

In Beamer, each slide is called a **frame**. You define slides using the `frame` environment:

```latex
\documentclass{beamer}          % Use the beamer class instead of article

% Choose a presentation theme
\usetheme{Madrid}
\usecolortheme{default}

% Presentation Metadata
\title{Technical Writing Project Presentation}
\subtitle{CSE 3rd Semester}
\author{Aryan Sharma}
\institute{MNIT Jaipur}
\date{\today}

\begin{document}

% Slide 1: Title Slide
\begin{frame}
    \titlepage
\end{frame}

% Slide 2: Outline / Agenda
\begin{frame}{Outline}
    \tableofcontents
\end{frame}

% Slide 3: Content Slide
\section{Introduction}
\begin{frame}{Introduction to Beamer}
    \framesubtitle{Why use code for slides?}
    \begin{itemize}
        \item Clean and consistent slide layout automatically.
        \item Easy to include complex mathematical equations.
        \item Direct reuse of code and citations from LaTeX reports.
    \end{itemize}
\end{frame}

\end{document}
```

---

## 3. Themes and Colors

Beamer comes with many pre-built themes that change the header, footer, and overall slide design with one line in the preamble:

### Popular Themes (`\usetheme{...}`)
- `Madrid`: Clean, modern, with useful bottom navigation bars showing author name, title, and slide numbers.
- `Berlin`: Structured top navigation dots showing section progress.
- `CambridgeUS`: Compact layout with red/burgundy accents.
- `Boadilla`: Minimalist and clean.

### Color Themes (`\usecolortheme{...}`)
You can change the color palette independently using `\usecolortheme{...}`:
- `dolphin`, `whale`, `seahorse` (shades of blue)
- `beaver` (grey and dark red)
- `orchid` (deep purple accents)

---

## 4. Useful Beamer Features

### 1. Highlight Blocks
Beamer has built-in boxes called "blocks" that are great for definitions, theorems, and warnings:

```latex
\begin{frame}{Important Concepts}

    \begin{block}{Definition}
        LaTeX Beamer compiles directly into a standard PDF presentation.
    \end{block}

    \begin{alertblock}{Caution}
        Always keep text brief on slides—avoid long paragraphs.
    \end{alertblock}

    \begin{exampleblock}{Example}
        Use \texttt{\textbackslash pause} to reveal points step by step.
    \end{exampleblock}

\end{frame}
```

### 2. Step-by-Step Reveals with `\pause`
To make bullet points appear one at a time when you advance the slide, add `\pause` between items:

```latex
\begin{frame}{Step-by-Step Execution}
    \begin{itemize}
        \item First, initialize your Git repository.
        \pause
        \item Next, stage the modified files using \texttt{git add}.
        \pause
        \item Finally, save your snapshot with \texttt{git commit}.
    \end{itemize}
\end{frame}
```

### 3. Multi-Column Layout (Side-by-Side Content)
To place text on the left and an image on the right:

```latex
\begin{frame}{Two-Column Slide}
    \begin{columns}
        % Left Column (50% width)
        \begin{column}{0.5\textwidth}
            \textbf{Key Points:}
            \begin{itemize}
                \item High readability
                \item Automatic alignment
                \item Clean graphics
            \end{itemize}
        \end{column}

        % Right Column (50% width)
        \begin{column}{0.5\textwidth}
            \includegraphics[width=\linewidth]{diagram.png}
        \end{column}
    \end{columns}
\end{frame}
```

---

## 5. Summary of Key Commands

| Command | Purpose |
|---|---|
| `\documentclass{beamer}` | Sets the document class for slides. |
| `\begin{frame}{Title} ... \end{frame}` | Creates a single presentation slide. |
| `\frametitle{...}` | Sets the title of the current slide. |
| `\framesubtitle{...}` | Sets a smaller sub-title below the slide title. |
| `\titlepage` | Generates the title slide using author and title metadata. |
| `\pause` | Pauses slide display so points appear on the next click. |
| `\begin{block}{...}` | Draws a styled box for definitions or summaries. |
| `\begin{columns}` | Splits the slide into multiple horizontal columns. |
