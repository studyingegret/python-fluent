About this fork
---------------
An attempt to refactor fluent.runtime.

Notes for whoever is interested in this fork:
- Do not expect my commits to be logical. I am new to developing with GitHub and Git, it feels too distracting and unrealistic for me to commit & message in a way that the message *perfectly* describes the commit. So often(?) the commit messages only describe the **main** changes of the commit or **one or some of** the changes in the commit.
- I am not sure if it is required to use my real name for Git commits. It seems that almost everyone else don't bother using their real name, but I would prefer to keep it secret (if possible).

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
