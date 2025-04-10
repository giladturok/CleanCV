# CleanCV :soap: : Modern, mimimal, & modular academic CV

CleanCV is a modern, minimal, and modular LaTeX CV designed for academics, students, and researchers.

This template prioritizes readability and clean typography while making it easy to maintain and update your CV.

## Features :sparkles:

CleanCV stands out from other academic templates with:

- **Simple style file** with comments you'll actually understand
- **Exceptional typography** using elegant spacing and ET Book font
- **Contact bar with icons** supporting personal info and social media
- **Modular structure** with two main entry types for all content
- **CV/Resume dual mode** with conditional section display
- **Easy customization** of colors and style
- **Automatic last-updated date**
- **BibLaTeX integration** for seamless use with `publications.bib`
- **Automatic name bolding** for your name in publications
- **Support for joint first author** annotations

## Setup :rocket:

### Option 1: Use on Overleaf (Recommended)
1. Create a [new Overleaf project](https://www.overleaf.com/learn/how-to/Creating_a_document_in_Overleaf)
2. Copy the `main.tex`, `cleanCV.sty`, and `publications.bib` files to your Overleaf project

If you have Overleaf premium, you can instead use this template to create a new Github repo and sync it directly with Overleaf ([instructions](https://www.overleaf.com/learn/how-to/GitHub_Synchronization#Creating_a_new_Overleaf_project_from_a_GitHub_repository)).

### Option 2: Use Locally
1. Install Tex/LaTeX ([get LaTeX](https://www.latex-project.org/get/))
2. Create a new Github repo by using this template
3. Clone your new Github repo locally: `git clone https://github.com/yourusername/CleanCV.git`

## Philosophy

CleanCV is built around a simple, consistent structure:

1. \textbf{Sections:} Main content divisions (Education, Experience, etc.)
2. \textbf{Subsections:} Optional subdivisions within sections (e.g., Posters under Talks or Peer Review under Service)
3. \textbf{Entries:} Individual items in each section using one of two standardized commands

Every entry in your CV will use one of two commands, creating a consistent visual hierarchy:

`\cventry`: For primary entries with organization, location, role, date, and optional description (in bullet point form)
`\cvitem`: For simpler entries with institution, name, and date that is often an item in a bullet-point list

This consistency makes your CV both visually appealing and easy to maintain.

## Usage Guide

### Basic Content Commands

CleanCV provides two primary commands for adding content:

#### 1. `\cventry` - For detailed entries (education, experience)

```latex
\cventry[
    \item First bullet point about this position
    \item Second bullet point with accomplishments
]{Institution/Company}{Location}{Role/Degree}{Year/Date Range}
```

For entries without bullet points, leave the first argument empty:

```latex
\cventry{University Name}{City, Country}{Degree Program}{2018-2022}
```

#### 2. `\cvitem` - For simple entries (awards, talks, etc.)

```latex
\cvitem{Organization}{Award/Talk Name}{Year}
```

### Section Examples

#### Education Section

```latex
\section*{Education}

\cventry{Princeton University}{Princeton, NJ, USA}{Ph.D. in Physics}{1934-1938}
\medskip
\cventry{MIT}{Cambridge, MA}{M.Sc. in Mathematics}{1932-1934}
```

#### Awards Section

```latex
\section*{Awards & Honors}

\begin{itemize}
    \item \cvitem{National Science Foundation}{Graduate Research Fellowship}{2023}
    \item \cvitem{University of Michigan}{Outstanding Thesis Award}{2022}
\end{itemize}
```

### Bibliography Management

CleanCV automatically integrates with BibLaTeX for publication lists.

1. Make your name bold in the bibliography:
   ```latex
   \boldname{YourLastName}{YourFirstName}{Y}
   ```

2. Mark joint first-authors in your .bib file:
   ```
   @article{keyname,
     title={Paper Title},
     author={Your Name and Colleague Name},
     journal={Journal Name},
     year={2023},
     annote={jointfirst}
   }
   ```

3. Display your bibliography:
   ```latex
   \section*{Publications}
   \nocite{*}
   \printbibliography[heading=none]
   ```

### CV/Resume Mode

Switch between a comprehensive CV or a condensed resume:

```latex
\cvtrue  % Full CV with all sections
\cvfalse % Resume with limited sections
```

## �� Acknowledgments

CleanCV is inspired by various academic CV templates with a focus on simplicity, elegance, and readability.