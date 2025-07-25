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

### KI-Kennzeichnung und Compliance

**NEU:** Diese Vorlage bietet eine umfassende KI-Kennzeichnungsfunktionalität, die den aktuellen akademischen Standards und den Anforderungen der BA Bautzen entspricht.

#### KI-Funktionen aktivieren/deaktivieren

```latex
\enableAI    % Aktiviert alle KI-Funktionen
\disableAI   % Deaktiviert alle KI-Funktionen
```

**Wichtig:** KI-Funktionen müssen in der `main.tex` vor `\begin{document}` aktiviert werden.

#### Verfügbare KI-Kennzeichnungstypen

##### 1. Fußnoten-Kennzeichnung
Für Textabschnitte, die mit KI-Unterstützung erstellt wurden:

```latex
\aifootnote{KI-Tool}{Prompt-Beschreibung}{Datum}
```

**Beispiel:**
```latex
Dieser Absatz behandelt Marktanalysen.\aifootnote{ChatGPT 4.0}{Erkläre Grundlagen der Marktanalyse}{15.03.2024}
```

##### 2. Inline-Kennzeichnung
Für direkte Kennzeichnung im Text:

```latex
\aisection{KI-Tool}{Prompt-Beschreibung}{Datum}
```

**Beispiel:**
```latex
\aisection{Claude 3.5}{Erstelle Einführung in Digitalisierung}{16.03.2024}
Der folgende Abschnitt wurde mit KI-Unterstützung verfasst.
```

##### 3. Vollständige Absätze
Für komplett mit KI erstellte Textabschnitte:

```latex
\aiparagraph{KI-Tool}{Prompt-Beschreibung}{Datum}
Der komplette Absatzinhalt hier...
```

##### 4. Tabellen und Abbildungen
Für KI-generierte visuelle Inhalte:

```latex
\aitable{KI-Tool}{Prompt-Beschreibung}{Datum}
```

**Beispiel in einer Tabelle:**
```latex
\begin{table}[h]
    \centering
    \begin{tabular}{|c|c|}
        \hline
        Spalte 1 & Spalte 2 \\
        \hline
        Daten & Werte \\
        \hline
    \end{tabular}
    \caption{Umsatzdaten Q1 2024}
    \aitable{Excel Copilot}{Erstelle Umsatztabelle für Q1}{18.03.2024}
\end{table}
```

##### 5. Code-Generierung
Für mit KI generierten Programmcode:

```latex
\aicode{KI-Tool}{Prompt-Beschreibung}{Datum}
```

##### 6. Übersetzungen
Für KI-übersetzte Inhalte:

```latex
\aitranslation{KI-Tool}{Prompt-Beschreibung}{Datum}
```

##### 7. Zusammenfassungen
Für KI-erstellte Zusammenfassungen:

```latex
\aisummary{KI-Tool}{Prompt-Beschreibung}{Datum}
```

#### Automatische KI-Dokumentation

**Wichtige Neuerung:** Alle KI-Verwendungen werden automatisch gesammelt und dokumentiert.

##### Automatische KI-Anlage generieren
Am Ende des Dokuments (vor der Selbstständigkeitserklärung):

```latex
\printailist
```

Dieser Befehl erstellt automatisch eine vollständige Anlage mit allen verwendeten KI-Tools, Prompts und Daten. Die Ausgabe erfolgt nur, wenn KI-Funktionen aktiviert sind und tatsächlich verwendet wurden.

#### KI-Integration in die Selbstständigkeitserklärung

Die Vorlage passt die Selbstständigkeitserklärung automatisch an, wenn KI-Funktionen aktiviert sind:

```latex
% In der declaration of independence.tex wird automatisch hinzugefügt:
\ifuseAI
    \textbf{Bestandteile der Arbeit, die mittels Künstlicher Intelligenz entstanden sind, wurden ausdrücklich gekennzeichnet.}
\fi
```

#### Best Practices für KI-Kennzeichnung

1. **Spezifische Tool-Namen verwenden:** "ChatGPT 4.0", "Claude 3.5", "GitHub Copilot"
2. **Aussagekräftige Prompt-Beschreibungen:** Beschreiben Sie präzise, was vom KI-Tool verlangt wurde
3. **Exakte Datumsangabe:** Format TT.MM.JJJJ verwenden
4. **Vollständige Transparenz:** Alle KI-Nutzungen kennzeichnen, auch kleinste Unterstützungen

#### Compliance und Richtlinien

- ✅ **BA Bautzen konform:** Entspricht den aktuellen Richtlinien zur KI-Kennzeichnung
- ✅ **Automatische Sammlung:** Keine vergessenen KI-Verwendungen
- ✅ **Flexible Kennzeichnung:** Verschiedene Kennzeichnungsarten je nach Kontext
- ✅ **Prüferfreundlich:** Übersichtliche Dokumentation in separater Anlage

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

### Verwendung der TODO-Funktionalität

Diese Vorlage bietet eine erweiterte TODO-Funktionalität zur besseren Strukturierung und Verwaltung von Aufgaben innerhalb Ihres Dokuments.

#### Verfügbare TODO-Typen

1. Allgemeine TODOs: `\todo{Aufgabenbeschreibung}`
2. Ideen: `\idea{Ideenbeschreibung}`
3. Kritische Aufgaben: `\critical{Beschreibung der kritischen Aufgabe}`

#### TODO-Listen erstellen

Sie können strukturierte TODO-Listen mit der `todolist`-Umgebung erstellen:

```latex
\begin{todolist}
  \item \todo{Erste Aufgabe}
  \item \idea{Zweite Aufgabe (Idee)}
  \item \critical{Dritte Aufgabe (Kritisch)}
\end{todolist}
```

#### Definitionen
Um Definitionen zu schreiben nutze dies
```latex
\begin{definition}
Let \(f\) be a function whose derivative exists in every point, then \(f\) is 
a continuous function.
\end{definition}
```

#### Anzeigen aller TODOs

Um alle TODOs an einer bestimmten Stelle im Dokument anzuzeigen, verwenden Sie den Befehl:

```latex
\printtodos
```

Diese Funktion ist besonders nützlich, um am Ende des Dokuments oder in einem separaten Abschnitt eine Übersicht aller offenen Aufgaben zu erhalten.

#### TODOs deaktivieren
Um alle TODOS sofort zu deaktivieren inkl. dem \printtodos, verwenden Sie den Befehl:

```latex
\hideTodos
```

Am Anfang des Bodys im Dokuments

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
- `todonotes` (für TODO-Funktionalität)

### Hinweise

- Grafikenpfade werden mit `\graphicspath` gesetzt.
- Benutzerdefinierte Beschriftungseinstellungen für Abbildungen und Tabellen werden mit `\captionsetup` konfiguriert.
- Benutzerdefinierter Autoren-Definitionsbefehl `\def\authorname`.
- Cleveref-Paket ist für Deutsch konfiguriert.
- Bibliografieeinstellungen sind definiert, Ressourcen werden mit `\addbibresource` hinzugefügt.
- Seitenformatierungs- und Layoutanpassungen werden für ein besseres Dokumentenlayout vorgenommen.
- **KI-Funktionen sind optional und müssen explizit aktiviert werden.**

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

### AI Attribution and Compliance

**NEW:** This template provides comprehensive AI attribution functionality that meets current academic standards and BA Bautzen requirements.

#### Enable/Disable AI Functions

```latex
\enableAI    % Enables all AI functions
\disableAI   % Disables all AI functions
```

**Important:** AI functions must be activated in `main.tex` before `\begin{document}`.

#### Available AI Attribution Types

##### 1. Footnote Attribution
For text sections created with AI assistance:

```latex
\aifootnote{AI-Tool}{Prompt-Description}{Date}
```

**Example:**
```latex
This paragraph discusses market analysis.\aifootnote{ChatGPT 4.0}{Explain basics of market analysis}{15.03.2024}
```

##### 2. Inline Attribution
For direct attribution within text:

```latex
\aisection{AI-Tool}{Prompt-Description}{Date}
```

##### 3. Complete Paragraphs
For entirely AI-created text sections:

```latex
\aiparagraph{AI-Tool}{Prompt-Description}{Date}
The complete paragraph content here...
```

##### 4. Tables and Figures
For AI-generated visual content:

```latex
\aitable{AI-Tool}{Prompt-Description}{Date}
```

##### 5. Code Generation
For AI-generated code:

```latex
\aicode{AI-Tool}{Prompt-Description}{Date}
```

##### 6. Translations
For AI-translated content:

```latex
\aitranslation{AI-Tool}{Prompt-Description}{Date}
```

##### 7. Summaries
For AI-created summaries:

```latex
\aisummary{AI-Tool}{Prompt-Description}{Date}
```

#### Automatic AI Documentation

**Important Feature:** All AI usage is automatically collected and documented.

##### Generate Automatic AI Appendix
At the end of the document (before the declaration of independence):

```latex
\printailist
```

This command automatically creates a complete appendix with all used AI tools, prompts, and dates.

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

### Using the TODO Functionality

This template provides an enhanced TODO functionality for better structuring and managing tasks within your document.

#### Available TODO Types

1. General TODOs: `\todo{Task description}`
2. Ideas: `\idea{Idea description}`
3. Critical Tasks: `\critical{Critical task description}`

#### Creating TODO Lists

You can create structured TODO lists using the `todolist` environment:

```latex
\begin{todolist}
  \item \todo{First task}
  \item \idea{Second task (idea)}
  \item \critical{Third task (critical)}
\end{todolist}
```

#### Displaying All TODOs

To display all TODOs at a specific point in the document, use the command:

```latex
\printtodos
```

This feature is particularly useful for getting an overview of all open tasks at the end of the document or in a separate section.

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
- `todonotes` (for TODO functionality)

### Notes

- Graphics paths are set using `\graphicspath`.
- Custom caption setup for figures and tables is configured using `\captionsetup`.
- Custom author definition command `\def\authorname`.
- Cleveref package is configured for German.
- Bibliography settings are defined, with resources added using `\addbibresource`.
- Page formatting and layout adjustments are made for better document appearance.
- **AI functions are optional and must be explicitly enabled.**