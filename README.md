:exclamation::exclamation: ** TRY DOING ALL EDITS IN OVERLEAF and SYNC GITHUB and GIT FROM IT **:exclamation::exclamation:

:exclamation: OVERLEAF Project: papilio-blue :exclamation:

- [Bsic Markdown syntax](https://www.markdownguide.org/basic-syntax)
- [Bsic Markdown syntax](https://www.markdownguide.org/extended-syntax)
- [List of Emojis](https://gist.github.com/rxaviers/7360908)


This is the repo for the book on review of basic electrical engineering principles mostly for Integrated Circuit & Electronic System designers. This book follows Tufte-style typesetting from Edward Tufte's books.  This repo is forked from the Tufte LaTeX package at https://github.com/Tufte-LaTeX/tufte-latex.

### Self-publish
- Check out Edward Tufte Visual Display of Quantitative Information for details on self-publishing
- Edward Tufte's [Beautiful Evidence chronicles](https://www.edwardtufte.com/bboard/q-and-a-fetch-msg?msg_id=000262&topic_id=1): writing, designing, publishing, consequences 
- Review Edward Tufte's course from his handout.
- Review some the of the books on typography and design from the Tufte's forum (see below)
- Edward Tufte's [Book design thread](https://www.edwardtufte.com/bboard/q-and-a-fetch-msg?msg_id=0000hB) has some great stuff on typography and book design. A must checkout.
- [Ask ET Forum](https://www.edwardtufte.com/bboard/) is the general forum with all questions.
- Robert Ghirst on [self-publishing on Amazon](https://www2.math.upenn.edu/~ghrist/whyselfpublish.html) is a must read as well.
- Checkout Memoir LaTeX class. Mostly for fiction and Math books.

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
  - Random numbers and statistics
- Electromagnetics
  - Feynman lectures: Vol-I 6: Probability, 22:Algebra,  25:Linear Systems, 50: Harmonics and Fourier series.
  - Griffith
  - Purcell
- Presenting Data (Edward Tufte)

### Working on Overleaf
- This repo is linked to overleaf: `New Project` -> `Import from GitHub`
- To keep the repo in sync: `Overleaf -> Menu -> Sync -> GitHub`
- Create all the git clones from overleaf and sync it on overleaf with GitHub
- [Managing Large projects](https://www.overleaf.com/learn/latex/Management_in_a_large_project)

### Figures
- Try https://github.com/pgf-tikz/pgf
- [PGF Plots](https://www.overleaf.com/learn/latex/Pgfplots_package)
- [CircuiTiKZ](https://www.overleaf.com/learn/latex/CircuiTikz_package)

### Fonts
The Tufte books use Bembo for text and Gill Sans for Title etc. The clones of these fonts which are cheaper from fontsite.com are Bergamo (BergamoPro) and Chantilly. Bought this OTF fonts and converted them to LaTeX but still can't get to work. So on hold. 
The default now is Palatino and Helevetica instead which are not bad so sticking with it for now till I figure out how to install the fonts completely.

- https://ctan.org/tex-archive/fonts/
- https://www.fontsite.com (paid fonts)
- [Loading custom fonts in overleaf](https://www.overleaf.com/learn/latex/Questions/I_have_a_custom_font_I'd_like_to_load_to_my_document._How_can_I_do_this%3F). After creating latexmrc, there is an error while compiling so not using this method.
- [Loading OpenType fonts in LaTeX](https://www.tug.org/TUGboat/tb27-2/tb87owens.pdf) : Mostly following this document to convert and install the Open Type fonts.
- Two utilities that can install Open Type fonts in TeX systems:
  - [J Owens otfinst](https://www.ece.ucdavis.edu/~jowens/code/otfinst/), [His Technical Paper on TUG](https://www.tug.org/TUGboat/tb27-2/tb87owens.pdf), Code on [CTAN](http://www.ctan.org/tex-archive/fonts/utilities/otfinst/)
  - Marc Penniga's [autoinst](https://ctan.org/tex-archive/fonts/utilities/fontools/)-- [manpage](https://manpages.debian.org/buster/texlive-font-utils/autoinst.1.en.html)
- Both of these are wrappers on top of `otftotfm` to simplify the process.
- Ended up using Marc's `autoinst` because Owen's script has a bug where the required version for `otfinfo` is higher than the latest version.
- The basic steps of converting and installing the fonts are:
  - For all the fonts and the attributes within them, install the _font metric_ and _encoding files_
  - For all fonts generate and install the description file `.fd` which maps select commands to font files.
  - Finally generate `.sty` files for users to use it in their code.
- Open Type Fonts contain the font data in either of the two types:
  - Adobe PS Type 1 or
  - True Type
- TeX requires the following files:
  - TFM : contains all the dimensions
  - PFB : Adobe PS Type-1 procedures that describe the shape of each chracter
  - VF : virtual mapping between TFm and PFB
  - ENC : specifies the encoding OT1, LY1, etc.
  - MAP : maps all the above files
- Use `otfinfo` to find all the properties of the fonts. The important ones are:
  - `kern` and `ligature`
  - numerals `old style` or `lining`
  - small caps with the option `smcp`

#### Installing the fonts in the AWS Ubuntu in the overleaf directory
Used the AWS Ubuntu instance to convert the files from OTF to TeX and put the directory structure in the overleaf project directory and used `\usepackage{PATH-TO-STY-FILE}`. The text fonts got changed to BergamoPro but could not use any of the different types eg. bold, italics, etc. Probably have to use an option but giving up for now. 

** Installing the LCDF tools (otftotfm, etc.) **
  
- Install all the development tools , if you haven't
- Install TeX if you haven't `apt install texlive-latex-base`
- Install the `kpathsea` path search lib `apt install libkpathsea-dev`
- `git clone https://github.com/kohler/lcdf-typetools`
- cd to the `lcdf-typetools` and configure, make and install:
  - `./bootstrap.sh` (only for github clones)
  - `./configure`
  - `sudo make`
  - `sudo make install`

** Installing autoinst and converting the OTF files **
- Downloaded the `autoinst` zip file from [CTAN](https://ctan.org/tex-archive/fonts/utilities/fontools/)
- Unzipped in ~/src/fontools
- Moved the content of `share` to the TeX share `/usr/share/texmf/fonts/enc/dvips/fontools`
- Added the `bin` directory to `$PATH` 
- To convert, simply ran `autoinst BergamoPro/* Chantilly/*`
- It created the entire directory sturcture under default directory `autoinst_output`
- Moved this driectory to the overleaf project directory
- Called the fonts using `\usepackage` but not fully working. Will look at it later.



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
