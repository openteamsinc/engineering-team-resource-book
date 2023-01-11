# Book Tutorial and Guidelines

This page includes information about how to add a section to this Jupyter Book as well as the standards for doing so.

## How to add a section:

### 1. Clone this repository
```git clone git@github.com:openteamsinc/engineering-team-resource-book.git```

### 2. Navigate to the docs folder
```cd ~/engineering_team_resource_book/docs```

### 3. Create a markdown file
```NAME_OF_FILE.md```

### 4. Add contents
See [Formatting Requirements](format)

### 5. In the _toc.yml file add markdown file.
A new main page for a project will follow the format below, and be written at the same indentation level as ```chapters```.

A section page under a project should be under the ```section``` portion which should be under, or should be created under the main or intro project page.

```
format: jb-book
root: docs/intro
chapters:
- file: docs/instructions
- file: docs/intro_to_project_page
  sections: 
  - file: docs/section_page1
  - file: docs/section_page2
```

### 6. Build the Book
**IMPORTANT** This is the equivalent of saving your work before pushing changes.
To make sure that everything saves properly, do this after you have added content and added your files to the ```_toc.yml```

Build with the following command:
```jupyter-book build engineering_team_resource_book```

The general command is:
```jupyter-book build mybookname/```

:::{note}
By default, Jupyter Book will only build the HTML for pages that have been updated since the last time you built the book.

If you’d like to force Jupyter Book to re-build a particular page, you can either edit the corresponding file in your book’s folder, or delete that page’s HTML in the _build/html folder.

You can also signal a full re-build using the --all option:

```jupyter-book build --all mybookname/```
:::


### 7.
```pip install ghp-import```

### 8. Navigate to engineering_team_resource_book and push changes using ghp-import
```ghp-import -n -p -f _build/html```
This will add the changes you have made to the GitHub Pages for this Jupyter Book which can be found [here.](https://openteamsinc.github.io/engineering-team-resource-book/docs/intro.html)

:::{note}
Make sure that you included the -n. This adds a file called .nojekyll to the output of your book, which tells GitHub not to build your book with Jekyll. Which is what we want in order for GitHub Pages to treat your files as a “static HTML website”.
:::

(format)=
## Formatting Requirements:
### Project intro page
This is the page that will be the first layer in the table of contents. 

On this page include a **"#" header** at the top, this will create the title of this page.

Then include a introductory section. Generally try to avoid adding to many subheaders on this page, add each major section to its own page later on.

Finally, add the following text:

```{tableofcontents}
```
This will add all of the section pages added to the ```_toc.yml``` section below this intro page. 
For example the ```section_page1``` and ```section_page2``` Would appear with their "#" Header name in this project's table of contents.

```
format: jb-book
root: docs/intro
chapters:
- file: docs/instructions
- file: docs/intro_to_project
  sections: 
  - file: docs/section_page1
  - file: docs/section_page2
```

### Section Pages
Add the bulk of the content into these pages, divided as you see fit.
Remember to update the ```_toc.yml``` file accordingly.

```
format: jb-book
root: docs/intro
chapters:
- file: docs/instructions
- file: docs/intro_to_project
  sections: 
  - file: docs/section_page1
  - file: docs/section_page2
```

## Some references for formatting:

#### Section Titles and Referencing
"#" symbols denote section headers in CommonMark markdown. They define the section headers on pages. 
"#" is the main title of the page, and "##" is the first subheader, and so on.

Here is an example:
```# Here's my sample title

This is some sample text.

(section-label)=
## Here's my first section

Here is a [reference to the intro](intro.md). Here is a reference to [](section-label).
```
- (section-label)= is a label that’s attached to a section header. It refers to whatever header follows, and allows you to refer to this label later on in your text.

#### Linking
- [link text](link-target) syntax is how you specify a link in markdown.

#### Notes
To create a note use ":::{note}" This is a directive in MyST Markdown. It is rendered like this:
:::{note}
I’m a note!
:::

A similar directive ":::{admonition}SPECIFIC_NAME"
:::{admonition}SPECIFIC_NAME
I’m an admonition!
:::

#### Code
"```" denotes a code block in CommonMark markdown. It is rendered like this:
```e=mc^2```

#### Bullet points
"- " Creates a bullet point.
- Which looks like this.

#### Typeface
"**" on either side of text creates bold face font.
**Bold text.**
"*" on either side of text creates italic font.
*Italic font.*

## More information:
For more information visit the Jupyter Book website.

[Creating a file.](https://jupyterbook.org/en/stable/start/new-file.html)

[Markdown explanation.](https://commonmark.org/)
