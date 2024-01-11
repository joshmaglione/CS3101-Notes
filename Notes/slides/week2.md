# Summary of LaTeX's Dynamic Bibliography Formatting with BibTeX

\LaTeX\ offers a significant advantage in dynamically formatting bibliographies and references, particularly through the use of BibTeX. BibTeX, developed by *Oren Patashnik* and *Leslie Lamport* in the 1980s, simplifies reference management in LaTeX documents.

# Key Advantages
- **Dynamic Bibliography Management**: Adding new references doesn't require manual reordering of the bibliography or updating numerous references. BibTeX automates these adjustments.
- **Simplified Citation Process**: Citations are easily added to the text using `\cite{<tag>}`. The bibliography is automatically formatted according to the chosen style.

# How BibTeX Works

To implement BibTeX, the following lines are included in the LaTeX document, usually at the end:
```latex
\bibliography{<bib file name>}
\bibliographystyle{<style>}
```

Using BibTeX alters the typical LaTeX compilation process.

- Run pdflatex, then bibtex twice, and pdflatex again.

[Overleaf](https://www.overleaf.com/) simplifies this process by including it in the whole compilation process.

# BibTeX Styles

- `plain`: This is one of the original BibTeX styles. It formats entries in a simple, straightforward manner and sorts them alphabetically by author.
- `alpha`: This style creates labels from the author's name and the year of publication. It's handy for author-year citations.
- `abbrv`: Similar to the plain style, but it abbreviates first names and journal names. It's useful for more compact bibliographies.
- `IEEEtran`: Used for formatting bibliographies in the style of the Institute of Electrical and Electronics Engineers (IEEE).
- `acm`: For formatting according to the style guidelines of the Association for Computing Machinery (ACM).

--- 

- `apa`: Adheres to the formatting guidelines of the American Psychological Association. Requires additional packages like `apacite`.
- `nature`: Mimics the citation style of the journal 'Nature'. This style is often used in scientific publications.
- `chicago`: This style follows the guidelines of the Chicago Manual of Style. Useful for humanities and social sciences.
- `mla`: Suitable for documents adhering to the Modern Language Association format, commonly used in the humanities.
- `amsplain`: Used for formatting in the style of the American Mathematical Society, particularly suitable for mathematics and related disciplines.

# The bib file

This file contains bibliography entries in a specific format.

Each entry includes details like title, author, publication year, and publisher.

Order is irrelevant.

Here's a sample:
```bibtex
@book{Macdonald1998,
  title={Symmetric functions and Hall polynomials},
  author={Macdonald, Ian Grant},
  year={1998},
  publisher={Oxford university press}
}
```

# Citing in the LaTeX Document

- For citations within the document, use 

    ```latex
    \cite[<options>]{<tag>} 
    ```



- Using our previous example, the tag was `Macdonald1998`.

    ```latex
    By \cite[Theorem 3.14]{Macdonald1998}, the proof 
    is complete. 
    ```

- Users need only to know the tags for the references they want to cite. BibTeX takes care of the rest. 