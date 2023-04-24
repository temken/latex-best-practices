# Best practices for scientific writing in $\LaTeX$
A collection of proposed best practices for scientific writing in $\LaTeX$.
These are only suggestions, and therefore subjective. Consistency should always go before following any set of rules to the letter.

## Text layout

- The layout and spacing of the text should be left to $\LaTeX$ wherever possible. Commands such as `\vspace{}`, `\medskip`, `\newline`, and `\clearpage` should be used sparingly, if at all. 
  
- Avoid line breaks at undesirable locations by using the `~` symbol. For example,
    - between numbers and units, i.e. `for 10~meters`, or
    - before references, `as seen in Eq.~\eqref{eq: x}` or `as derived in Ref.~\cite{x}`.

- By default, $\LaTeX$ adds more space between sentences than between words. If a full stop appears in the middle of a sentence, such as in `e.g.`, $\LaTeX$ will erroneously add extra space. You should avoid this by using the backslash `\` to force a normal-sized space: `e.g.\`. Alternatively, you can set the space between sentences and between words to be the same, by using the `\frenchspacing` command at the start of the document.

- Opening and closing quotation marks are not the same. Use ```  and `'` for opening and closing single quotation marks, and use ```` and `"` for double.
  
```math
    \text{"example"} \longleftarrow \textcolor{red}{\text{bad}}\, , \\
    \text{``example"} \longleftarrow\textcolor{ForestGreen}{\text{better}}\, .
```

- $\LaTeX$ does not treat a
    newline in the source code as a new paragraph. Instead, blank line should be added for a new paragraph. For readability, extra spacing in the source code can be added (without starting new paragraphs) by adding a line containing only a comment starting with `%`.

```
Sentence 1.
%
Sentence 2.
```

## Equation layout

- Equations should be incorporated into the text including **punctuation** at the end of the equations. For example,
```math
        a^2 +b^2 = c^2 \, .
```
- Furthermore, there should be an empty space between the last line of the equations and the period/comma using `\,,` or `\,.`.
- The content of brackets should not exceed the height of the brackets themselves.
```math
    (\frac{1}{2}) \longleftarrow \textcolor{red}{\text{bad}}\, ,\\
    \left(\frac{1}{2}\right) \longleftarrow\textcolor{ForestGreen}{\text{better}}\, .
```
This can be achieved by either using the `\left(` and `\right)` environment, or by stating the bracket sizes explicitly using e.g. `\bigg(` (This is necessary when line breaks occur within the brackets). For more details, see [this guide](https://www.overleaf.com/learn/latex/Brackets_and_Parentheses).
- The differential operator should not be italic.
```math
        \int dx  \longleftarrow \textcolor{red}{\text{bad}}\, ,\\
        \int \mathrm{d}x  \longleftarrow\textcolor{ForestGreen}{\text{better}}\, .
```
This can be achieved by `\mathrm{d}`. It can also make sense to define a command in the preamble, `\newcommand{\dd}{\mathrm{d}}`, for convenience.
- Furthermore, there should be an empty space between the integrand and the differential operator (using `\,.` or `\,.`, as above). 
- Subscripts that are words (or abreviations of words) should not be italic, but in an `\mathrm` environment.
```math
        N_{particles} \longleftarrow \textcolor{red}{\text{bad}}\, ,\\
        N_\mathrm{particles} \longleftarrow\textcolor{ForestGreen}{\text{better}}\, .
```
Here, we wrote `N_\mathrm{particles}`, no need for extra brackets.

## Figures

- It generally looks best to have figures at the top or bottom of a page (rather than floating in the text). For this, use the placement options `tb`:
 ```   
    \begin{figure}[tb]
    \includegraphics{...}
    \end{figure}
```
- In a two-column document, it can be an idea to use a `figure*` environment, which will add the figure at the top over the entire page.

## References

- Reference labels should be descriptive, including an indicator for what the reference is for. If the reference is for 
    - an equation: `\label{eq:...}`,
    - a figure: `\label{fig:...}`,
    - a table: `\label{tab:...}`,
    - a section: `\label{sec:...}`,
    - a sub-section: `\label{ss:...}`,
    - a sub-sub-section: `\label{sss:...}`, or
    - an appendix: `\label{app:...}`.
- Ideally the label should be short and intuitive, such that they be reproduced later on. (Editors like e.g. overleaf help with this.)
    - Bad example: `\label{abc}`.
    - Better example: `\label{eq: pythagorean theorem}`.
- There is a command specifically for referring to equations - `\eqref{}` - that automatically adds brackets. So instead of writing `in Eq.~(\ref{eq: x})`, this can be simplified to `in Eq.~\eqref{eq: x}`.
- When a reference (e.g. `Sec.~3.1 introduced ...`) appears at the start of a sentence, the word should be written out in full (i.e. `Section 3.1 introduced...`).

## Authors
(in alphabetical order)
- T. Emken
- B. J. Kavanagh
