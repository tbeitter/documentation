ownCloud Documentation
======================

This is the ownCloud documentation. It currently focuses on the server,
client manuals are in the respective git repositories. Because of the
complexity of the server and the split into the core and apps modules,
the manuals are in this separate directory.

License
-------

All documentation in this repository is licensed under the Creative Commons
Attribution 3.0 Unported license (`CC BY 3.0`_).

Style
-------

It is using the `Sphinx Documentation Generator
<http://sphinx.pocoo.org/>`_. The syntax follows the `reStructuredText
<http://docutils.sourceforge.net/rst.html>`_ style, and can also be edited
from GitHub.

For PHP documentation you'll need to get the according language
domain package. The documenation for PHP source is located at
http://packages.python.org/sphinxcontrib-phpdomain/reference.html

Manuals
-------

At this point, this repository hosts three manuals:

* **Users Manual:** Covers topics from an end user's Point of View
* **Administrators Manual:** Setup, Deployment, Best Practices, etc.
* **Developers Manual:** Developing Apps for ownCloud & understanding the
  core Architecture.

Building
--------

Linux / OS X
^^^^^^^^^^^^

First, make sure that the following are installed:

* Python 2 (2.6.0 or better, Python 3 is not yet supported!)
* Sphinx (e.g. ``sudo yum install python-sphinx``),
  on Mac: ``sudo easy_install Sphinx``
* Sphinx PHPDomain (e.g. ``sudo easy_install sphinxcontrib-phpdomain``)
* rst2pdf (e.g. ``sudo easy_install rst2pdf``)
* If you're on Arch Linux, the build script is called sphinx-build2 which
  will fail. You will need to provide a link to the expected script name::

     sudo ln -s /usr/bin/sphinx-build2 /usr/bin/sphinx-build

...then enter any manual directory, then run ``make html``. The result can
be found in the ``_build/html`` subdirectory.  PDFs can be build with the
``make latexpdf`` command and found

Windows
^^^^^^^

Running ``setup.cmd`` will install Python 2.7 and install all dependencies.

Enter any manual and clicking the "Build HTML" shortcut will create a HTML
build. Likewise, "Build PDF" will build the PDF using the more lightweight,
but feature-incomplete RST2PDF tool. The results are in ``_build/html`` and
``_build/pdf`` respectively.

Importing Word and OpenDocument files
-------------------------------------

Sometimes, existing documentation might be in Word or LibreOffice documents. To
make it part of this documentation collection, follow these steps:

Prerequisits
^^^^^^^^^^^^

1. Install Python 2.x
2. Install odt2shpinx (``easy_install odt2sphinx``)
3. Install GCC/clang (`Xcode command line tools`_ required on Mac OS)

Process
^^^^^^^

1. ``doc/docx`` files need to be stored as odt first
2. Run ``odt2sphinx my.docx``
3. Move the resulting ``rst`` files in place and reference them
4. Wrap text lines at 80 chars, apply markup fixes

.. _CC BY 3.0: http://creativecommons.org/licenses/by/3.0/deed.en_US
.. _`Xcode command line tools`: http://stackoverflow.com/questions/9329243/xcode-4-4-and-later-install-command-line-tools
