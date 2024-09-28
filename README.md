# sphinx-autosummary-autocollect

Sphinx plugin based on autosummary, that automatically collects symbols if non are provided. 

## Installation

Install the latest built version via:
````commandline
pip install sphinx-autosummary-autocollect
````

To develop on this project, clone it via:
```commandline
git clone git@github.com:helpmefindaname/sphinx_autosummary_autocollect.git
cd sphinx_autosummary_autocollect
```
Then use [poetry](https://python-poetry.org/docs/#installation) to install the project: 
```
poetry install
```

## Usage

> **Note**
>
> This plugin was only tested with sphinx 7.4.7.
> If you are using a newer version and the plugin stops working, please create an [issue](https://github.com/helpmefindaname/sphinx_autosummary_autocollect/issues)

This plugin is based on [AutoSummary](https://www.sphinx-doc.org/en/master/usage/extensions/autosummary.html) and should be used the same way.
There are only 2 differences:
* in the `conf.py` the `extensions`-list should not contain `"sphinx.ext.autosummary"` but `"sphinx_autosummary_autocollect"`
* in the `.. autosummary::` you can provide no symbols. In that case `sphinx_autosummary_autocollect` will build a table and subpages for all elements that can be extracted from the "current-module"

for example, instead of specifying:
````rst
my_module
=========

.. currentmodule:: my_module

.. autosummary::
    :toctree: generated
    :nosignatures:
    
    class1
    function1
````
you can now leave the elements out:
````rst
my_module
=========

.. currentmodule:: my_module

.. autosummary::
    :toctree: generated
    :nosignatures:
````

> **Note**
>
> This is a note