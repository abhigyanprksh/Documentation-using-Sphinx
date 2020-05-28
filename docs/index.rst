

.. toctree::
   :local:
   


Welcome to Cratekube's documentation 
=====================================

************
Introduction
************

This is a proof of concept for using Sphinx with Read the Docs to build interactive documentation from git repositories. `Sphinx <https://www.sphinx-doc.org/en/master/>`_ is a very versatile documentation generator that uses reStructuredText as its native markup language.


*************
GitHub Setup
*************

* Create a git repository. The hierarchy of directories are a matter of choice. Setup explained here is with respect to the setup `here <https://github.com/abhigyanprksh/Documentation-using-Sphinx>`_.
* ``docs/``: All the documentation content goes here. Sphinx, by default, expects the content to be in reStructuredText format.
* ``docs/conf.py``: All the configurations for building the documents are specified here. Some of the configurable attributes are explained `here <https://www.sphinx-doc.org/en/master/usage/configuration.html>`_.
* ``.readthedocs.yml``: It is a `configuration <https://docs.readthedocs.io/en/stable/config-file/index.html>`_ file used by Read the Docs. It specifies attributes like document generation engine, path to the configuration file (``conf.py``), python version and path to a ``requirements.txt`` file to specify additional dependencies.
* ``requirements/requirements.txt``: This file lists any additional dependencies for the build. 

***************
Using Markdown
***************

* Markdown can be used to write documentation files by using `this <https://recommonmark.readthedocs.io/en/latest/>`_ Sphinx extension.
* `This <https://pandoc.org/try/>`_ is a good tool for converting texts among popular markup formats.
* However, since many of the Sphinx's extensions are designed to work with reStructuredText, it is suggested to use the same. 




************************
Using with Read the Docs
************************

* Since we have already created a ``.readthedocs.yml`` file, all we need to do is to import the repository on Read the Docs and proceed with the build. Project name and versioning can be specified there. 


**************************
Using interactive widgets
**************************

* One good option for embedding Jupyter widgets that can be executed live is to use ``jupyter-sphinx`` extension. 
* Its fairly simple to use, and the documentation can be found `here <https://jupyter-sphinx.readthedocs.io/en/latest/>`_.
* All we need to do is to specifiy ``jupyter-sphinx.execute`` in the extensions in our ``conf.py`` and ``jupyter-sphinx`` should be added to the ``requirements.txt`` file. 
* ``jupyter-sphinx`` doesn't work with Markdown, so the only choice is to go ahead with reStructuredText.
* There is a bug with ``jupyter-sphinx`` in the latest version, the widgets are not rendered on Read the Docs. So, the previous version has to be used and the version has to be specified in the ``requirements.txt`` file. The latest version that works is ``v0.2.3``, hence ``jupyter-sphinx==0.2.3`` has to be added in the ``requirements.txt`` instead of ``jupyter-sphinx`` as it would pull the latest version.
* This extension also supports `theblab <https://thebelab.readthedocs.io/en/latest/>`_.

***************
Example Widget
***************

Click on `Make live` to turn the code snippet into an executable widget.

.. jupyter-execute::
  	:hide-output:

  	name = 'world'
  	print('hello ' + name + '!')











   



