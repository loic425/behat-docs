Format Options
==============

Behat supports different ways of printing output information. Output printers
in ``behat`` are called *formats* or *formatters*. You can tell ``behat`` to
run with a specific formatter by providing the ``--format`` option:

.. code-block:: bash

    $ behat --format progress

.. note::

    The default formatter is ``pretty``.

``behat`` supports 2 formatters out of the box:

* ``pretty`` - prints the feature as is:

    .. image:: /images/formatter-pretty.png
       :align: center

* ``progress`` - prints one character per step:

   .. image:: /images/formatter-progress.png
      :align: center


If you don't want to print output to the console, you can tell ``behat``
to print output to a file instead of ``STDOUT`` with the ``--out`` option:

.. code-block:: bash

    $ behat --format pretty --out report.txt

.. note::

    Some formatters, like ``junit``, always require the ``--out`` option to be
    specified. The ``junit`` formatter generates ``*.xml`` files for every
    suite, so it needs a destination directory to put these XML files into.

Also, you can specify multiple formats to be used by Behat using multiple --format options:

.. code-block:: bash

    $ behat --format pretty --format progress

In this case, default output will be used as output for both formatters. But if you want
them to use different ones - specify them with ``--out``:

.. code-block:: bash

    $ behat -f pretty -o ~/pretty.out -f progress -o std -f junit -o xml

In this case, output of pretty formatter will be written to ``~/pretty.out`` file, output of junit
formatter will be written to ``xml`` folder and progress formatter will just print to console.

Behat tries hard to identify if your terminal supports colors or not, but
sometimes it still fails. In such cases, you can force ``behat`` to
use colors (or not) with the options ``--colors`` or ``--no-colors``,
respectively:

.. code-block:: bash

    $ behat --no-colors
