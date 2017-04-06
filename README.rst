####################
IS 210 Assignment 11
####################
************
Warmup Tasks
************

:College: CUNY School of Professional Studies
:Course-Name: Software Application Programming I
:Course-Code: IS 210

Overview
========

In this assignment, you'll be introduced to Python's classes and use them
in isolated contexts to get a feel for how they work.

Instructions
============

The following tasks will either have you interacting with existing files in
the assignment repository or creating new ones on the fly. Don't forget to add
your interpreter directive, utf-8 encoding, and a short docstring with any new
files that you create!

.. important::

    In these exercises, you may, on occasion, come across a task that requres
    you to research or use a function or method not directly covered by the
    course text. Since Python is such a large language it would be impossible
    for the author to have included descriptions of each and every available
    function which would largely duplicate the offical Python documentation.

    A *vital* skill to successful programming is being comfortable searching
    for and using official language documentation sources like the
    `Python String Documentation`_ page. Throughout our coursework we will be
    practicing both the use of the language in practice and the search skills
    necessary to become functional programmers.

Warmup Tasks
============

Task 01
-------

You've already instantiated and used some classes already if you consider
your prior use of such classes like the ``Decimal()`` class. Here you'll be
instantiating and accessing custom class instances.

Specifications
^^^^^^^^^^^^^^

#.  Create a new module named ``task_01.py``. In ``task_01.py``:

#.  Import the ``produce`` module

#.  Create two instances of the ``Produce()`` class

    #.  The first should not be passed any constructor variables and should be
        assigned to a variable named ``TOMATO``

    #.  The next should be named ``EGGPLANT`` and the constructor should be
        passed the value of ``1311210802``

#.  Access the ``arrival`` attribute of ``TOMATO`` and save it to a variable
    named ``TOMATO_ARRIVAL``

#.  Call the ``get_expiration()`` method of ``EGGPLANT`` and save its result
    to a variable named, ``EGGPLANT_EXPIRES``

Examples
^^^^^^^^

.. code:: pycon

    >>> isinstance(TOMATO, produce.Produce)
    True
    >>> isinstance(EGGPLANT, produce.Produce)
    True

Task 02
-------

In this task you'll be creating your own class from the ground-up.

Specifications
^^^^^^^^^^^^^^

#.  Create a new file named ``task_02.py``. In ``task_02.py``:

#.  Import the ``time`` module. This module provides functions specifically
    related to time. We'll use it for its ``time()`` function which returns a
    `Unix Timestamp`_ 

#.  Create a class named ``Snapshot``

#.  Create a constructor for ``Snapshot``

#.  In the constructor, create an *instance attribute* named ``created`` and
    assign it the output of ``time.time()`` which returns the current
    `Unix Timestamp`_

.. tip::

    Classes without an explicit parent class should always be subclassed to the
    generic ``object`` class.

Examples
^^^^^^^^

.. code:: pycon

    >>> mysnap = Snapshot()
    >>> hasattr(mysnap, 'created')
    True

Task 03
-------

Subclasses are part of the heart and soul of object-oriented programming. Here,
we'll be subclassing an existing class to slightly alter its properties.

Specifications
^^^^^^^^^^^^^^

#.  Create a new file named ``task_03.py``. In ``task_03.py``:

#.  Import the ``produce`` module

#.  Create a new class named ``Apple`` that is subclassed from
    ``produce.Produce``

#.  Update the *class attribute* named ``duration`` to a new value of
    ``5356800``

Examples
^^^^^^^^

.. code:: pycon

    >>> print Apple.duration
    5356800
    >>> print produce.Produce.duration
    604800

Task 04
-------

In this exercise, we'll be using subclassing, to demonstrate both the
*has-a* and *is-a* concepts. Take a peek inside the ``car`` module as we'll be
extending the ``Car()`` class found inside.

Specifications
^^^^^^^^^^^^^^

#.  Create a new module named ``task_04.py``.

#.  Import the ``car`` module.

#.  Create a class named ``CustomCar()`` that is itself, a child-class of
    ``car.Car``

#.  Create a class named ``CustomTire()`` that is, itself, a child-class of
    ``car.Tire``

#.  Override the class constructor ``CustomCar()`` has inherited from ``Car()``
    and, in it, call the ``Car()`` constructor. To do this, you must call the
    ``car.Car()`` constructor as a *class method* and **not** as an *instance
    method*. A snippet containing this construction is as below:
    below:

    .. code:: python

        car.Car.__init__(self, color)

    This calls the constructor to do its work but *instead* of creating a new
    instance of ``car.Car()`` we pass it the current instance of
    ``CustomCar()`` as ``self``.

#.  Add an additional argument named, ``tires`` to the ``CustomCar()``
    constructor.

    #.  Generally, this should be a list of ``CustomTire()`` objects

    #.  The default of this argument should be ``None``

#.  Add a new *instance attribute* to ``CustomCar()`` called
    ``tires`` to store a list of tires

    #.  Assign the new instance attribute the value of the ``tires`` argument

    #.  If the value of the ``tires`` argument is ``None``:

        #.  Create a list

        #.  Create four new instances of the ``CustomTire()`` class and append
            each into the list

#.  Add a pseudo-private *class attribute* to the ``CustomTires()`` class
    called ``__maximum_miles`` and assign it a value of ``500``.

#.  Test that your ``CustomCar()`` class works with both a ``tires`` argument
    and without.

Examples
^^^^^^^^

.. code:: pycon

    >>> mycar = CustomCar()
    >>> len(mycar.tires)
    4
    >>> isinstance(mycar.tires[0], CustomTire)
    True

Executing Tests
===============

Code must be functional and pass tests before it will be eligible for credit.

Linting
-------

Lint tests check your code for syntactic or stylistic errors To execute lint
tests against a specific file, simply open a terminal in the same directory as
your code repository and type:

.. code:: console

    $ pylint filename.py

Where ``filename.py`` is the name of the file you wish to lint test.

Unit Tests
----------

Unit tests check that your code performs the tested objectives. Unit tests
may be executed individually by opening a terminal in the same directory as
your code repository and typing:

.. code:: console

    $ nosetests tests/name_of_test.py

Where ``name_of_test.py`` is the name of the testfile found in the ``tests``
directory of your source code.

Running All Tests
-----------------

All tests may be run simultaneously by executing the ``runtests.sh`` script
from the root of your assignment repository. To execute all tests, open a
terminal in the same directory as your code repository and type:

.. code:: console

    $ ./runtests.sh

Submission
==========

Code should be submitted via Blackboard.

.. _GitHub: https://github.com/
.. _Python String Documentation: https://docs.python.org/2/library/stdtypes.html
.. _Unix Timestamp: https://en.wikipedia.org/wiki/Unix_time
