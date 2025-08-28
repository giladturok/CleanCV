# How It Works

CleanCV uses just two commands, defined in `CleanCV.sty`, to handle all your CV content:

## `\cvblock` — For Important Entries
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

## `\cvitem` — For List Entries
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

## When to Use Each Command

Instead of one-size-fits-all formatting, CleanCV lets you choose the right command for each type of content. Different information deserves different presentation.

- **`\cvblock`**: Major entries with details (education, experience, projects)  
- **`\cvitem`**: List entries (awards, talks, service)  
- **Plain text**: Simple content (skills, interests)

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
```

> [!TIP]
> When in doubt: Need bullet points or multiple lines? Use `\cvblock`. Single line in a list? Use `\cvitem`. Just text? Use neither.

# Customize

## Manage CV Sections
Add, remove, or reorder sections (and subsections) as needed.

- Default sections: `Research Interests`, `Education`, `Experience`, `Awards & Honors`, `Publications`, `Skills`, `Code`, `Talks & Presentations`, `Teaching`, `Mentoring`, `Service`

Here's an example of adding a new section with its own subsections:

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

- Suggested additional sections: `Media Coverage`, `Blog`, `Grants & Fundraising`, `Professional Affiliations`, `References`

## Change Colors and Styling
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

## CV vs Resume Mode
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

> [!TIP]
> To make your resume fit on one page, increase the page height in `CleanCV.sty`:
> ```latex
> \geometry{
>     letterpaper,
>     left=2.5cm,
>     right=2.5cm,
>     top=2cm,
>     bottom=2.5cm,
>     pageheight=30cm        % Add this argument and set the appropriate height
> }
> ```

## Customize Contact Bar
Modify the contact bar by editing icons or removing sections in `main.tex`:
```latex
% Standard contact bar
\contactbar{yoursite.com}{you@email.com}{github-user}{linkedin}{scholar-url}{Your City}

% Skip unused platforms by leaving empty
\contactbar{yoursite.com}{you@email.com}{}{linkedin}{}{Your City}
```

## Name Highlighting in Publications
Your name appears bold in every publication automatically:
```latex
% In main.tex - must match your name exactly in .bib file
\boldname{YourLast}{YourFirst}{Initial}
```

> [!IMPORTANT]
> The name in `\boldname{}` must match exactly how your name appears in your `.bib` file, including capitalization and any middle initials. If no middle initials, leave the brackets `{}` empty.

## Joint First-Author Annotations
Mark joint first-author papers with asterisks:
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

## Author Annotations in Publications

Add author annotations in `publications.bib` via the `author+an` field. Default annotations include equal contribution (*) and corresponding author (†).

```latex
@article{yourpaper2023,
    title={Your Amazing Research},
    author={Your Name and Collaborator Name and Third Author},
    journal={Nature},
    year={2023},
    % Author annotations are assigned via numerical author ordering
    % Separate authors with semicolons and separate multiple annotations with commas
    author+an = {1=equal; 2=equal,corresponding; 3=corresponding}
}
```

**Output**:
```text
Your Name*, Collaborator Name*†, and Third Author†. “Your Amazing Research”. In: Nature (2023).
```

Annotations are implemented in `cleancv.sty` following the [Hansen Lab approach](http://www.hansenlab.org/cv_bibliography_tex). `main.tex` also includes a note explaining author annotation symbols at the top of the `Publications` section.
