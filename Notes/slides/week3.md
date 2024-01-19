---
title: "CS3101"
author: "Josh Maglione"
institute: "University of Galway"
subtitle: "Lecture 3: Latex environments and packages"
header-includes: |
colorlinks: true
urlcolor: violet
---

# Latex Environments

- General blueprints of \LaTeX\ markup is an *environment*. 
- A \LaTeX\ environment has the following basic structure:
  ```latex
  	\begin{<environment>}     % Explicit start 
		%
		% Content
		%
	\end{<environment>}       % Explicit end 
  ```
- We have already seen examples with `document`:
  ```latex
  	\begin{document}
		%
		% Body
		%
	\end{document}
  ```

---

**Now for many many examples**

---

# The `center` Environment

- If you want to center justify your text, then you are in luck!

```latex
\begin{center}
    This text is centered.
\end{center}
```

\begin{center}
    This text is centered.
\end{center}

- This one is super simple.


# The `equation` Environment

- Displayed lines of math can be viewed as an environment.

The following 
```latex
\begin{equation}
    \sum_{n=1}^\infty \frac{1}{n^s} 
        = \prod_{p \text{ prime}} \frac{1}{1 - p^{-s}} 
\end{equation}
```
produces

\begin{equation}
    \sum_{n=1}^\infty \frac{1}{n^s} 
        = \prod_{p \text{ prime}} \frac{1}{1 - p^{-s}} 
\end{equation}

# Now for a slight distraction

\centering
\includegraphics[width=0.5\textwidth]{../imgs/rabbit.jpg}

# Cross-referencing (detour)

\begin{equation}
    \sum_{n=1}^\infty \frac{1}{n^s} 
        = \prod_{p \text{ prime}} \frac{1}{1 - p^{-s}} 
\end{equation}

- Notice the number at the right side (It ChAnGeD!)
- Created with the `equation` environment. 
- Like with citations and references, we can use that number to reference that equation elsewhere. 

# Labels and Refs (down the rabbit hole)

- We need to add a tag to our `equation` environment.
- Look for `\label{<tag>}`

Updated code:

```latex
\begin{equation}\label{Euler}
    \sum_{n=1}^\infty \frac{1}{n^s} 
        = \prod_{p \text{ prime}} \frac{1}{1 - p^{-s}} 
\end{equation}
Equation \eqref{Euler} is the Euler decomposition.
```

\begin{equation}\label{Euler}
    \sum_{n=1}^\infty \frac{1}{n^s} 
        = \prod_{p \text{ prime}} \frac{1}{1 - p^{-s}} 
\end{equation}

Equation \eqref{Euler} is the Euler decomposition.

# Refs and Eqrefs (almost out)

- We used `\eqref{<tag>}` which is special for equations. 

```latex
This is an eqref \eqref{Euler}. 
This is a ref \ref{Euler}.
```

This is an eqref \eqref{Euler}. This is a ref \ref{Euler}.

- With the exception of equation-llike environments, use `\ref{<tag>}`. 
- We will see more examples!

# The `align` environment

*This uses the `amsmath` package we haven't discussed yet.*

```latex
\begin{align} 
    \sum_{n=1}^{\infty} \frac{1}{n^2} 
    &= 1 + \frac{1}{4} + \frac{1}{9} + \cdots \\
    &= \frac{\pi^2}{6} . 
\end{align}
```

\begin{align} 
    \sum_{n=1}^{\infty} \frac{1}{n^2} 
    &= 1 + \frac{1}{4} + \frac{1}{9} + \cdots \\
    &= \frac{\pi^2}{6} . 
\end{align}

- Lots to discuss. First, each line has a number. 

---


```latex
\begin{align} 
    \sum_{n=1}^{\infty} \frac{1}{n^2} 
    &= 1 + \frac{1}{4} + \frac{1}{9} + \cdots \\
    &= \frac{\pi^2}{6} . 
\end{align}
```

\begin{align} 
    \sum_{n=1}^{\infty} \frac{1}{n^2} 
    &= 1 + \frac{1}{4} + \frac{1}{9} + \cdots \\
    &= \frac{\pi^2}{6} . 
\end{align}

- Latex *aligns* based on the `&` symbol.
- New lines are created using `\\`
- To reference a specific line, put `\label{<tag>}` on that line.

---

- We can remove the numbers from the `equation` and `align` environments. 
- Use environments `equation*` and `align*`. 
- Often `*` is used to remove numbering. 

```latex
\begin{align*} 
    \sum_{n=1}^{\infty} \frac{1}{n^2} 
    &= 1 + \frac{1}{4} + \frac{1}{9} + \cdots \\
    &= \frac{\pi^2}{6} . 
\end{align*}
```

\begin{align*} 
    \sum_{n=1}^{\infty} \frac{1}{n^2} 
    &= 1 + \frac{1}{4} + \frac{1}{9} + \cdots \\
    &= \frac{\pi^2}{6} . 
\end{align*}


# The `tabular` Environment

I can't *not* think of *tubular*

<!-- ![](../imgs/tubular.jpeg){ width=50% } -->
\centering
\includegraphics[width=0.5\textwidth]{../imgs/tubular.jpeg}


# The `tabular` Environment (seriously now)

- `tabular` is used for creating tables in \LaTeX.
- One can specify the alignment, formatting, and content of each cell within
the table.
- The `tabular` environment requires an argument:
  
```latex
\begin{tabular}{|l|c|r|}
    % Content
\end{tabular}
```

- The `{|l|c|r|}` explains how to format:
  - `|` put vertical lines
  - `l` left-justifies the text in the column
  - `c` center-justifies the text in the column
  - `r` right-justifies the text in the column
- Thus, we have 3 columns separated by vertical lines. 

---

- We will nest two enviornments: `center` and `tabular` for a centered table. 

```latex
\begin{center}
\begin{tabular}{|l|c|r|}
    \hline
    \textbf{My} & \textbf{Favorite} & \textbf{Table} \\
    \hline
    Look, & it has entries. & Neat. \\
    \hline
\end{tabular}
\end{center}
```


\begin{center}
\begin{tabular}{|l|c|r|}
    \hline
    \textbf{My} & \textbf{Favorite} & \textbf{Table} \\
    \hline
    Look, it & has entries in it. & Whoa cool. \\
    \hline
\end{tabular}
\end{center}

- `\hline` adds a horiztonal line.

# The `enumerate` and `itemize` Environments

- `enumerate` is used to construct numbered lists.
- It enables one to specify items within the list, automatically numbering them in the desired format.
- It's magical moment when you do not have to renumber items in your list.

---

```latex
\begin{enumerate}
    \item First item,
    \item Second item,
    \item Another item,
    \item I am losing count.
\end{enumerate}
```

\begin{enumerate}
    \item First item,
    \item Second item,
    \item Another item,
    \item I am losing count.
\end{enumerate}

---


```latex
\begin{itemize}
    \item First item,
    \item Second item,
    \item Another item,
    \item I am losing count.
\end{itemize}
```

\begin{itemize}
    \item First item,
    \item Second item,
    \item Another item,
    \item I am losing count.
\end{itemize}


In a `pdf` the default symbol is $\bullet$.

---

- One can skip or simply change the numbering using `\setcounter`.
- You can nest `enumerate` and `itemize`, individually or together.

```latex
\begin{enumerate}
    \item Look at me.
    \item \begin{enumerate}
        \item I can make
        \item nested enumerates.
    \end{enumerate}
    \item So cool.
\end{enumerate}
```

\begin{enumerate}
    \item Look at me.
    \item \begin{enumerate}
        \item I can make
        \item nested enumerates.
    \end{enumerate}
    \item So cool.
\end{enumerate}

---

**Moving onto \LaTeX\ packages.**

# \LaTeX\ Packages

- \LaTeX\ packages are essential tools that enhance the functionality of \LaTeX.
- Packages are sets of additional commands and features that extend the capabilities of the basic \LaTeX\ system, often for specialized tasks.
- To include a package, one first needs it to be installed in the local machine---or one can use [Overleaf](https://www.overleaf.com/) (#StillNotSponspored) and avoid thinking about this.
- To use a \LaTeX\ package, you need to include it in the preamble of your
document.

```latex
\usepackage[<options>]{<package name>}
```

# Example Packages

- The first few lines of the [lecture notes](https://github.com/joshmaglione/CS3101-Notes/blob/main/Notes/LectureNotes.tex) look like

```latex
\documentclass[a4paper, 12pt]{article}
\usepackage{amsmath}
\usepackage{amsthm}
\usepackage{amssymb}
\usepackage{enumerate}
\usepackage{hyperref}
```

- Will mention a few packages that might be particularly relevant.

# The `amsmath` package

- One of the most useful packages for mathematical output.
- It provides numerous environments and commands for formatting equations, aligning mathematical expressions, and handling mathematical symbols.
- `align` environment. Also matrix environments like `matrix`, `pmatrix`, and `bmatrix`.

```latex
\[
    \begin{pmatrix}
        1 & 2 \\
        3 & 4 \\
    \end{pmatrix}
\]
```

$$
    \begin{pmatrix}
        1 & 2 \\
        3 & 4 \\
    \end{pmatrix}
$$

# The `amsthm` Package

- Specifically designed to facilitate the typesetting of theorems, lemmas, definitions, and similar structures in a document.
- Key features include:

1. **Theorem-like Environments:** Allows you to define new theorem-like
structures (like Theorem, Lemma, Corollary, Proposition, Definition,
Example, Remark).
1. **Customization:** Provides options to customize the style of theorem-like
environments, such as italicized or normal text, numbering, and shared or
independent counters.
1. **Proof Environment:** Offers a dedicated proof environment for
typesetting proofs, automatically adding a QED symbol at the end.

# More into `amsthm`

- One needs to first define the theorem-like environment in the preamble. 
- There are two main commands for doing this:

```latex
\newtheorem{<name>}{<printed output>}[<numbered within>]
\newtheorem{<name>}[<numbered like>]{<printed output>}
```

- As an example, we use the following in the lecture notes:
  
```latex
\newtheorem{theorem}{Theorem}[section]
```

- The enviornment name is `theorem`. It prints out 'Theorem', and it is numbered within the sections. 

# `amsthm` Example

```latex
\begin{theorem}
    The equation $x^n + y^n = z^n$ has no solution in 
    the positive integers for $n \geq 3$.
\end{theorem}
```

\begin{theorem}
	The equation $x^n + y^n = z^n$ has no solution in 
	the positive integers for $n \geq 3$.
\end{theorem}

- These slides don't do this example justice. 

# The `graphicx` package

- A powerful tool for including and manipulating graphics (or images) within documents.
- Extends the basic capabilities by providing commands for inserting images, scaling, rotating, and controlling their placement.

```latex
\begin{figure}
    \centering
    \includegraphics[scale=0.2]{imgs/Sherlock.jpg}
    \caption{My dog.}
\end{figure}
```

![My dog.](../imgs/Sherlock.jpg){ width=20% }

# Beyond...

- There are over 4000 packages for \LaTeX.
- A few honorable mentions:

1. `hyperref` : Enables references and citations to produce hyperlinks within the \texttt{pdf} file. (This file uses it.)
2. `listings` & `minted` : Displays code and pseudo-code in a structure block.
3. `siunitx` : For those working often with SI units, this can help manage it all.
4. `tikz` : Very powerful image producing package. The possibilities are stunning.