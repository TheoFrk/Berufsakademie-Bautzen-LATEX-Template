This is a LaTeX project template that adheres to the guidelines of BA Bautzen, specifically tailored for economics. This template streamlines the process of creating professional and compliant documents for academic and professional use. 

Use it with your own responsibility

Quickstart LATEX:
- [LaTeX Kurzstart DE](https://learnxinyminutes.com/docs/de-de/latex-de/)
- [LaTeX Quickstart EN](https://learnxinyminutes.com/docs/latex/)

# Custom Commands

Change Custom Commands in `build/commands.sty`  
Change Custom Layout and Package Settings in `build/customization.sty`

## Custom Commands

- `\customtitlepage{path/to/logo.png}{scale}` - Generate BABautzen Title Page
- `\customauthorsabstract` - Generate Authorsabstract out of Settings

### Explanation of the command `\lawcite`

`\lawcite[§ 1 Absatz 1 Satz 1]{citation key}`

- This command is used to cite a specific section of a law.
- `[§ 164 Absatz 1 Satz 1]` is the optional argument, specifying the section, paragraph, or sentence of the law.
- `{citation key}` is the mandatory argument, the citation key from the bibliography.

It is important to place the lawbooks in `build/bib/law.bib`.  
Ensure that you define the bibliography file in the preamble of your `main.tex` document as follows:  
`\addtocategory{law}{aktg1965, .....}`

### Use `\autocite` for citing

Example: `\autocite[pagenumber]{citation key}`

# Structure

Defining Sections and Subsections in the `main.tex` document. 

Create a file in the `sections/` directory named `sectiontitle.tex`. The main structure should follow the format provided in `sample.tex`; refer to `introduction.tex` as an example. To include this file in your main document, use the command `\subfile{sections/introduction}` in your main document.


Put your images in `images/`

For Changes look into 'build/' 

### Used Packages

# LaTeX Packages Used

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

