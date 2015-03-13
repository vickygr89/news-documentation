.. ==================================================
.. FOR YOUR INFORMATION
.. --------------------------------------------------
.. -*- coding: utf-8 -*- with BOM.

.. include:: ../../../Includes.txt


TsConfig
--------

This section covers all configurations which can be set with TsConfig.
Every configuration starts with ``tx_news.``.



Properties
^^^^^^^^^^

.. container:: ts-properties

	=========================== =====================================
	Property                    Data type
	=========================== =====================================
	singlePid_        :ref:`t3tsref:data-type-boolean`
	templateLayouts_             :ref:`t3tsref:data-type-wrap`
	archive_             :ref:`t3tsref:data-type-wrap`
	=========================== =====================================

	=========================== =====================================
	Property                    Data type
	=========================== =====================================
	preselect_                    :ref:`t3tsref:data-type-array`
	defaultPid_                    :ref:`t3tsref:data-type-array`
	redirectToPageOnStart_                    :ref:`t3tsref:data-type-array`
	allowedPage_                    :ref:`t3tsref:data-type-array`
	=========================== =====================================




TODO Clear caches if a news record changes
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

If a news record is created or edited, chances are high that the changes are not visible in the frontend as the output is still cached.
Therefore you need to clear the caches of the list and single view pages. This can be done automatically by using this command in the PageTsConfig: ::

	TCEMAIN.clearCacheCmd = 123,456,789


The code needs to be added to the sys folder where the news records are edited. Change the example page ids to the ones which should be cleared, e.g. the one of list views and detail view.
You can use: ::

	TCEMAIN.clearCacheCmd = pages

to clear the complete caches as well

	TCEMAIN.clearCacheCmd = cacheTag:tx_news

to clear all caches of pages on which the news plugins are used

.. tip::

	The mentioned TCEMAIN settings are part of the TYPO3 core and can be used therefore not only for the news extension.
