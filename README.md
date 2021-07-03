# Introdução a Ciência da Computação

**Projeto SymPy**   
Uma ferramenta para visualização de equações e formulas matemáticas, e para cálculo simbolico de equações.

Por exemplo, a raiz de 3 não possui um valor finito, então ao avaliar a expressão sqrt(3), o computador é limitado ao número de casas decimais. Com SymPy, é possível abstrair a avaliação da expressão, e trabalhar com a raiz simbólica, ou seja o operador √(3)

Projeto original: https://github.com/sympy/sympy.github.com   
Autores: https://www.sympy.org/   

Gist: https://gist.github.com/mathiashemmer/1bd4a77d65de344a4d2e57fd30ada2cc

Drive: https://colab.research.google.com/drive/1yUX0aolqYUg5uCon-zCAiukuRju1mPtH


# SymPy Website

[![Build
Status](https://travis-ci.org/sympy/sympy.github.com.svg?branch=sources)](https://travis-ci.org/sympy/sympy.github.com)

This is the SymPy website served at:

http://sympy.org/

using GitHub Pages.

To modify it, edit the files in the `templates` directory. You can check the
output with

    ./generate

You need to install jinja2 (http://jinja.pocoo.org/) and Babel
(http://pypi.python.org/pypi/Babel).

To see the output with styling, you will need to run a HTTP server. The
easiest way to do this is to run

    python -m http.server

and then open [0.0.0.0:8000](0.0.0.0:8000) in your browser.

The website is generated automatically on [Travis
CI](https://travis-ci.org/sympy/sympy.github.com). The pages are served
using GitHub pages from the
[`gh-pages`](https://github.com/sympy/sympy.github.com/tree/gh-pages) branch. All
modifications should be made to the
[`sources`](https://github.com/sympy/sympy.github.com/tree/sources) branch. The
`gh-pages` branch is generated automatically.

Note that all files at the root of the `sources` branch are synced to the
`gh-pages` branch. If you want to add additional files that are not translated,
they can be added there. But consider:

- Any page with content should be added to `templates` so that it can be
translated.

- Any images should be added to `media`.

- Any styling changes should be made in
  the [sympy-web-static](https://github.com/sympy/sympy-web-static)
  repository. This repository is added as a submodule in the `static`
  directory.

## Translations

The web pages for each language are generated into the `cs`, `de`, `en`
directories. In order to add a new language, first extract all translatable
texts into a `.pot` file using

    ./extract_i18n_text

It will appear in the i18n directory. Then translate it by creating a `.po` file
with the translation in the i18n directory. Compile it using

    ./compile_i18n

Then add the language in the generate script, generate the pages and commit the
generated files. Don't forget to add the new language in the `base.html` so that
one can switch into it.
