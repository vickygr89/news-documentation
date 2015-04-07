.. ==================================================
.. FOR YOUR INFORMATION
.. --------------------------------------------------
.. -*- coding: utf-8 -*- with BOM.

.. include:: ../../Includes.txt


Plugin
------

The news plugin is used to output a defined list of records.

It can be added to create a content element with the type "*Plugin*" and by selecting the plugin type "**News system**".

TODO: screenshot

.. only:: html

   The available actions are:

   .. contents::
        :local:
        :depth: 1

List
^^^^
TODO

Detail
^^^^^^

There are 2 typical use cases for this action:

- Use this action to show a full news record which is linked by a list view.
- Provide a specific news record to output that one. This is very useful to embed a news record e.g. in a newsletter.

Date menu
^^^^^^^^^
Use this action to show a list of news items grouped by the date. A typical output can look like: ::

	2015
		January: 13 entries
		February: 9 entries
		March: 6 entries
		June: 4 entries
		...
	2014
		March: 81 entries
		April: 32 entries
		May: 1 entry


If you define a specific page id in field "**PageId for list display**" (inside the tab "*Additional*") and
placing a news plugin with the type "**List**" there, it is possible to create a date filter.

Search form
^^^^^^^^^^^
Use this action to show a basic search inside news records.

Search result
^^^^^^^^^^^^^
The search result action is based on the list action including an additional filter provided by the search form.

Category menu
^^^^^^^^^^^^^
Use this action to show a list of categories. The categories are listed as tree.

If you define a specific page id in field "**PageId for list display**" (inside the tab "*Additional*") and
placing a news plugin with the type "**List**" there, it is possible to create a category filter.

Tag list
^^^^^^^^
Use this action to show a list of tags.

If you define a specific page id in field "**PageId for list display**" (inside the tab "*Additional*") and
placing a news plugin with the type "**List**" there, it is possible to create a tag filter.