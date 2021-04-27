:exclamation::exclamation: ** TRY DOING ALL EDITS IN OVERLEAF and SYNC GITHUB and GIT FROM IT **:exclamation::exclamation:

:exclamation: OVERLEAF Project: papilio-blue :exclamation:

- [Bsic Markdown syntax](https://www.markdownguide.org/basic-syntax)
- [Bsic Markdown syntax](https://www.markdownguide.org/extended-syntax)
- [List of Emojis](https://gist.github.com/rxaviers/7360908)


This is the repo for the book on review of basic electrical engineering principles mostly for Integrated Circuit & Electronic System designers. This book follows Tufte-style typesetting from Edward Tufte's books.  This repo is forked from the Tufte LaTeX package at https://github.com/Tufte-LaTeX/tufte-latex.

### Self-publish
- Edward Tufte's [Book design thread](https://www.edwardtufte.com/bboard/q-and-a-fetch-msg?msg_id=0000hB) has some great stuff on typography and book design. A must checkout.
- [Ask ET Forum](https://www.edwardtufte.com/bboard/) is the general forum with all questions.
- Robert Ghirst on [self-publishing on Amazon](https://www2.math.upenn.edu/~ghrist/whyselfpublish.html) is a must read as well.

### content scratch.
- Math
  - Algebra (Feynman's lecture)
  - Art of appoximation (Sanjoy Mahajan)
  - What's an imaginary number (Feynman's lecture and 1,2,3 infinity)
  - Complex number (Feynman's lecture, 1,2,3.. Infity)
  - Vector Calc (feynman)
  - Calculus (Robert Ghrist, UPenn)
  - Vector Calc (Feynman's lectures and Ghrist)
  - Linear Algebra (Strang, UPenn lecture)
  - Calculus ([Robert Ghrist's](https://www2.math.upenn.edu/~ghrist/) Youtube lectures, Strang OCW)
  - Diff equations.
- Electromagnetics
  - Feynman lectures: Vol-I 6: Probability, 22:Algebra,  25:Linear Systems, 50: Harmonics and Fourier series.
  - Griffith
  - Purcell

### Working on Overleaf
- This repo is linked to overleaf: `New Project` -> `Import from GitHub`
- To keep the repo in sync: `Overleaf -> Menu -> Sync -> GitHub`
- Create all the git clones from overleaf and sync it on overleaf with GitHub

### Figures
- Try https://github.com/pgf-tikz/pgf

## Documentation on the tufte-latex package.
The following documention is from the tufte-latex's README.md
Welcome to the beginnings of Tufte LaTeX package to help you
produce Tufte-style handouts, reports, and notes.

## Quick Start

Try typesetting `sample-handout.tex` with the following sequence
of commands,

    pdflatex sample-handout
    bibtex   sample-handout
    pdflatex sample-handout
    pdflatex sample-handout

The result should look like `sample-handout.pdf`.

The sample book can be compiled with the following:

    pdflatex sample-book
    bibtex sample-book
    texindy --language english sample-book.idx
    # or makeindex sample-book.idx
    pdflatex sample-book
    pdflatex sample-book
    pdflatex sample-book

## Troubleshooting

If you encounter errors of the form,

    ! LaTeX Error: File `paralist.sty' not found.

you will need to obtain missing packages from [CTAN](http://ctan.org).
For package installation instructions and answers to many other
questions, see the [UK TeX FAQ](http://www.tex.ac.uk/faq/) or search the [`comp.text.tex` group](http://groups.google.com/group/comp.text.tex).

The following packages are required:

 * chngpage or changepage
 * fancyhdr
 * fontenc
 * geometry
 * hyperref
 * natbib and bibentry
 * optparams
 * paralist
 * placeins
 * ragged2e
 * setspace
 * textcase
 * textcomp
 * titlesec
 * titletoc
 * xcolor
 * xifthen

The following packages are optional and will be automatically used if installed:

 * beramono
 * helvet
 * ifpdf
 * ifxetex
 * letterspace (in the microtype package)
 * mathpazo
 * soul

## Bugs/Features/Support

For kudos, feature requests, patches, or support requests that you
feel are _particular_ to this Tufte-LaTeX package, i.e., not a general
LaTeX issue, please use this project's issue tracker available at <https://github.com/Tufte-LaTeX/tufte-latex/issues>.

## Contributing

Patches and pull requests are most welcome via the issue tracker!  Submit a series of high quality patches, and you'll find yourself a developer on this project.

## License

Copyright 2007–2015 by Kevin Godby, Bil Kleb, and Bill Wood.

Licensed under the Apache License, Version 2.0 (the "License");
you may not use this file except in compliance with the License.
You may obtain a copy of the License at

    http://www.apache.org/licenses/LICENSE-2.0

Unless required by applicable law or agreed to in writing, software
distributed under the License is distributed on an "AS IS" BASIS,
WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
See the License for the specific language governing permissions and
limitations under the License.
