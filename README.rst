====
Vega
====

.. image:: https://travis-ci.com/andreicuceu/vega.svg?branch=master
    :target: https://travis-ci.com/andreicuceu/vega

.. image:: https://readthedocs.org/projects/lyafit/badge/?version=latest
        :target: https://vega.readthedocs.io/en/latest/?badge=latest

.. image:: https://codecov.io/gh/andreicuceu/Vega/branch/master/graph/badge.svg
        :target: https://codecov.io/gh/andreicuceu/Vega



Vega is a tool for computing 3D correlation function models for tracers used by the Ly-:math:`\alpha` forest group (such as Ly-:math:`\alpha` flux, Quasar positions or different metal lines) and for fitting data produced by `picca <https://github.com/igmhub/picca>`__ primarily to measure Baryon Acoustic Oscillations (BAO).


* Free software: GPL-3.0 License
* Documentation: https://vega.readthedocs.io.

Installation
------------

You can either clone the public repository:

.. code-block:: console

    $ git clone git://github.com/andreicuceu/Vega

Or download the `tarball`_:

.. code-block:: console

    $ curl -OJL https://github.com/andreicuceu/Vega/tarball/master

Once you have a copy of the source, you can install it with:

.. code-block:: console

    $ cd Vega
    $ pip install -r requirements.txt
    $ pip install .

If you want to run the sampler you will need `Polychord`_. Instructions can be found `here`_, and will be added to this repo soon.

.. _tarball: https://github.com/andreicuceu/Vega/tarball/master
.. _Polychord: https://github.com/PolyChord/PolyChordLite
.. _here: https://github.com/andreicuceu/fitter2_tutorial

Usage
-----

Vega can be used both interactively (e.g. from Jupyter Notebooks) or from the command line. It needs a config file to run: main.ini.

This main.ini file must also contain the paths to extra configuration files. One of these extra files is needed for each correlation component. E.g. for a run with LyaxLya and QSOxLya, you would need 3 config files:

- main.ini
- lyaxlya.ini
- qsoxlya.ini

Example config files can be found in the `examples`_ folder, and detailed descriptions of all the possible options can be found in the documentation. (Work in progress)

Examples for the interactive use can be found in the `tutorial`_ . Most of Vega functionality can be accessed and used entirely from a Notebook, but compute times might be long if you try to minimize over too many parameters (especially if they are degenerate). 

The only thing that needs to be run from the console is the sampler. It can be called using the 'vega_mpi.py' script in the bin folder like this:

.. code-block:: console

    $ python run_vega_mpi.py path_to/main.ini

We strongly suggest you run the sampler in parallel on many cores, as normal run-times are of the order :math:`10^2` - :math:`10^4` core hours.

.. _examples: https://github.com/andreicuceu/Vega/tree/master/examples
.. _tutorial: https://github.com/andreicuceu/Vega/blob/master/examples/Vega_tutorial.ipynb

Credits
-------

This package is based on picca fitter2 found here: https://github.com/igmhub/picca/tree/master/py/picca/fitter2, and was created with Cookiecutter_ and the `audreyr/cookiecutter-pypackage`_ project template.

.. _Cookiecutter: https://github.com/audreyr/cookiecutter
.. _`audreyr/cookiecutter-pypackage`: https://github.com/audreyr/cookiecutter-pypackage
