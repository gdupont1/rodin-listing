# LaTeX Package for Rendering Event-B Code

Based on `lstlisting`.

## Basic usage

Just input the `rodinlisting.tex` file:
```latex
\input{rodinlisting}
```

This file defines the `eventb` language, that can be summoned as any language in
an `lstlisting` environment:
```latex
\begin{lstlisting}[language=eventb]
VARIABLE x
INVARIANTS
 inv1: x : INT
EVENTS
 INITIALISATION
 THEN
  act1: x := 0
 END
END
```

It is **highly recommended** to enable `mathescape` in the listing, so that you 
can simply write Event-B formulas directly in the listing:
```latex
...
\lstset{
    ... % Other configuration
    mathescape=true
}
...
\begin{lstlisting}[language=eventb]
VARIABLE $v$
INVARIANTS
 inv1: $v \in \mathbb{Z}$
\end{lstlisting}
```

## Supported elements

`rodinlisting` adds syntax highlighting for pretty much every keywords of the
Event-B language (and the Theory language).

Tags (`ordinary`, `convergent`, `theorem`, etc.) are also highlighted, and
belong to their own keyword group (so they can be styled differently).

The syntax also supports comments with `--`.

`rodinlisting` also defines symbols that are missing from LaTeX (i.e. "the weird
arrows"):
 * `\leftleftrightarrow` for the total relation (`<<->`)
 * `\leftrightrightarrow` for the surjective relation (`<->>`)
 * `\leftleftrightrightarrow` for the total surjective relation (`<<->>`)
 * `\lhdminus` for domain subtraction (`<<|`)
 * `\rhdminus` for range subtraction (`|>>`)
 * `\lhdplus` for relational override (`<+`)
 * `\partialrightarrow` for partial function (`+->`)
 * `\partialrightarrowtail` for partial injection (`>+>`)
 * `\partialtwoheadrightarrow` for partial surjection (`+->>`)
 * `\twoheadrightarrowtail` for bijection (`>->>`)

 Other symbols can be achieved using the standard LaTeX packages (in particular
 `amssymb`, already imported by `rodinlisting`).

## Example

An example is available in `example.tex`, and the corresponding render is found
in `example.pdf`.



