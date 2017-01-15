---
layout: post
published: false
title: 'Utils: Writting a book in Markdown'
subtitle: Is that even possible?
---
Say you want to write your very own software or coding book. The first option to proceed is, of course, a text processor like [LibreOffice Writer](https://www.libreoffice.org/discover/writer/). Don't use that. You may use instead a more complex toolchain, like [LaTeX](https://www.latex-project.org/). If you are as lazy as me, you probably won't want to learn how to layout a book using LaTeX. So... what's left?

Here's the best and easiest way: use [Markdown](https://es.wikipedia.org/wiki/Markdown). Of course, it's not as powerful as LaTeX, but it's fast, easy and lightweight.

EDIT: This is the second time I rewrite this post, because "Oh oh! Chrome crashes and changes weren't saved automatically!".

## Where do we start?

If you don't know Markdown, I recommend you to read [this tutorial](http://www.markdowntutorial.com/). Since we're not serving the book as is (some scattered *.md* files) we need something to transform those source *.md* files into a convinient format like *.pdf* or *.pub*. Please, greet your new friend [Pandoc](http://pandoc.org/).

## Installing

Please, check [this page](http://pandoc.org/installing.html) for more information. On ubuntu, it can be installed with this command:

```sh
sudo apt-get install pandoc
```

<a href="https://www.youtube.com/watch?v=n3TAEaTCJHg" target="_blank">Easy peasy lemon squeezy</a>.

Also, we'll be using [make](https://www.gnu.org/software/make/), so don't forget to install it:

```sh
sudo apt-get install make
```

## Folder structure

Before creating scattered files like a maniac, let's create a folder tree structure to keep files organized. For example:

```
my-book/         # Root directory.
|- build/        # Folder used to store builded (output) files.
|- chapters/     # Markdowns files; one for each chapter.
|- images/       # Images folder.
|  |- cover.png  # Cover page for epub.
|- metadata.yml  # Metadata content (title, author...).
|- Makefile      # Makefile used for building our books.
```

Simple, isn't it? Don't worry abuot the files' content; I'll explain each file on the following sections.

You can find the template used on this post in [this GitHub repository](TODO). 

## Setup generic data

First, we need a title and an author, don't we? That's the purpose of *metadata.yml*. Here's a example:

```yml
---
title: My book title
author: Daniel Herzog
rights:  Creative Commons Attribution 4.0 International
language: en-US
tags: [book, my-book, etc]
abstract: |
  Your summary text.
---
```

You get the idea, right? You can find the list of all available keys on [this page](http://pandoc.org/MANUAL.html#extension-yaml_metadata_block).

## Creating chapters

Creating a new chapter is as simple as creating a new markdown file in your *chapters/* folder. Something like this:

```
chapters/01-introduction.md
chapters/02-installation.md
chapters/03-usage.md
chapters/04-references.md
```

Pandoc will join them automatically. All you need to specify is at least a title:

```md
# Introduction

This is the first paragraph of the introduction chapter.

## First

This is the first subsection.

## Second

This is the second subsection.
```

### Links between sections

...

### Links between chapters

...

## Output

...

### Export to PDF

...

### Export to EPUB

...

### Export to HTML

...

### Configuring the style

...

### Configuring the output

...

## References