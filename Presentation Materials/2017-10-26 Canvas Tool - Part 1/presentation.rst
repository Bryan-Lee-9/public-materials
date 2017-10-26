.. _Hovercraft: https://github.com/regebro/hovercraft
.. Suggested template: https://github.com/sixfeetup/sixfeetup_hovercraft

  :title: ACM Meeting Slides
  :data-transition-duration: 1000

This file is meant to be viewed using Hovercraft_.
To view, execute::

  pipenv run hovercraft -t path/to/sixfeetup_hovercraft/template.cfg presentation.rst

----

Hello again!
============

----

.. image:: https://imgs.xkcd.com/comics/infrastructures.png
   :height: 600px

:title: The heartfelt tune it plays is CC licensed,
   and you can get it from my seed on JoinDiaspora.com whenever that project gets going.

(https://xkcd.com/743/)

----

.. What are we doing today?

Today we are making an app for Canvas
-------------------------------------

* Using a module called ``canvasapi`` from the University of Central Florida

----

.. What do we need to know in order to do it?

``canvasapi``
-------------

Installing:

.. code-block:: bash

   pip3 install canvasapi --user

Requires an access token

``canvasapi``
-------------

The basics

.. code-block:: python

   # Import the Canvas class
   from canvasapi import Canvas

   # Canvas API URL
   api_url = 'https://miamioh.instructure.com/api/v1/'
   # Canvas API key
   api_key = 'p@$$w0rd'

   # Initialize a new Canvas object
   canvas: Canvas = Canvas(api_url, api_key)

----

Getting courses
---------------

.. code-block:: python

   for course in canvas.get_courses():
      print(course)

Getting Assignments for a given Course
--------------------------------------

.. code-block:: python

   course = canvas.get_courses()[0]
   for assignment in course.get_assignments():
      print(assignment)

----

The plan
========

.. _miami-acm/public-materials: https://github.com/miami-acm/public-materials

#. Create a program that lists your courses
#. Modify it so it lists the assignments of a course of your choosing
#. Implement another feature of your choice

   * See the API under today's folder in `miami-acm/public-materials`_

----

Conclusion
==========

We made a useful program that interacted with Canvas.

----

See you next time
=================