About this fork
---------------
An attempt to refactor fluent.runtime.

Notes for whoever is interested in this fork:

- Do not expect my commits to be logical. I am new to developing with GitHub and Git, it feels too distracting and unrealistic for me to commit & message in a way that the message *perfectly* describes the commit. So often(?) the commit messages only describe the **main** changes of the commit or **one or some of** the changes in the commit.

  (Some people commit per file change (?), but it feels too verbose, and I feel I will likely make changes hard to summarize and end up saying very general messages like "Do one thing", "Change files a.py, b.txt" that way, which are too general to be really useful)
- I am not sure if it is required to use my real name for Git commits. It seems that almost everyone else don't bother using their real name, but I would prefer to keep it secret (if possible).
- Code will be rewritten if it feels unclear.

Unresolved questions for refactoring:

.. ::raw: html
   </summary>

- Is the project architecture designed to be same as fluent.js, fluent-rs? If so, do the classes correspond trivially?

  Specifically, what does FluentLocalization correspond to?
- Should I fix failing tests first? Saw these failures at 17dfdd4c (output of VS Code task "Test fluent.syntax and fluent.runtime") (Python 3.13.1)

  .. code-block:: plain

     # Test fluent.syntax
     ====================
     ........................................................................................................................................................................................................................................................................
     ----------------------------------------------------------------------
     Ran 264 tests in 0.189s

     OK

     # Test fluent.runtime
     =====================
     ....................................................................................................................................................E.F.F.D:\study-coding\python-fluent\fluent.runtime\fluent\runtime\types.py:361: UserWarning: FluentDateType option hour12 is not yet supported
       warnings.warn(f"FluentDateType option {k} is not yet supported")
     ................s...............
     ======================================================================
     ERROR: test_bundles (tests.test_fallback.TestLocalization.test_bundles)
     ----------------------------------------------------------------------
     Traceback (most recent call last):
       File "D:\software\Python\Python313\Lib\unittest\mock.py", line 1424, in patched
         return func(*newargs, **newkeywargs)
       File "D:\study-coding\python-fluent\fluent.runtime\tests\test_fallback.py", line 34, in test_bundles
         bundle_de = next(bundles_gen)
     StopIteration

     ======================================================================
     FAIL: test_all_exist (tests.test_fallback.TestResourceLoader.test_all_exist)
     ----------------------------------------------------------------------
     Traceback (most recent call last):
       File "D:\software\Python\Python313\Lib\unittest\mock.py", line 1424, in patched
         return func(*newargs, **newkeywargs)
       File "D:\study-coding\python-fluent\fluent.runtime\tests\test_fallback.py", line 64, in test_all_exist
         self.assertEqual(len(resources_list), 1)
         ~~~~~~~~~~~~~~~~^^^^^^^^^^^^^^^^^^^^^^^^
     AssertionError: 0 != 1

     ======================================================================
     FAIL: test_one_exists (tests.test_fallback.TestResourceLoader.test_one_exists)
     ----------------------------------------------------------------------
     Traceback (most recent call last):
       File "D:\software\Python\Python313\Lib\unittest\mock.py", line 1424, in patched
         return func(*newargs, **newkeywargs)
       File "D:\study-coding\python-fluent\fluent.runtime\tests\test_fallback.py", line 76, in test_one_exists
         self.assertEqual(len(resources_list), 1)
         ~~~~~~~~~~~~~~~~^^^^^^^^^^^^^^^^^^^^^^^^
     AssertionError: 0 != 1

     ----------------------------------------------------------------------
     Ran 186 tests in 0.237s

     FAILED (failures=2, errors=1, skipped=1)

  However `the latest GitHub Actions test on original repo passed <https://github.com/projectfluent/python-fluent/actions/runs/10113936886/job/27971404861>`_.

.. ::raw: html
   </details>

Project Fluent
==============

This is a collection of Python packages to use the `Fluent localization
system <http://projectfluent.org/>`__.

python-fluent consists of these packages:

``fluent.syntax``
-----------------

The `syntax package <fluent.syntax>`_ includes the parser, serializer, and traversal
utilities like Visitor and Transformer. You’re looking for this package
if you work on tooling for Fluent in Python.

``fluent.runtime``
------------------

The `runtime package <fluent.runtime>`__ includes the library required to use Fluent to localize
your Python application. It comes with a ``Localization`` class to use,
based on an implementation of ``FluentBundle``. It uses the tooling parser above
to read Fluent files.

``fluent.pygments``
-------------------

A `plugin for pygments <fluent.pygments>`_ to add syntax highlighting to Sphinx.

Discuss
-------

We’d love to hear your thoughts on Project Fluent! Whether you’re a
localizer looking for a better way to express yourself in your language,
or a developer trying to make your app localizable and multilingual, or
a hacker looking for a project to contribute to, please do get in touch
on the mailing list and the IRC channel.

-  Mozilla Discourse: https://discourse.mozilla.org/c/fluent
-  Matrix channel:
   `#fluent:mozilla.org <https://chat.mozilla.org/#/room/#fluent:mozilla.org>`__

Get Involved
------------

python-fluent is open-source, licensed under the Apache License, Version
2.0. We encourage everyone to take a look at our code and we’ll listen
to your feedback.
