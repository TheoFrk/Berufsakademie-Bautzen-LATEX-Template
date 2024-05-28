This is a LaTeX project template that adheres to the guidelines of BA Bautzen, specifically tailored for economics. This template streamlines the process of creating professional and compliant documents for academic and professional use. 

Use it with your own responsibility

Quickstar LATEX:
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
