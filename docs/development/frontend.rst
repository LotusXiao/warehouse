Frontend
========

The Warehouse frontend is (as you might suspect) written in JavaScript with the
CSS handled by SCSS. It uses gulp to process these files and prepare them for
serving.

All of the static files are located in ``warehouse/static/`` and external
libraries are found in ``package.json``.


Building
--------

Static files should be automatically built when ``make serve`` is running,
however you can trigger a manual build of them by installing all of the
dependencies using ``npm install`` and then running ``gulp dist``.


Browser Support
---------------

========= ====================
 Browser  Supported Versions
========= ====================
 Chrome   Current, Current - 1
 Firefox  Current, Current - 1
 Edge     Current, Current - 1
 Opera    Current, Current - 1
 Safari   9.0+
 IE       11+
========= ====================


HTML Code Style
---------------

Warehouse follows the `Google HTML style guide <http://bit.ly/29gepl6>`_,
which is enforced via linting with `HTML Linter <http://bit.ly/29sf7Aa>`_.

Exceptions to these rules include:

- Protocols can be included in links - we prefer to include https protocols
- All HTML tags should be closed

We also allow both dashes and underscores in our class names, as we follow the
`Nicholas Gallagher variation <http://bit.ly/1g8225q>`_
of the `BEM naming methodology <https://en.bem.info/>`_.

More information on how BEM works can be found in
`this article from CSS Wizardry <http://bit.ly/1dM4LGz>`_.


SCSS Style and Structure
------------------------

Warehouse follows the `Airbnb CSS / Sass style guide <http://bit.ly/29geHZj>`_,
with the exception that JS hooks should be prefixed with ``-js`` rather
than ``js``.

Our SCSS codebase is structured according to the `ITCSS system
<http://bit.ly/1OHRsEw>`_.  The principle of this system is to break SCSS code
into layers and import them into a main stylesheet in an order moving from
generic to specific. This tightly controls the cascade of styles.

The majority of the SCSS styles are found within the 'blocks' layer,
with each BEM block in its own file. All blocks are documented at the top of
the file to provide guidelines for use and modification.
