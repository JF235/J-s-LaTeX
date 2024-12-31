
## bibtex vs. biblatex

https://www.overleaf.com/learn/latex/Bibliography_management_with_bibtex

https://www.overleaf.com/learn/latex/Bibliography_management_with_biblatex

If you are starting from scratch **we recommend using biblatex** because that package provides localization in several languages, it’s actively developed and makes bibliography management easier and more flexible. 

## Referências para cada seção

> More in: https://www.overleaf.com/learn/latex/Questions/Creating_multiple_bibliographies_in_the_same_document


### biblatex

1. You can have biblatex automatically start a new refsection when it encounters \chapter, by adding the refsection=chapter option when loading biblatex: 

```latex
\usepackage[natbib,style=authoryear,refsection=chapter]{biblatex}
\addbibresource{refs.bib}
```

2. You can then put a \printbibliography at the end of each \chapter, to list only the citations that had appeared since the last \chapter. In the code sample below, we also use the heading=subbibintoc option for \printbibliography, so that the bibliography is printed at the end of the chapter as an unnumbered section (subbib) rather than an unnumbered chapter; and such that it will be included in the table of contents (intoc). 

```latex
\chapter{First Chapter}

\section{Section Heading}
Here's a citation! \citep{latex:companion}
\printbibliography[heading=subbibintoc]


\chapter{Second Chapter}

\section{Section Heading}
Here's another citation! \citep{lshort}
\printbibliography[heading=subbibintoc]
```

3. Alternatively, you can put \begin{refsection}...\end{refsection} around each chapter, or around arbitrary blocks of text. Do not use the refsection=chapter option in this case