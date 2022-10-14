# quarto-book-test

This repository was created to explore using [Quarto] for creating and publishing Quarto Books via private GitHub Pages.

## The published book

The published version of this Quarto Book is available at <https://upgraded-spork-6075ab73.pages.github.io/>.  

This is a private site that can only be access by those who have access to this <https://github.com/ucsf-wynton/quarto-book-test/> repository.


## How this book was created

The content in this repository was created using:

```sh
$ quarto --version
1.2.215
```


### Create book template folder (once)

Following the instructions on <https://quarto.org/docs/books/>, I created `quarto-book-test/` book template folder using:

```sh
$ quarto create-project quarto-book-test --type book
...
$ cd quarto-book-test/
```


### Viewer book locally (just a test)

To preview the HTML-version of the book in your local web browser, run

```sh
$ cd quarto-book-test/
$ quarto preview
```

This is how the book will look like when published online.


### Create git repository (once)

Next step was to set this up in git repository to be pushed to GitHub.  Reading ahead in the instruction, I first created a [`.gitignore`](https://github.com/ucsf-wynton/quarto-book-test/blob/main/.gitignore) file that ignores certain files and folders we don't want include in the git repository;

```plain
*~
/.quarto/
/_book/
```

Then I created the git repository, and pushed it online:

```sh
$ git init
$ git add -- .* *
$ git commit -am "Created book skeleton"
$ git remote add origin git@github.com:ucsf-wynton/quarto-book-test.git
$ git push
```


### Publish to GitHub Pages

This repository was set up as a _private_ GitHub repository.  Since it is hosted under the <https://github.com/ucsf-wynton/> organization, which is under the GitHub Enterprise Cloud plan that UCSF has, we can use _private_ GitHub Pages.  The instructions for publish to GitHub Pages are the same for private and public GitHub Pages (<https://quarto.org/docs/publishing/github-pages.html>);

```sh
$ quarto publish gh-pages
```

The only culprit is that this command will get stuck at:

```sh
(/) Deploying gh-pages branch to website (this may take a few minutes)
```

We have to hit <kbd>Ctrl-C</kbd> to break out of it.  This is a bug, which I've reported (<https://github.com/quarto-dev/quarto-cli/issues/2864>).


[Quarto]: https://quarto.org/
