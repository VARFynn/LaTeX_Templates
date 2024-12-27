
## Introduction

This guide explains how to work with the provided Beamer LaTeX template to create professional presentations. It will guide you on customizing key aspects like title, colors, sections, and adding content without altering the base structure or theme.

## File Structure

The project consists of the following files and directories:

- **main.tex**: The main LaTeX file controlling the document structure.
- **config/code_langs.tex**: Configuration for syntax highlighting in code.
- **sections/**: Contains separate `.tex` files for each section of the presentation.
- **img/**: A folder for storing images used in the presentation.
- **bibliography.bib**: A file for managing references.

Each file has a specific role, and changes should be made in the relevant file for a modular workflow.

## How to Use the Template

1. **Editing Title, Author, and Date**
   - In the `main.tex` file, update the `\title`, `\author`, and `\date` commands under the **Presentation Information** section.
   - Example:
     ```latex
     \title[Short Title]{Full Presentation Title}
     \author[Your Initials]{Your Full Name}
     \date[Year]{Month / Year}
     ```

2. **Adding Content**
   - Add your presentation content in the section files located in the `sections/` folder.
   - Each section is included in `main.tex` using `\include{sections/sectionXX}`, where `XX` is the section number.
   - To add a new section, create a new `.tex` file in the `sections/` folder and include it in `main.tex`.

3. **Customizing Colors**
   - The template uses predefined colors (e.g., `primaryColor`, `secondaryColor`).
   - To change colors, modify the `\definecolor` commands in `main.tex` under the **Custom Colors** section.
   - Example:
     ```latex
     \definecolor{primaryColor}{RGB}{20,60,105}   % Change RGB values for a new primary color
     ```

4. **Managing Images**
   - Store your images in the `img/` folder.
   - Reference images in your sections using:
     ```latex
     \includegraphics[width=\linewidth]{filename}
     ```
     Ensure the `\graphicspath{{img/}}` command in `main.tex` is correctly set.

5. **Handling References**
   - Add references to `bibliography.bib` using BibTeX format.
   - Use your custom citation command, such as `\citegray{key}`, to cite references within your sections.
     - Example:
       ```latex
       \citegray{Author et al. 2024}
       ```
   - Ensure `\addbibresource{bibliography.bib}` is included in `main.tex`:
     ```latex
     \usepackage[style=alphabetic,backend=biber]{biblatex} % Bibliography style using alphabetic citation, backend: biber.
     \addbibresource{bibliography.bib}                     % Adds the bibliography file (bibliography.bib).
     ```
   - Use the `\nocite` command if needed to include references that are not explicitly cited in the presentation:
     ```latex
     % \nocite{*}  % Uncomment this line to include all references from bibliography.bib in the bibliography.
     ```
     Note: By default, `\nocite` is commented out, so no references will be generated unless explicitly cited. This approach is useful if you prefer manual citations within Beamer slides.

6. **Adjusting Themes**
   - The template uses the `Boadilla` theme for a clean look. Avoid changing the theme, as it may disrupt the formatting.
   - You can adjust minor visual elements, such as navigation symbols, by modifying the `\setbeamertemplate` commands in `main.tex`.

7. **Compiling the Presentation**
   - Compile the `main.tex` file using a LaTeX editor like Overleaf or locally with tools like `pdflatex` or `xelatex`.

## Tips for Using the Template

- Keep sections modular by editing or adding content only in the corresponding `.tex` files.
- Maintain a consistent color scheme to ensure visual harmony.
- Use the provided structure to include images, tables, or code snippets seamlessly.
- Avoid altering the overall layout or theme to prevent formatting issues.

## Conclusion

This Beamer template is designed to create structured and visually appealing presentations. By following the guidelines above, you can customize the template to suit your presentation needs while preserving its professional design.
