<!---
{
  "id": "11830a64-a50f-461e-8379-ae9511768cc4",
  "teaches": "Document Structure Hierarchy in LaTeX",
  "depends_on": ["00650b50-14de-471d-a347-246f47ffadde"],
  "author": "Stephan Bökelmann",
  "first_used": "2025-06-02",
  "keywords": ["LaTeX", "document structure", "chapters", "sections", "vim"]
}
--->

# Document Structure Hierarchy in LaTeX

> In this exercise you will learn how to structure LaTeX documents using parts, chapters, sections, subsections, and paragraphs. Furthermore we will explore how different document classes influence the document hierarchy.

### Introduction

A well-structured document is easier to read, maintain, and navigate. LaTeX provides a hierarchical system of sectioning commands that reflect the logical structure of your document. These sectioning commands automatically handle numbering, formatting, and inclusion in the table of contents.

The available levels depend on the chosen `documentclass`:

* In `article` class: `\section`, `\subsection`, `\subsubsection`, `\paragraph`, `\subparagraph`
* In `report` and `book` classes: `\part`, `\chapter`, followed by the same lower levels

Here is the general hierarchy (top to bottom):

1. `\part`
2. `\chapter` *(only in `report` and `book`)*
3. `\section`
4. `\subsection`
5. `\subsubsection`
6. `\paragraph`
7. `\subparagraph`

LaTeX automatically numbers these elements (unless starred versions like `\section*{...}` are used) and formats them appropriately.

Understanding this hierarchy is essential for writing larger documents such as theses, books, reports, or technical manuals.

### Further Readings and Other Sources

* [Overleaf: Sections and Chapters](https://www.overleaf.com/learn/latex/Sections_and_chapters)
* [LaTeX Wikibook - Sectioning](https://en.wikibooks.org/wiki/LaTeX/Document_Structure#Sectioning_commands)
* [YouTube - LaTeX Sectioning Tutorial](https://www.youtube.com/watch?v=XtFMnsyecp8)
* [The Not So Short Introduction to LaTeX (Document Structure Section)](https://tobi.oetiker.ch/lshort/lshort.pdf)

---

## Tasks

### Task 0: Create a New LaTeX File Using the `book` Class

Open Vim and create a new file:

```bash
vim structure.tex
```

Insert the following base structure:

```latex
\documentclass{book}
\begin{document}

Your content goes here.

\end{document}
```

Save and exit Vim.

### Task 1: Create a Complete Hierarchical Structure

Replace `Your content goes here.` with:

```latex
\part{Fundamentals}

\chapter{Introduction}

\section{Motivation}
This document demonstrates the LaTeX document structure.

\subsection{Background}
A brief background.

\subsubsection{Historical Notes}
Some history here.

\paragraph{Key Insight}
Important detail.

\subparagraph{Further Clarification}
Even more detail.

\chapter{Advanced Topics}

\section{Challenges}
Challenges in document structuring.
```

Compile using:

```bash
pdflatex structure.tex
```

### Task 2: Switch to the `article` Class and Observe Differences

Edit the first line of your file to:

```latex
\documentclass{article}
```

Recompile. Observe:

* `\part` is still valid.
* `\chapter` causes an error (not defined in `article` class).
* The other commands (`\section`, `\subsection`, etc.) still work.

### Task 3: Create a Table of Contents

Before `\end{document}`, add:

```latex
\tableofcontents
```

Recompile twice to ensure the table of contents is generated correctly.

```bash
pdflatex structure.tex
pdflatex structure.tex
```

Verify that all sections and subsections are listed in the table of contents with correct numbering.

---

## Questions

1. Which document classes support `\chapter`?
2. What happens if you use `\chapter` in `article` class?
3. How does LaTeX determine numbering for sectioning commands?
4. Why is it useful to include a table of contents in longer documents?

---

## Advice

Always structure your documents logically using the full hierarchy LaTeX provides. Avoid manually formatting section headers or numbering — let LaTeX handle these automatically. When writing longer documents, start with an outline using `\part`, `\chapter`, and `\section` commands. As the document grows, you can easily insert, reorder, or modify sections without breaking the structure. Proper use of sectioning commands also ensures consistent table of contents generation and cross-referencing later.
