# HogwartsCV: A Clean Academic CV Template for LaTeX ��

HogwartsCV is a minimalist, elegant LaTeX template for academic CVs and resumes designed for researchers, professors, and graduate students.

![HogwartsCV Preview](preview.png)

## ✨ Features

- **Clean, professional design** with focus on readability and content
- **Customizable primary color** to match your personal brand
- **Comprehensive sections** for academic profiles:
  - Research interests
  - Education
  - Experience
  - Publications (with BibLaTeX integration)
  - Awards & honors
  - Skills
  - Talks & presentations
  - Teaching
  - Service
  - Code & software projects
- **Dual modes**: Full CV mode (all sections) or Resume mode (limited sections)
- **Contact bar** with professional links and location
- **Bold name highlighting** in publication lists
- **Joint first-author** marking with asterisks
- **Elegant typography** using ET Book font
- **Hyperlinked content** for easy navigation
- **Automatic "Last Updated" date** in footer

## �� Requirements

- A LaTeX distribution (TeXLive, MiKTeX, etc.)
- LuaLaTeX or XeLaTeX compiler (recommended)
- BibLaTeX and Biber (for bibliography)

## �� Quick Start

1. Clone this repository:
   ```bash
   git clone https://github.com/yourusername/HogwartsCV.git
   ```

2. Copy `HogwartsCV.sty` to your project directory or LaTeX path

3. Create your CV based on the template:
   ```latex
   \documentclass[letterpaper,11pt]{article}
   \usepackage{HogwartsCV}
   
   % Choose between CV and Resume mode
   \cvtrue  % For full CV (all sections)
   % \cvfalse % For Resume (limited sections)
   
   % Import your publications
   \addbibresource{publications.bib}
   
   \begin{document}
   
   % Your name
   \cvname{Your Name}
   
   % Make your name bold in bibliography
   \boldname{LastName}{FirstName}{FirstInitial}
   
   % Contact information
   \contactbar{your.website.com}{email@example.com}{github-username}{linkedin-username}{https://scholar.google.com/citations?user=YOUR_ID}{Your Location}
   
   % Rest of your CV...
   
   \end{document}
   ```

4. Compile with LuaLaTeX or XeLaTeX:
   ```bash
   lualatex your_cv.tex
   biber your_cv
   lualatex your_cv.tex
   ```

## �� Usage Guide

### Contact Bar

The contact bar displays your professional information with icons:

```latex
\contactbar{website}{email}{github}{linkedin}{google-scholar-url}{location}
```

### Education & Experience Entries

Use the `\cventry` command for education and experience entries:

```latex
\cventry[
    \item First bullet point
    \item Second bullet point
]{Institution/Company}{Location}{Role/Degree}{Year/Date Range}
```

Leave the first argument empty for entries without bullet points.

### Awards, Talks, etc.

Use the `\cvitem` command for simple entries:

```latex
\cvitem{Organization}{Award/Talk Name}{Year}
```

### Bibliography

1. Create a `publications.bib` file with your publications
2. Make your name bold in the bibliography:
   ```latex
   \boldname{YourLastName}{YourFirstName}{Y}
   ```
3. Mark joint first-authors with the `jointfirst` annotation in your BibTeX entries

### CV/Resume Mode

Choose between full CV or condensed resume:

```latex
\cvtrue  % Full CV with all sections
\cvfalse % Resume with limited sections
```

## �� License

This template is available under the MIT License. See the LICENSE file for details.

## �� Acknowledgments

HogwartsCV is inspired by various academic CV templates with a focus on simplicity, elegance, and readability.