# Zine Booklet

A zine booklet template in TeX. Lovingly inspired by [this repo](https://github.com/sylvain-kern).

## Custom Environments 

This package provides two custom environments for typesetting articles and 
poems. Examples of these templates can be found in the `sec` directory in the.
Both environments can be modified in the `preamble.tex` file.

Example of an article.
```
\begin{article*}{Title}{Author}
    Content is typset here like any other content in \LaTeX{}. Using the default 
    configuration, articles will be in a two column format. The title and 
    author will be auto formatted above the text.
\end{article*}
```

Example of a poem.
```
\begin{poem*}{Title}{Author}
    A poem goes here\\
    it uses the verse package\\
    it's easy to use!\\
\end{poem*}
```
## Adding Chapters 

To add a chapter, create a new file in the `sec` directory. Each chapter is a 
standalone TeX file that must be called in the main file.

```
\documentclass[../main.tex]{subfiles}
\begin{document}
    \chapter{Chapter Title}
    \ThisLRCornerWallPaper}{1.2}{../img/image-title.ext}
    \begin{article*}{Title}{Jane Doe}
        Content of article (or other environment. Goes here.
    \end{article*}
\end{document}
```

After saving the file, if you want to include this chapter in the final output,
make sure to add it to the `main.tex` file without the `.tex` extension.

```
\documentclass[12pt]{book}
\input{preamble.tex}
\begin{document}
    \tableofcontents
    \import{./sec/}{chapterFileName}
\end{document}
```

## Building 

In order to build a PDF, run the `pdflatex` command on the main file (you 
may have to build it twice in order to get a proper table of contents).

`pdflatex main.tex`

To prepare a document for printing, run the `pdflatex` command on the outputted
`print.tex`. It is important to build the `main.tex` file into a PDF first. Running
pdflatex on the `print.tex` file will simply rearrange the pages in a way
conducive for printing. 

`pdflatex print.tex`

**Note:** All images in this repo are in the public domain and can be accessed 
using the [Wikimedia Commons](https://commons.wikimedia.org/w/index.php?search=japanese+travel+posters&title=Special:MediaSearch&go=Go&type=image).
