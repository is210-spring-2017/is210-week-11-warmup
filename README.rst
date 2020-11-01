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

In this exercise, we'll be using subclassing, to demonstrate both the
*has-a* and *is-a* concepts. Take a peek inside the ``car`` module as we'll be
extending the ``Car()`` class found inside.

Specifications
^^^^^^^^^^^^^^

#.  Use a new cell in your notebook

#.  Pase the following code into your cell:

.. code:: pycon
class Car(object):
    def __init__(self, color='red'):
        self.color = color
        
class Tire(object):
    def __init__(self, miles=0):
        self.miles = miles
    def add_miles(self, miles):
        self.miles += miles


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

Expected Output
^^^^^^^^

.. code:: pycon

    >>> mycar = CustomCar()
    >>> len(mycar.tires)
    4
    >>> isinstance(mycar.tires[0], CustomTire)
    True



Code should be submitted via Blackboard.

.. _GitHub: https://github.com/
.. _Python String Documentation: https://docs.python.org/2/library/stdtypes.html
.. _Unix Timestamp: https://en.wikipedia.org/wiki/Unix_time
