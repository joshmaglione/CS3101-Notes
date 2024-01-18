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

![](rabbit.jpg)

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
