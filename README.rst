pl-CNI_challenge_ChRIS
================================

.. image:: https://badge.fury.io/py/cni_challenge_chris.svg
    :target: https://badge.fury.io/py/cni_challenge_chris

.. image:: https://travis-ci.org/FNNDSC/cni_challenge_chris.svg?branch=master
    :target: https://travis-ci.org/FNNDSC/cni_challenge_chris

.. image:: https://img.shields.io/badge/python-3.5%2B-blue.svg
    :target: https://badge.fury.io/py/pl-cni_challenge_chris

.. contents:: Table of Contents


Abstract
--------

An app to ...


Synopsis
--------

.. code::

    python cni_challenge_chris.py                                           \
        [-v <level>] [--verbosity <level>]                          \
        [--version]                                                 \
        [--man]                                                     \
        [--meta]                                                    \
        <inputDir>
        <outputDir> 

Description
-----------

``cni_challenge_chris.py`` is a ChRIS-based application that...

Agruments
---------

.. code::

    [-v <level>] [--verbosity <level>]
    Verbosity level for app. Not used currently.

    [--version]
    If specified, print version number. 
    
    [--man]
    If specified, print (this) man page.

    [--meta]
    If specified, print plugin meta data.


Run
----

This ``plugin`` can be run in two modes: natively as a python package or as a containerized docker image.

Using PyPI
~~~~~~~~~~

To run from PyPI, simply do a 

.. code:: bash

    pip install cni_challenge_chris

and run with

.. code:: bash

    cni_challenge_chris.py --man /tmp /tmp

to get inline help. The app should also understand being called with only two positional arguments

.. code:: bash

    cni_challenge_chris.py /some/input/directory /destination/directory


Using ``docker run``
~~~~~~~~~~~~~~~~~~~~

To run using ``docker``, be sure to assign an "input" directory to ``/incoming`` and an output directory to ``/outgoing``. *Make sure that the* ``$(pwd)/out`` *directory is world writable!*

Now, prefix all calls with 

.. code:: bash

    docker run --rm -v $(pwd)/out:/outgoing                             \
            fnndsc/pl-cni_challenge_chris cni_challenge_chris.py                        \

Thus, getting inline help is:

.. code:: bash

    mkdir in out && chmod 777 out
    docker run --rm -v $(pwd)/in:/incoming -v $(pwd)/out:/outgoing      \
            fnndsc/pl-cni_challenge_chris cni_challenge_chris.py                        \
            --man                                                       \
            /incoming /outgoing

Examples
--------





