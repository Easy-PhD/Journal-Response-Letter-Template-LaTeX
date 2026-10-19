# Journal-Response-Letter-Template-LaTeX

This repository is adapted from [Journal-Response-Letter-Template-LaTeX](https://github.com/shellywhen/Journal-Response-Letter-Template-LaTeX).

## Summary of Changes in v2.0

- Added a table of contents.
- Added the ability to specify custom reviewer numbers (e.g., 2, 3, 4, 5, 7 without 1 and 6).

## Usage

To use the `responsereview.sty` package in your document, simply include the following line in your LaTeX document:

```latex
\usepackage[editor={Editor and Reviewers},
            journal={Name of the Journal},
            manuscript={Number/ID of the Manuscript}]{responsereview}
```

## Commands

The package provides the following commands.

### Editor and Reviewers

```latex
\editor
\reviewer
```

These commands start a new editor or reviewer section. Typical usage is as follows:

```latex
\begin{document}
...
\editor
Response to the editor

\reviewer{1}
Response to the first reviewer

\reviewer{3}
Response to the third reviewer
```

### Comments and Responses

```latex
\begin{generalcomment}
...
\end{generalcomment}
```

The `generalcomment` environment is intended for general comments made by the editor and reviewers.

```latex
\begin{revcomment}
...
\end{revcomment}
```

The `revcomment` environment is intended for individual comments made by the reviewers. Comments are numbered automatically.

It also accepts optional arguments, which are passed directly to the underlying `tcolorbox` environment. This is useful when you want to add specific arguments in particular situations, such as the `breakable` keyword for very long comments.

```latex
\begin{revresponse}[Optional Parameter]
...
\end{revresponse}
```

The `revresponse` environment is intended for responses to individual comments from the reviewers and editor. The optional parameter changes the text on the first line. By default, this text is "Thank you for the comment."

### Changes

```latex
\begin{changes}
...
\end{changes}
```

The `changes` environment is intended for indicating changes that you have made to your manuscript. It places the content in a box to highlight it for the reviewers.

### Bibliography

The `reviewresponse` package supports the use of `biblatex` for references. Simply include `biblatex` and use the `\cite` command in your response.

If you cite within a comment, please print the bibliography at the end of the response to that comment, you can use the `\printpartbibliography` command as follows:

```latex
\printbibliography[heading=subbibliography, title={}]
```
