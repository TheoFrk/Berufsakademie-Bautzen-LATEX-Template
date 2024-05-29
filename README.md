# LaTeX Projektvorlage für BA Bautzen Wirtschaft

Diese LaTeX-Projektvorlage entspricht den Richtlinien der BA Bautzen, speziell zugeschnitten für die Wirtschaftswissenschaften. Sie vereinfacht den Prozess der Erstellung professioneller und richtlinienkonformer Dokumente für akademische und berufliche Zwecke.

**Verwenden Sie sie auf eigene Verantwortung.**

## Sprachauswahl

Für die deutsche Version dieses Dokuments, klicken Sie hier: [Deutsch](#deutsche-version)

For the English version of this document, click here: [English](#english-version)

---

## Deutsche Version

### LaTeX Schnellstart

- [LaTeX Kurzstart DE](https://learnxinyminutes.com/docs/de-de/latex-de/)
- [LaTeX Quickstart EN](https://learnxinyminutes.com/docs/latex/)

### Benutzerdefinierte Befehle

#### Benutzerdefinierte Befehle ändern

- Benutzerdefinierte Befehle können in `build/commands.sty` geändert werden.
- Benutzerdefinierte Layout- und Paket-Einstellungen können in `build/customization.sty` geändert werden.

#### Verfügbare Befehle

- `\customtitlepage{path/to/logo.png}{scale}`: Erstellt eine Titelseite für die BA Bautzen.
- `\customauthorsabstract`: Erstellt ein Autorenreferat aus den Einstellungen.

##### Erklärung des Befehls `\lawcite`

```latex
\lawcite[§ 1 Absatz 1 Satz 1]{citation key}
```

- Dieser Befehl wird verwendet, um einen spezifischen Abschnitt eines Gesetzes zu zitieren.
- `[§ 164 Absatz 1 Satz 1]` ist das optionale Argument, das den Abschnitt, Absatz oder Satz des Gesetzes angibt.
- `{citation key}` ist das obligatorische Argument, der Zitierungsschlüssel aus der Bibliografie.

Stellen Sie sicher, dass Gesetzbücher in `build/bib/law.bib` abgelegt werden. Definieren Sie die Bibliografiedatei in der Präambel Ihres `main.tex` Dokuments wie folgt:

```latex
\addtocategory{law}{aktg1965, .....}
```

#### Zitieren mit `\autocite`

Beispiel:

```latex
\autocite[Seitenzahl]{citation key}
```

### Struktur

#### Definition von Abschnitten und Unterabschnitten

Erstellen Sie Abschnitte und Unterabschnitte im `main.tex` Dokument.

- Erstellen Sie eine Datei im Verzeichnis `sections/` mit dem Namen `sectiontitle.tex`.
- Folgen Sie der Struktur in `sample.tex`; siehe `introduction.tex` als Beispiel.
- Binden Sie diese Datei in Ihr Hauptdokument ein mit:

  ```latex
  \subfile{sections/introduction}
  ```

Legen Sie Ihre Bilder im Verzeichnis `images/` ab.

Für Änderungen schauen Sie in das Verzeichnis `build/`.

### Verwendung von Anlagen

Wenn Sie Anhänge in Ihrem LaTeX-Dokument hinzufügen müssen, verwenden Sie die Umgebung `attachment`. Unten ist ein Beispiel:

```latex
\begin{attachment}[NameOfAttachment]
    Schreiben Sie hier Ihren Inhalt.
\end{attachment}
```

#### Listen in Anhängen

Um Listen in Anhängen einzufügen:

```latex
\begin{attachment}[NameOfAttachment2]
    \begin{customlistof}{0cm}{}
        Schreiben Sie hier die Liste
    \end{customlistof}
\end{attachment}
```

### Verwendung von Akronymen

Akronyme werden in `build/acronyms` eingegeben. Allgemeiner Syntax:

```latex
\newacronym{ai}{AI}{Artificial Intelligence}
```

- `\newacronym{ai}{AI}{Artificial Intelligence}` definiert ein neues Akronym.
- `{ai}` ist der Schlüssel, der innerhalb des Dokuments verwendet wird.
- `{AI}` ist die Kurzform des Akronyms.
- `{Artificial Intelligence}` ist die ausführliche Beschreibung.

### Verwendete LaTeX-Pakete

- `inputenc` (mit UTF-8 Kodierung)
- `babel` (mit der Option german)
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
- `geometry` (mit den Optionen: a4paper, left=40mm, right=20mm, top=20mm, bottom=20mm)
- `biblatex-chicago` (mit den Optionen: backend=biber, authordate, ibidtracker=context)
- `fancyhdr`
- `acronym`
- `hyperref`
- `tocloft` (mit der Option titles)
- `pdfpages`
- `cleveref`
- `lipsum`
- `microtype` (mit der Option final)
- `caption`
- `subfiles`
- `glossaries`

### Hinweise

- Grafikenpfade werden mit `\graphicspath` gesetzt.
- Benutzerdefinierte Beschriftungseinstellungen für Abbildungen und Tabellen werden mit `\captionsetup` konfiguriert.
- Benutzerdefinierter Autoren-Definitionsbefehl `\def\authorname`.
- Cleveref-Paket ist für Deutsch konfiguriert.
- Bibliografieeinstellungen sind definiert, Ressourcen werden mit `\addbibresource` hinzugefügt.
- Seitenformatierungs- und Layoutanpassungen werden für ein besseres Dokumentenlayout vorgenommen.

---

## English Version

### Quickstart LaTeX

- [LaTeX Kurzstart DE](https://learnxinyminutes.com/docs/de-de/latex-de/)
- [LaTeX Quickstart EN](https://learnxinyminutes.com/docs/latex/)

### Custom Commands

#### Modify Custom Commands

- Custom commands can be changed in `build/commands.sty`.
- Custom layout and package settings can be changed in `build/customization.sty`.

#### Available Commands

- `\customtitlepage{path/to/logo.png}{scale}`: Generate a BA Bautzen title page.
- `\customauthorsabstract`: Generate an authors' abstract from the settings.

##### Explanation of the Command `\lawcite`

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

#### Citing with `\autocite`

Example:

```latex
\autocite[pagenumber]{citation key}
```

### Structure

#### Defining Sections and Subsections

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

### Using Acronyms

Acronyms are entered in `build/acronyms`. General syntax:

```latex
\newacronym{ai}{AI}{Artificial Intelligence}
```

- `\newacronym{ai}{AI}{Artificial Intelligence}` defines a new acronym.
- `{ai}` is the key used within the document.
- `{AI}` is the short form of the acronym.
- `{Artificial Intelligence}` is the full description.

### LaTeX Packages Used

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

### Notes

- Graphics paths are set using `\graphicspath`.
- Custom caption setup for figures and tables is configured using `\captionsetup`.
- Custom author definition command `\def\authorname`.
- Cleveref package is configured for German.
- Bibliography settings are defined, with resources added using `\addbibresource`.
- Page formatting and layout adjustments are made for better document appearance.
```
