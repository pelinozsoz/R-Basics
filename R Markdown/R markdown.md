# R Markdown
## 1- What is Markup Language?
A markup language is a way of writing text where you add special symbols or tags to show how the text should be structered, formatted, or displayed.
It refers to any system that uses symbols or tags to structure or format texts.
```r
# 📌 Examples of markup languages
- HTML – uses tags like <h1>, <p>, <b>
- Markdown – uses simple symbols like #, *, **, []()
- LaTeX – uses commands like \section{}, \textbf{}
- XML – uses structured tags like <name> ... </name>
```
## 2- What is Markdown?
Markdown is one specific markup language. It is a simple, lightweight, easy-to-read version of markup. It is used for quick formatting for documents such as headings, lists, bold/italic, links, images, code blocks. It is also ideal for README files, notes, simple blogs.
- The file extention of a markdown file is .md or .markdown.

## 3- What is R Markdown?
R Markdown is a markup language that combines regular markdown with executable R code chunks. So that, one can write text, run code, and show the visual outcomes in one reproduceble document. This documents could be exported as HTML, PDF, Word, Slides, and more.
- The file extention of an R markdown is .Rmd.

### ✏️ Why We Use R Markdown?
- **To enhance reproducibility & transparency**

Because code + results + narrative are bundled together, someone reading your document can see exactly what you did and re-run the same code to obtain the same results. It makes sharing analyses—and reproducing them later—much easier.
- **To integrate analysis and documentations**

You don’t have to keep separate files for code, results, and write-up. Everything lives in one place. This makes it ideal for reports, notebooks, summaries, even theses or papers. 
- **To provide flexibility for output formats**

From a single .Rmd file, you can generate many kinds of outputs: HTML pages, PDFs, Word documents, slide presentations, dashboards, websites, books — depending on your needs. 
- **To enable version control and collabration**

Since .Rmd is plain text, it works very well with version control systems (e.g. git). It’s easy to track changes, merge edits, and keep a clean history — unlike binary formats like Word .docx. 

### 🖋️ Structure of a R Markdown Document
An R Markdown (.Rmd) document is typically composed of three parts.
#### 📰 Header / Metadata
- At the top of the file, enclosed in triple dashes ---.
- Specifies metadata like document title, author, date, and output options (e.g. HTML, PDF, Word, slides, etc.).
#### 📝 Markdown Text
- Normal prose, written using Markdown syntax (headers, lists, bold/italic, links, etc.).
- This is where you explain your hypotheses, describe your methods, present interpretation, discussion, etc.
#### 💻 Code Chunks
- Blocks of R code (or sometimes other languages) enclosed in backticks and braces, e.g. ``````{r} … . 
- When you “knit” the document, these chunks are executed; their output (console output, tables, plots) is captured and inserted into the final document.

### 🖍️ R Markdown syntax
#### 1- Headings
```r
# Heading 1
## Heading 2
### Heading 3
#### Heading 4
```
#### 2- Text Formatting
```r
# Bold
**bold**

# Italic
*italic*

# Bold + italic
***very important***

# Strikethrough
~~deleted~~
```
#### 3- Lists
```r
# Unordered
- item
- item
    - subitem

# Ordered
1. First
2. Second
    1. Sub-numbered
```
#### 4- Links & Images
```r
# Links
[link text](https://example.com)

# Images
![alt text](image.png)
```
#### 5- Tables
```r
| Name | Age |
|------|-----|
| John | 24  |
| Anna | 31  |
```
