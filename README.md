sphinx-mobi
===========

Patch Sphinx code to enable kindle/mobi support.

Requirements
------------
I assume that you'll be able to download Sphinx-1.1.3 release as well as
install on your system kindlegen. The former is provided
[here](http://pypi.python.org/pypi/Sphinx), while later can be found on
Amazon Kindle support
[page](http://www.amazon.com/gp/feature.html?ie=UTF8&docId=1000765211).

Description
-----------

This is a fork for Sphinx 1.1.3 code with changes to enable support for
Kindle (mobi data format). Basically I copied epub, tweak themes, core code and
add mobi option into sphinx-quickstart.

Install
-------

To install, please get sphinx-1.1.3.mobi.patch and patch your vanila
Sphinx-1.1.3 code base with the following command:

    cd Sphinx-1.1.3
    patch -p1 < sphinx-1.1.3.mobi.patch
    cp sphinx/themes/basic/static/file.png sphinx/themes/mobi/static/file.png
    cp kindle-logo.jpg sphinx/themes/mobi/static/

Then build and install your Sphinx in a usual way

::

    python setup.py install --prefix=<your_install_path>

Build your mobi
---------------

Once everything in place, run sphinx-quickstart in a usual way, and answer
``y`` to the following questions:

* Do you want to use the kindle/mobi builder (y/N) [n]: y
* pngmath: include math, rendered as PNG images (y/N) [n]: y

The former enable mobi option in generated Makefile, while later allows you to
embed LaTeX formulas into your mobi book.

Example
-------

You can find the source code as well as generated kindle.mobi file in example
directory.

Future
------

Once time permit I'll look further in customization of mobi builder in sphinx
code. Upon that time, I'm happy with this preliminary hack.
