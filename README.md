# LaTeX Project Template for BA Bautzen Economics

This LaTeX project template adheres to the guidelines of BA Bautzen, specifically tailored for economics. It streamlines the process of creating professional and compliant documents for academic and professional use.

**Use it with your own responsibility.**

## Quickstart LaTeX

- [LaTeX Kurzstart DE](https://learnxinyminutes.com/docs/de-de/latex-de/)
- [LaTeX Quickstart EN](https://learnxinyminutes.com/docs/latex/)

## Custom Commands

### Modify Custom Commands

- Custom commands can be changed in `build/commands.sty`.
- Custom layout and package settings can be changed in `build/customization.sty`.

### Available Commands

- `\customtitlepage{path/to/logo.png}{scale}`: Generate a BA Bautzen title page.
- `\customauthorsabstract`: Generate an authors' abstract from the settings.

#### Explanation of the Command `\lawcite`

```latex
\lawcite[§ 1 Absatz 1 Satz 1]{citation key}
```

- This command is used to cite a specific section of a law.
- `[§ 164 Absatz 1 Satz 1]` is the optional argument specifying the section, paragraph, or sentence of the law.
- `{citation key}` is the mandatory argument, the citation key from the bibliography.

Ensure that law books are placed in `build/bib/law.bib`. Define the bibliography file in the preamble of your `main.tex` document as follows:

```latex
\addtocategory{law}{aktg1965, .....}
```

### Citing with `\autocite`

Example:

```latex
\autocite[pagenumber]{citation key}
```

## Structure

### Defining Sections and Subsections

Create sections and subsections in the `main.tex` document.

- Create a file in the `sections/` directory named `sectiontitle.tex`.
- Follow the structure provided in `sample.tex`; refer to `introduction.tex` as an example.
- Include this file in your main document using:

  ```latex
  \subfile{sections/introduction}
  ```

Place your images in the `images/` directory.

For changes, look into the `build/` directory.

### Using Attachments

If you need to add attachments in your LaTeX document, use the `attachment` environment. Below is an example:

```latex
\begin{attachment}[NameOfAttachment]
    Write your content here.
\end{attachment}
```

#### List in Attachments

To include lists in the attachments:

```latex
\begin{attachment}[NameOfAttachment2]
    \begin{customlistof}{0cm}{}
        Write list here
    \end{customlistof}
\end{attachment}
```

## LaTeX Packages Used

- `inputenc` (with utf8 encoding)
- `babel` (with german option)
- `amsmath`
- `amsfonts`
- `amssymb`
- `graphicx`
- `xcolor`
- `titling`
- `listings`
- `float`
- `lastpage`
- `setspace`
- `csquotes`
- `tikz`
- `helvet`
- `geometry` (with options: a4paper, left=40mm, right=20mm, top=20mm, bottom=20mm)
- `biblatex-chicago` (with options: backend=biber, authordate, ibidtracker=context)
- `fancyhdr`
- `acronym`
- `hyperref`
- `tocloft` (with titles option)
- `pdfpages`
- `cleveref`
- `lipsum`
- `microtype` (with final option)
- `caption`
- `subfiles`
- `glossaries`

## Notes

- Graphics paths are set using `\graphicspath`.
- Custom caption setup for figures and tables is configured using `\captionsetup`.
- Custom author definition command `\def\authorname`.
- Cleveref package is configured for German.
- Bibliography settings are defined, with resources added using `\addbibresource`.
- Page formatting and layout adjustments are made for better document appearance.