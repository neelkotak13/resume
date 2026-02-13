# Resume Template

Professional LaTeX resume template optimized for technical roles (DevSecOps, Security Engineering, Software Development).

## Files

- `civilian.tex` - Main resume source file
- `resume.cls` - Custom LaTeX class defining formatting and layout
- `civilian.pdf` - Compiled PDF output
- `RESUME_OPTIMIZATION_LOG.md` - Detailed change history and optimization notes

## Prerequisites

### macOS
```bash
# Install BasicTeX (smaller, ~400MB)
brew install --cask basictex

# OR install full MacTeX (~4GB, includes GUI tools)
brew install --cask mactex

# Refresh PATH
eval "$(/usr/libexec/path_helper)"
```

### Linux
```bash
# Debian/Ubuntu
sudo apt-get install texlive-latex-base texlive-latex-extra

# Fedora/RHEL
sudo dnf install texlive-scheme-basic
```

### Windows
Download and install [MiKTeX](https://miktex.org/download) or [TeX Live](https://www.tug.org/texlive/)

## Quick Start

### Compile Resume
```bash
# Navigate to resume directory
cd /path/to/resume

# Compile LaTeX to PDF
pdflatex civilian.tex

# Open PDF (macOS)
open civilian.pdf

# Open PDF (Linux)
xdg-open civilian.pdf

# Open PDF (Windows)
start civilian.pdf
```

### Clean Build Artifacts
```bash
# Remove temporary files
rm -f *.aux *.log *.out *.toc *.synctex.gz *.fdb_latexmk *.fls
```

## Template Structure

### Header Section
```latex
\name{Your Name}
\address{Phone \\ Job Title \\ Location \\ Clearance}
\address{Email \\ LinkedIn \\ GitHub}
```

### Main Sections
1. **Professional Summary** - 3-4 line value proposition
2. **Education** - Degrees with dates and relevant coursework
3. **Certifications** - Professional certifications with dates
4. **Skills** - Categorized technical skills
5. **Experience** - Work history with bullet points

### Adding Experience
```latex
\textbf{Job Title} \hfill Start Date - End Date\\
Company Name \hfill \textit{Location}
 \begin{itemize}
    \itemsep -3pt {}
     \item Achievement or responsibility with metrics
     \item Another achievement with quantifiable impact
     \item Technical skills demonstrated
 \end{itemize}
```

### Adding Skills
```latex
\begin{tabular}{ @{} >{\bfseries}l @{\hspace{3ex}} l }
Category Name & Skill1, Skill2, Skill3 \\
Another Category & Tool1, Tool2, Tool3 \\
\end{tabular}
```

## Customization

### Margins
Edit in `civilian.tex`:
```latex
\usepackage[left=0.4in,top=0.4in,right=0.4in,bottom=0.4in]{geometry}
```

### Font Size
Edit in `resume.cls`:
```latex
\LoadClass[11pt,letterpaper]{article}  % Change 11pt to 10pt or 12pt
```

### Section Spacing
Edit in `resume.cls`:
```latex
\def\sectionskip{\medskip}  % Change to \smallskip or \bigskip
```

## Best Practices

### Content
- **Length:** 2 pages for 4+ years experience
- **Bullet points:** 1-2 lines max, start with action verbs
- **Metrics:** Include quantifiable achievements (%, $, time saved)
- **Keywords:** Match job description for ATS optimization
- **Clearance:** Place in header for maximum visibility

### Formatting
- **Font:** Standard (Computer Modern) for ATS compatibility
- **Sections:** Use standard headers (Experience, Education, Skills)
- **Consistency:** Maintain uniform date formats and bullet styles
- **White space:** Balance content density with readability

### ATS Optimization
- Avoid tables for main content (use for skills only)
- No images, graphics, or fancy formatting
- Standard section names
- Include both acronyms and full terms (e.g., "CI/CD" and "Continuous Integration")

## Common Issues

### Command Not Found
```bash
# If pdflatex not found, refresh PATH
eval "$(/usr/libexec/path_helper)"

# Or use full path
/Library/TeX/texbin/pdflatex civilian.tex
```

### Missing Packages
```bash
# BasicTeX users may need additional packages
sudo tlmgr update --self
sudo tlmgr install <package-name>
```

### Overfull/Underfull Boxes
These warnings are normal. Check PDF output - if text looks good, ignore them.

### Text Overflowing Margins
- Break long lines into multiple rows
- Shorten bullet points
- Use abbreviations where appropriate

## Version Control

### Recommended .gitignore
```
# LaTeX build artifacts
*.aux
*.log
*.out
*.toc
*.synctex.gz
*.fdb_latexmk
*.fls
*.pk
*.tfm

# OS files
.DS_Store
Thumbs.db
```

### Git Workflow
```bash
# Initialize repository
git init
git add civilian.tex resume.cls README.md .gitignore
git commit -m "Initial resume template"

# After making changes
git add civilian.tex
git commit -m "Update experience section"
git push
```

## Editing Tools

### Recommended Editors
- **Overleaf** - Online LaTeX editor (no local install needed)
- **VS Code** - With LaTeX Workshop extension
- **TeXShop** - macOS native LaTeX editor
- **TeXworks** - Cross-platform LaTeX editor
- **Vim/Emacs** - With LaTeX plugins

### VS Code Setup
```bash
# Install LaTeX Workshop extension
code --install-extension james-yu.latex-workshop

# Configure auto-compile on save in settings.json
{
  "latex-workshop.latex.autoBuild.run": "onSave"
}
```

## Template Customization Guide

### Change Colors (Advanced)
Add to preamble in `civilian.tex`:
```latex
\usepackage{xcolor}
\definecolor{linkcolor}{RGB}{0,0,139}
```

### Add Section
```latex
\begin{rSection}{SECTION NAME}
Content here
\end{rSection}
```

### Special Characters
- `\&` for &
- `\%` for %
- `\$` for $
- `\_` for _
- `\#` for #

## Resources

- [LaTeX Documentation](https://www.latex-project.org/help/documentation/)
- [Overleaf Tutorials](https://www.overleaf.com/learn)
- [CTAN Package Archive](https://ctan.org/)
- [Resume Optimization Log](RESUME_OPTIMIZATION_LOG.md) - Detailed change history

## Support

For template issues or questions:
1. Check `RESUME_OPTIMIZATION_LOG.md` for context
2. Review LaTeX error messages in `.log` file
3. Search [TeX StackExchange](https://tex.stackexchange.com/)

## License

This template is based on the Medium Length Professional CV template from LaTeXTemplates.com.

---

**Last Updated:** February 13, 2026
