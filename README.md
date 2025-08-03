# CleanCV :sparkles: :page_facing_up:

**Modern, minimal, and modular LaTeX CV template**

Most academic CV templates are overcomplicated or ugly. CleanCV gives you professional typography, clean design, enhanced readability, and advanced features — so you can focus on your research, not formatting.

See a preview of the example CV (*content generated with Claude*):

<p align="center">
  <img src="assets/pg1_example_cv.svg" width="47%" />
  <img src="assets/pg2_example_cv.svg" width="47%" />
</p>

> [!TIP]
> :star: Consider giving CleanCV a star on Github to help others discover this template

## Quick Start

1. **[Create your CV instantly in Overleaf](https://www.overleaf.com/docs?snip_uri=https://github.com/giladturok/CleanCV/archive/main.zip)** — Click to open a new project with CleanCV pre-loaded
2. **Replace example content** — Update `main.tex` with your information and `publications.bib` with your publication list

*To set up your own GitHub repository with version control, see the [Create Your Own Repository](#create-your-own-repository) section below.*

## Features

- **:book: Professional Typography**: ET Book font with carefully optimized spacing for maximum readability

- **:wrench: Easy Customization**: Change colors, sections, and styling without breaking anything

- **:books: Smart Publications**: Your `.bib` file automatically becomes a formatted publication list with your name highlighted in bold and joint first-authors marked with an asterisk (*)

- **:memo: Commented Style File**: `CleanCV.sty` is well-commented for easy understanding and modification

- **:bust_in_silhouette: Contact Integration**: Professional contact bar with icons for email, GitHub, LinkedIn, Google Scholar

- **:arrows_counterclockwise: CV/Resume Dual Mode**: Generate both comprehensive CVs and condensed resumes from the same document

- **:zap: Two-Command System**: `\cvblock` for detailed entries, `\cvitem` for simple lists — that's all you need to learn

- **:clock10: Last-updated Date**: automatically generates last-updated date

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

Instead of one-size-fits-all formatting, CleanCV lets you choose the right command for each type of content. Different information deserves different presentation.

**`\cvblock`** — Major entries with details (education, experience, projects)  
**`\cvitem`** — List entries (awards, talks, service)  
**Plain text** — Simple content (skills, interests)

> [!TIP]
> When in doubt: Need bullet points or multiple lines? Use `\cvblock`. Single line in a list? Use `\cvitem`. Just text? Use neither.

```latex
% List entries
\section*{Awards}
\begin{itemize}
    \cvitem{Best Paper Award}{ICML 2023}{June 2023}
\end{itemize}

% Plain text for skills  
\section*{Technical Skills}
\textbf{Programming:} Python, R, MATLAB, C++ \\
\textbf{Tools:} Git, Docker, Slurm, LaTeX

### When to Use Each Command

CleanCV gives you flexibility to format content appropriately rather than forcing everything into the same template. The key is matching the command to the type of information:

**`\cvblock`** is for entries that need prominence and detail — your major positions, degrees, and projects. These typically have multiple pieces of information (institution, location, title, dates) and often include bullet points describing your accomplishments.

**`\cvitem`** is for list entries where you want consistent, clean formatting — awards, talks, or service roles. These work well in a list where each item has a brief description and a date or location aligned to the right.

**Plain text** works best for simple content like research interests, skill lists, or short statements that don't need special formatting.

The goal is natural structure: important entries get `\cvblock` treatment, list items get `\cvitem` formatting, and everything else stays as readable text.

> [!TIP]
> When in doubt, ask: "Does this entry need bullet points or multiple lines?" If yes, use `\cvblock`. If it's a single line in a list, use `\cvitem`. If it's just text, use neither.

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
% Everything between \ifcv and \fi only appears when \cvtrue is set
% Use this to hide detailed sections in resume mode
\section*{Teaching Experience}  % Only appears in CV mode
\cvblock{Course Name}{University}{Instructor}{Semester}
\fi  % Ends the conditional block
```

### Customize Contact Bar
Modify the contact bar by editing icons or removing sections in `main.tex`:
```latex
% Standard contact bar
\contactbar{yoursite.com}{you@email.com}{github-user}{linkedin}{scholar-url}{Your City}

% Skip unused platforms by leaving empty
\contactbar{yoursite.com}{you@email.com}{}{linkedin}{}{Your City}
```

### Name Highlighting in Publications
Your name appears bold in every publication automatically:
```latex
% In main.tex - must match your name exactly in .bib file
\boldname{YourLast}{YourFirst}{Initial}
```

> [!IMPORTANT]
> The name in `\boldname{}` must match exactly how your name appears in your `.bib` file, including capitalization and any middle initials.

### Joint First Author Annotations
Mark co-first author papers with asterisks:
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

Researchers worldwide use CleanCV for their academic profiles. See examples: [Gilad Turok](https://giladturok.com/cv), [Jane Doe](https://janedoe.com/cv), [John Smith](https://johnsmith.com/cv).

> [!TIP]
> **Using CleanCV?** We'd love to feature you! [Open an issue](https://github.com/giladturok/CleanCV/issues) with a link to your CV and we'll add you to our gallery.

## Create Your Own Repository

The link in the [quick start](#quick-start) section creates a new Overleaf project. Instead, if you want CleanCV in your own Github repo with version control, follow these steps:

### **Step 1: Create repository from template**  
Go to the [CleanCV repository](https://github.com/giladturok/CleanCV) and click the green **"Use this template"** button at the top of the page. This creates your own copy of CleanCV in your GitHub account.

### **Step 2: Edit your `.tex` files**  
Choose how you want to edit your files:

- **Edit locally**: Clone your new repository and use any LaTeX editor  
  ```bash
  git clone https://github.com/yourusername/your-cv-repo.git
  cd your-cv-repo
  # Edit main.tex and publications.bib
  pdflatex main.tex && biber main && pdflatex main.tex
  ```

- **Edit in Overleaf**: Copy the `main.tex`, `publications.bib`, and `CleanCV.sty` files into a new Overleaf project. You can sync changes with Overleaf's GitHub integration, documented [here](https://www.overleaf.com/learn/how-to/GitHub_Synchronization) (Overleaf premium is required).

## Acknowledgments

CleanCV is heavily adapted from LaTeX CV templates by [Bastian Rieck](https://github.com/Pseudomanifold/latex-cv) and [Corey Stephan](https://github.com/historical-theology/cv). Please check out their work.
