# Teaching & Syllabi Website

This repository contains a Quarto-based website for teaching information and course syllabi. All syllabi are created using R and Quarto (.qmd files) and can be rendered to multiple formats: HTML, PDF, and Word.

## 🌐 Live Website

The website provides:
- Teaching information and course descriptions
- Syllabi in multiple formats (HTML, PDF, DOCX)
- Active links to all document formats
- Source .qmd files for transparency

## 📋 Structure

```
Teaching/
├── _quarto.yml           # Quarto website configuration
├── index.qmd             # Home page
├── teaching.qmd          # Teaching page with syllabus links
├── styles.css            # Custom CSS styling
├── syllabi/              # Syllabi directory
│   ├── intro-methods/
│   │   └── syllabus.qmd  # Example syllabus 1
│   └── advanced-methods/
│       └── syllabus.qmd  # Example syllabus 2
└── _site/                # Generated website (after rendering)
```

## 🚀 Getting Started

### Prerequisites

1. **R and RStudio** - Download from [CRAN](https://cran.r-project.org/) and [RStudio](https://posit.co/download/rstudio-desktop/)
2. **Quarto** - Download from [quarto.org](https://quarto.org/docs/get-started/)

### Installation

1. Clone this repository:
   ```bash
   git clone https://github.com/UMR-Political-Science-Methods/Teaching.git
   cd Teaching
   ```

2. Install required R packages (optional, for advanced features):
   ```r
   install.packages(c("rmarkdown", "knitr"))
   ```

## 🔨 Building the Website

### Render All Syllabi

To generate HTML, PDF, and Word versions of all syllabi:

```bash
# Render individual syllabi
quarto render syllabi/intro-methods/syllabus.qmd
quarto render syllabi/advanced-methods/syllabus.qmd

# Or render the entire website
quarto render
```

### Preview the Website

```bash
quarto preview
```

This will start a local server (usually at `http://localhost:4200`) where you can preview the website.

## 📝 Adding New Syllabi

1. **Create a new directory** in the `syllabi/` folder:
   ```bash
   mkdir syllabi/your-course-name
   ```

2. **Create a syllabus.qmd file** with the following header:
   ```yaml
   ---
   title: "Your Course Title"
   subtitle: "Course Code - Semester Year"
   format:
     html:
       toc: true
       number-sections: true
     pdf:
       toc: true
       number-sections: true
       colorlinks: true
     docx:
       toc: true
       number-sections: true
   ---
   ```

3. **Add your content** using Markdown and R code chunks

4. **Render the syllabus**:
   ```bash
   quarto render syllabi/your-course-name/syllabus.qmd
   ```

5. **Update teaching.qmd** to add links to your new syllabus:
   ```markdown
   ### Your Course Title
   
   - [View HTML](syllabi/your-course-name/syllabus.html){target="_blank"}
   - [Download PDF](syllabi/your-course-name/syllabus.pdf){target="_blank"}
   - [Download Word](syllabi/your-course-name/syllabus.docx){target="_blank"}
   - [Source .qmd](syllabi/your-course-name/syllabus.qmd){target="_blank"}
   ```

6. **Re-render the website**:
   ```bash
   quarto render
   ```

## 📤 Publishing

### GitHub Pages

1. Enable GitHub Pages in your repository settings
2. Set the source to the `_site` folder or use GitHub Actions
3. Your website will be available at `https://yourusername.github.io/Teaching`

### Using GitHub Actions (Recommended)

Create `.github/workflows/publish.yml`:

```yaml
name: Publish Quarto Website

on:
  push:
    branches: main

jobs:
  build-deploy:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v2
      
      - uses: quarto-dev/quarto-actions/setup@v2
      
      - name: Render Quarto Project
        run: quarto render
        
      - name: Deploy to GitHub Pages
        uses: peaceiris/actions-gh-pages@v3
        with:
          github_token: ${{ secrets.GITHUB_TOKEN }}
          publish_dir: ./_site
```

## 🎨 Customization

- **Theme**: Edit `_quarto.yml` to change the theme (options: cosmo, flatly, darkly, etc.)
- **Navigation**: Modify the navbar in `_quarto.yml`
- **Styling**: Edit `styles.css` for custom CSS
- **Output formats**: Adjust format options in individual .qmd files

## 📚 Resources

- [Quarto Documentation](https://quarto.org/)
- [Quarto Gallery](https://quarto.org/docs/gallery/)
- [R Markdown Guide](https://rmarkdown.rstudio.com/)

## 📄 License

This project is open source and available under standard academic use.

## 🤝 Contributing

Feel free to fork this repository and adapt it for your own teaching needs!