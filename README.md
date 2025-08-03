# CleanCV :soap: :sparkles:

**Modern, minimal, and modular LaTeX CV template for academics**

CleanCV is designed for academics, graduate students, and researchers in STEM. It prioritizes readability, ease-of-use, clean design, and exceptional typography. Contains everything you need and nothing you don't.

## Quick Start

### 1. Open in Overleaf
**[Create your CV in Overleaf](https://www.overleaf.com/docs?snip_uri=https://github.com/giladturok/CleanCV/archive/main.zip)** *(opens instantly, no downloads needed)*

### 2. Add Your Information
Replace the example content in `main.tex` with your own information and `publications.bib` with your publication list. Here's a quick example:

```latex
% Replace with your details
\cvname{Your Full Name}
\contactbar{yoursite.com}{you@email.com}{github-user}{linkedin}{scholar-url}{Your City}

% Add your education
\cvblock{Your University}{City, State}{Ph.D. in Your Field}{2020-2024}

% Add your experience
\cvblock[
    \item Your major achievement or research contribution
    \item Another accomplishment with measurable impact
]{Institution Name}{Location}{Your Position}{Years}
```

### 3. Compile and Download
Click "Recompile" in Overleaf → Download PDF → Done!

## Features

**�� Professional Typography**: ET Book font with carefully optimized spacing for maximum readability

**�� Easy Customization**: Change colors, sections, and styling without breaking anything

**�� Smart Publications**: Your `.bib` file automatically becomes a formatted publication list with your name highlighted in bold and co-first authors marked with an asterisk (*)

**�� Commented Style File**: `CleanCV.sty` is well-commented for easy understanding and modification

**�� Contact Integration**: Professional contact bar with icons for email, GitHub, LinkedIn, Google Scholar

**�� Dual Mode**: Generate both comprehensive CVs and condensed resumes from the same document

**⚡ Two-Command System**: `\cvblock` for detailed entries, `\cvitem` for simple lists — that's all you need to learn

**��️ Last-updated Date**: automatically generates last-updated date

## How It Works

CleanCV uses just two commands to handle all your CV content:

### `\cvblock` — For Important Entries
Use for education, experience, major projects. Supports optional bullet points.

```latex
\cvblock[
    \item Published 4 papers in top-tier conferences (ICML, NeurIPS)
    \item Mentored 3 undergraduate research assistants
    \item Received departmental teaching award
]{Stanford University}{Stanford, CA}{PhD Candidate in Computer Science}{2020-2024}
```

**Output:**

```text
Stanford University                                   Stanford, CA
PhD Candidate in Computer Science                        2020-2024
- Published 4 papers in top-tier conferences (ICML, NeurIPS)
- Mentored 3 undergraduate research assistants  
- Received departmental teaching award
```

### `\cvitem` — For List Entries
Use for awards, talks, service. Clean one-line format within lists.

```latex
\section*{Awards \& Honors}
\begin{itemize}
    \cvitem{NSF Graduate Research Fellowship}{National Science Foundation}{2021-2024}
    \cvitem{Best Paper Award}{ICML 2023}{June 2023}
    \cvitem{Outstanding TA Award}{Stanford CS Department}{Spring 2022}
\end{itemize}
```

**Output:**

```text
Awards & Honors
- Graduate Research Fellowship, National Science Foundation ··· 2021-2024
- Best Paper Award, ICML 2023 ································· June 2023
- Outstanding TA Award, Stanford CS Department ·············· Spring 2022
```

### When to Use Each Command
`\cvblock` and `\cvitem` handle most CV content, but not everything. Use your judgment:

**Use the commands for:**
- Education, experience, awards, talks, service, publications

**Don't use commands for:**
- Research interests, technical skills, brief personal statements
- Simple text paragraphs or comma-separated lists

```latex
% Good - use commands for structured entries
\section*{Awards}
\begin{itemize}
    \cvitem{Best Paper Award}{ICML 2023}{June 2023}
\end{itemize}

% Also good - plain text for skills  
\section*{Technical Skills}
\textbf{Programming:} Python, R, MATLAB, C++ \\
\textbf{ML Frameworks:} PyTorch, TensorFlow, Scikit-learn \\
\textbf{Tools:} Git, Docker, Slurm, LaTeX
```

## Customize

### Manage CV Sections
Add, remove, or reorder sections as needed. The template includes these sections by default (some of which have their own subsections):
- `Research Interests`, `Education`, `Experience`, `Awards & Honors`, `Publications`, `Skills`, `Talks & Presentations`, `Teaching`, `Mentoring`, `Service`, `Media Coverage`

Here's an example of a new section with subsections:

```latex
\section*{Hobbies} % Add a new section

\subsection*{Travel} % Add a subsection
\begin{itemize}
    \cvitem{Europe}{Visited 10 countries, focusing on cultural heritage}{2019}
    \cvitem{Asia}{Explored diverse landscapes and traditions}{2021}
\end{itemize}

\subsection*{Cooking} % Another subsection
\begin{itemize}
    \cvitem{Italian Cuisine}{Specialized in pasta and sauces}{2015-present}
    \cvitem{Baking}{Cakes, pastries, and bread-making}{2018-present}
\end{itemize}
```

### Change Colors and Styling
Edit key styling options in `CleanCV.sty`:
```latex
% Change primary color theme
\definecolor{primary}{RGB}{83, 39, 115}  % Default purple
\definecolor{primary}{RGB}{0, 102, 204}   % Academic blue  
\definecolor{primary}{RGB}{153, 51, 102}  % Professional burgundy

% Adjust page margins
\geometry{
  letterpaper,          % Or a4paper
  left=2.5cm,           % Left margin
  right=2.5cm,          % Right margin  
  top=2cm,              % Top margin
  bottom=2.5cm          % Bottom margin
}

% Modify spacing
\setlength{\parskip}{0.2em}                    % Paragraph spacing
\titlespacing*{\section}{0pt}{1.5em}{0.5em}    % Section spacing
```

### CV vs Resume Mode
Generate different versions by editing the top of `main.tex`:
```latex
\cvtrue   % Full academic CV (includes all sections)
\cvfalse  % Condensed resume (excludes \ifcv...\fi sections)
```

Wrap optional sections in conditional blocks:
```latex
\ifcv
\section*{Teaching Experience}  % Only appears in CV mode
\cvblock{Course Name}{University}{Instructor}{Semester}
\fi
```

### Customize Contact Bar
Modify the contact bar by editing icons or removing sections in `main.tex`:
```latex
% Standard contact bar
\contactbar{yoursite.com}{you@email.com}{github-user}{linkedin}{scholar-url}{Your City}

% Skip unused platforms by leaving empty
\contactbar{yoursite.com}{you@email.com}{}{linkedin}{}{Your City}
```

### Your Publications, Automatically
CleanCV uses BibLaTeX to manage your publication list with two special features:

**Name Highlighting**: Your name appears bold in every publication
```latex
% In main.tex - must match your name exactly in .bib file
\boldname{YourLast}{YourFirst}{Initial}
```

**Joint First Authors**: Mark co-first author papers with asterisks
```latex
% In publications.bib - add this annotation
@article{yourpaper2023,
    title={Your Amazing Research},
    author={Your Name and Collaborator Name},
    journal={Nature},
    year={2023},
    annote={jointfirst}  % This adds the asterisk: Your Name*
}
```

## User Gallery

CleanCV is used by researchers and academics worldwide. Here are some examples:

- [Gilad Turok](https://giladturok.com/cv) - Computer Vision Researcher
- [Jane Doe](https://janedoe.com/cv) - Machine Learning Engineer
- [John Smith](https://johnsmith.com/cv) - Data Scientist

**Using CleanCV for your CV?** We'd love to feature you! [Open an issue](https://github.com/giladturok/CleanCV/issues) with a link to your CV (or a screenshot) and we'll add you to our gallery. 

*Don't forget to [⭐ star the repo](https://github.com/giladturok/CleanCV) to help others discover CleanCV!*

## Advanced Usage

**Want more control?** Clone the repository locally to:
- Use with your preferred LaTeX editor
- Track changes with Git  
- Customize the style file extensively

```bash
git clone https://github.com/giladturok/CleanCV.git
cd CleanCV
pdflatex main.tex && biber main && pdflatex main.tex
```

## Acknowledgments

CleanCV builds upon excellent foundational work by [Dr. Bastian Rieck](https://github.com/Pseudomanifold/latex-cv) and [Dr. Corey Stephan](https://github.com/historical-theology/cv), enhanced for modern academic workflows with improved usability and maintainability.