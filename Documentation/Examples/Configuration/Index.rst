.. ==================================================
.. FOR YOUR INFORMATION
.. --------------------------------------------------
.. -*- coding: utf-8 -*- with BOM.



.. _configuration:

Configuration Reference
=======================

http://wiki.typo3.org/ReST_Syntax

http://docs.typo3.org/typo3cms/drafts/github/marble/DocumentationStarter/Chapter1/SubChapter/TopicC.html

Technical information: Installation, Reference of TypoScript options,
configuration options on system level, how to extend it, the technical
details, how to debug it and so on.

.. note:: This is a note admonition.

	These notes are similar to tips, but usually contain information you should pay attention to. It might be details about a step that a whole operation hinges on or it may highlight an essential sequence of tasks.

	- The note contains all indented body elements following.
	- It includes this bullet list.


.. tip::

   Take a break from time to time!

Admonitions should be used to warn the users about potential
pitfalls, attract their attention to important elements
or just add some notes for for information (further reading,
for example).

.. important::

   Remember to always say "please" when asking your software to
   do something.


.. attention::

   Some directives of the Docutils have different
   names in Sphinx or work differently.

.. warning::

	These notes draw your attention to things that can interrupt your service or website if not done correctly. Some actions can be difficult to undo.



..

   Remember to always say "please" when asking your software to
   do something.

.. _configuration-typoscript:

TypoScript Reference
--------------------

Possible subsections: Reference of TypoScript options.
The construct below show the recommended structure for
TypoScript properties listing and description.

Properties should be listed in the order in which they
are executed by your extension, but the first should be
alphabetical for easier access.

When detailing data types or standard TypoScript
features, don't hesitate to cross-link to the TypoScript
Reference as shown below. See the :file:`Settings.yml`
file for the declaration of cross-linking keys.


Properties
^^^^^^^^^^

.. container:: ts-properties

	=========================== ===================================== ======================= ====================
	Property                    Data type                             :ref:`t3tsref:stdwrap`  Default
	=========================== ===================================== ======================= ====================
	allWrap_                    :ref:`t3tsref:data-type-wrap`         yes                     :code:`<div>|</div>`
	`subst\_elementUid`_        :ref:`t3tsref:data-type-boolean`      no                      0
	wrapItemAndSub_             :ref:`t3tsref:data-type-wrap`
	=========================== ===================================== ======================= ====================


Property details
^^^^^^^^^^^^^^^^

.. only:: html

	.. contents::
		:local:
		:depth: 1


.. _ts-plugin-tx-extensionkey-stdwrap:

allWrap
"""""""

:typoscript:`plugin.tx_extensionkey.allWrap =` :ref:`t3tsref:data-type-wrap`

Wraps the whole item.


.. _ts-plugin-tx-extensionkey-wrapitemandsub:

wrapItemAndSub
""""""""""""""

:typoscript:`plugin.tx_extensionkey.wrapItemAndSub =` :ref:`t3tsref:data-type-wrap`

Wraps the whole item and any submenu concatenated to it.


.. _ts-plugin-tx-extensionkey-substelementUid:

subst_elementUid
""""""""""""""""

:typoscript:`plugin.tx_extensionkey.subst_elementUid =` :ref:`t3tsref:data-type-boolean`

If set, all appearances of the string ``{elementUid}`` in the total
element html-code (after wrapped in allWrap_) are substituted with the
uid number of the menu item. This is useful if you want to insert an
identification code in the HTML in order to manipulate properties with
JavaScript.


API
---

How to use the API...

.. code-block:: php

	$stuff = \TYPO3\CMS\Core\Utility\GeneralUtility::makeInstance(
		'\\Foo\\Bar\\Utility\\Stuff'
	);
	$stuff->do();

or some other language:

.. code-block:: javascript
   :linenos:
   :emphasize-lines: 2-4

	$(document).ready(
		function () {
			doStuff();
		}
	);


Headline 3
----------

Headline 4
^^^^^^^^^^

Headline 5
""""""""""

Headline 6
~~~~~~~~~~+++

Alternatively a grid table can be used. As tip, Emacs editor provides some facilities_ to edit grid table. A recommended tutorial can be found at http://www.emacswiki.org/emacs/TableMode. ::


	+------------+------------+-----------+
	| Header 1   | Header 2   | Header 3  |
	+============+============+===========+
	| body row 1 | column 2   | column 3  |
	+------------+------------+-----------+
	| body row 2 | Cells may span columns.|
	+------------+------------+-----------+
	| body row 3 | Cells may  | - Cells   |
	+------------+ span rows. | - contain |
	| body row 4 |            | - blocks. |
	+------------+------------+-----------+

Side bar
========

A sidebar is typically offset by a border and "floats" to the side of the page; the document's main text may flow around::

	.. sidebar:: Here a side bar

		This box is going to be shifted to the right corner which can be useful to display pointers or other kind of side information.


Substitutions
=============

ReST supports “substitutions”, which are pieces of text and/or markup referred to in the text by |name|. Substitution are to be included in file ``_IncludedDirectives`` to be avaiable across the documentation. They are defined like footnotes with explicit markup blocks, like this::

	.. |name| replace:: replacement *text*

