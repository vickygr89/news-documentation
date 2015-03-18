.. ==================================================
.. FOR YOUR INFORMATION
.. --------------------------------------------------
.. -*- coding: utf-8 -*- with BOM.

.. include:: ../../../Includes.txt


TypoScript
----------

.. warning::
	TODO: add plugin.tx_news.settings

Properties
^^^^^^^^^^

.. container:: ts-properties

	==================================== =============== ==================================================
	Property                             Type            Default
	==================================== =============== ==================================================
	cssFile_                              string          EXT:news/Resources/Public/Css/news-basic.css
	format_                               string          html
	overrideFlexformSettingsIfEmpty_      string          See below
	displayDummyIfNoMedia_                boolean         1
	detailPidDetermination_               string          flexform, categories, default
	defaultDetailPid_                     integer
	`subst\.elementUid`_                  basic
	==================================== =============== ==================================================


cssFile
"""""""

Path to the css file. This is included with the Layouts.

format
""""""

Set a different format for the output. Use e.g. “xml” for RSS feeds.

overrideFlexformSettingsIfEmpty
"""""""""""""""""""""""""""""""

The default behaviour of extbase is to override settings from
TypoScript by the one of the flexforms. This is even valid if the setting is
left empty in the flexforms.

Therefore you can define those settings which's value should be taken from TypoScript if nothing
is set in the plugin.

The default value is: ::

	cropMaxCharacters,dateField,timeRestriction,orderBy,orderDirection,backPid,listPid,startingpoint,recursive,list.paginate.itemsPerPage,list.paginate.templatePath


displayDummyIfNoMedia
"""""""""""""""""""""

If set and no preview image is defined, a placeholder image is shown. The placeholder itself is defined with TypoScript ::

	plugin.tx_news.settings.list.media.dummyImage = typo3conf/ext/news/Resources/Public/Images/dummy-preview-image.png

detailPidDetermination
""""""""""""""""""""""

This settings defines which page is used for the link to the detail view.
3 possible options are available which processed in the given order until a page has been found.

.. only:: html

	.. contents::
		:local:
		:depth: 1

flexform
~~~~~~~~

This type tries to get the detail page from the plugin's setting *PageId for single news display* which
can also be set by using TypoScript. ::

	# If set via TypoScript, also add detailPid to the setting "overrideFlexformSettingsIfEmpty"
	plugin.tx_news.settings.detailPid = 123

categories
~~~~~~~~~~

A detail page can also be defined for every category. Use the field **Single-view page for news from this category** for that.

default
~~~~~~~

This type tries to get the value from the setting *defaultDetailPid*. ::

	plugin.tx_news.settings.defaultDetailPid = 456

defaultDetailPid
""""""""""""""""

*See above*


subst.elementUid
""""""""""""""""

x