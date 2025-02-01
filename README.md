# genwro.AI blog

This is blog of genwro.AI research group. 

Here you can find:
* latest updates on what we're researching and building,
* regular "What We're Reading" posts where our team shares interesting papers and reports,
* tutorials and explanations of ML concepts we work with,
* tips and tricks we've learned along the way - useful whether you're just starting or already in the field.

## How to Contribute?

### Short setup guide

1. Install `hugo`.
2. Clone the repo.
3. Initialize theme submodules: `git submodule update --init --recursive`.
4. Run `hugo serve -D` to create/update static files and serve the website.


### Writing Posts

```bash
# Create a new post
hugo new posts/<post-name>.md

# For a post with references
hugo new --kind posts posts/<optional-directory>/<post-name>
```

Posts should be written in Markdown format. The front matter should include:
- title,
- date,
- author,
- category,
- tags (optional).

Exemplary front matter:
```yaml
---
title: "Your Post Title"
date: 2024-02-01
author: "Your Name"
category: ["Research", "Tutorial", "Paper Review"]
tags: ["machine-learning", "neural-networks"]
draft: false
---
```

#### Using BibTeX references

Simply add required references into your `references.bib` and when you want to cite one or more of the articles, use `{{< cite ref-key >}}` or `{{< cite "ref-key1, ref-key2" >}}`.

### Contribution

Create a PR (most preferably with Linear issue code) with the changes that you want to make. After a review, merge the PR and the github actions workflow will do everything else ;)


### Acknowledgments

This blog is built with:
* [Hugo](https://gohugo.io/) - A fast and flexible static site generator
* [PaperMod](https://github.com/adityatelange/hugo-PaperMod) theme - A clean, fast, and responsive Hugo theme
* GitHub Actions for automated deployment and continuous integration
* GitHub Pages for hosting
