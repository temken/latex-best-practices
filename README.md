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

## References

## Authors
(in alphabetical order)
- T. Emken
- B. J. Kavanagh
