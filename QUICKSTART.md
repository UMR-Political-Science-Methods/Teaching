# Quick Start Guide

This guide will help you get your teaching website up and running quickly.

## Step 1: Install Quarto

Download and install Quarto from [quarto.org](https://quarto.org/docs/get-started/)

## Step 2: Clone the Repository

```bash
git clone https://github.com/UMR-Political-Science-Methods/Teaching.git
cd Teaching
```

## Step 3: Preview the Website

```bash
quarto preview
```

This will open a browser window showing your website at `http://localhost:4200`

## Step 4: Customize Your Syllabi

1. Edit the example syllabi in `syllabi/intro-methods/syllabus.qmd` and `syllabi/advanced-methods/syllabus.qmd`
2. Or create new syllabi by following the template

## Step 5: Render All Formats

To generate HTML, PDF, and Word versions of your syllabi:

```bash
# Render individual syllabi
quarto render syllabi/intro-methods/syllabus.qmd
quarto render syllabi/advanced-methods/syllabus.qmd

# Or render everything at once
quarto render
```

## Step 6: Update Links

Edit `teaching.qmd` to add or modify links to your syllabi:

```markdown
### Your Course Name

- [View HTML](syllabi/your-course/syllabus.html){target="_blank"} - Online version
- [Download PDF](syllabi/your-course/syllabus.pdf){target="_blank"} - Printable version
- [Download Word](syllabi/your-course/syllabus.docx){target="_blank"} - Editable version
- [Source .qmd](syllabi/your-course/syllabus.qmd){target="_blank"} - Quarto source file
```

## Step 7: Publish to GitHub Pages (Optional)

The repository includes a GitHub Actions workflow that automatically publishes your site when you push to the main branch.

To enable:
1. Go to your repository Settings → Pages
2. Set Source to "GitHub Actions"
3. Push your changes to the main branch
4. Your site will be available at `https://yourusername.github.io/Teaching`

## Tips

- **Live Preview**: Run `quarto preview` while editing to see changes in real-time
- **Multiple Formats**: Each .qmd file can generate HTML, PDF, and Word simultaneously
- **Customization**: Modify `_quarto.yml` to change themes, add pages, or adjust settings
- **Icons**: The CSS adds automatic icons (🌐 for HTML, 📄 for PDF, 📝 for Word, 📋 for .qmd)

## Troubleshooting

**Links not working?**
- Make sure you've rendered the syllabi first with `quarto render`
- Check that file paths in `teaching.qmd` match your directory structure

**PDF generation fails?**
- Install TinyTeX: `quarto install tinytex`

**Need help?**
- Check the [Quarto documentation](https://quarto.org/docs/guide/)
- See the full README.md for more details
