.. ==================================================
.. FOR YOUR INFORMATION
.. --------------------------------------------------
.. -*- coding: utf-8 -*- with BOM.

.. include:: ../../../Includes.txt

.. _extendClasses:

Extending EXT:news
==================

Follow this chapter to learn how to add new fields or actions.

.. only:: html

	.. contents::
		:local:
		:depth: 1

Add a new field in the backend
------------------------------
To add new fields, use either the extension **extension_builder** (http://typo3.org/extensions/repository/view/extension_builder) or create the extension from scratch.

The extension key used in this examples is ``eventnews``.

Create the fields
^^^^^^^^^^^^^^^^^
3 files are basically all what you need:

ext_emconf.php
""""""""""""""
The file  ``ext_emconf.php`` holds all basic information about the extension like the title, description and version number.

.. code-block: php

	<?php

	$EM_CONF[$_EXTKEY] = array(
		'title' => 'news events',
		'description' => 'Events for news',
		'category' => 'plugin',
		'author' => 'Georg Ringer',
		'author_email' => '',
		'state' => 'alpha',
		'internal' => '',
		'uploadfolder' => '0',
		'createDirs' => '',
		'clearCacheOnLoad' => 1,
		'version' => '',
		'constraints' => array(
			'depends' => array(
				'typo3' => '6.2',
				'news' => '3.0.0',
			),
			'conflicts' => array(),
			'suggests' => array(),
		),
	);

SQL definition
""""""""""""""
Create the file ``ext_tables.sql`` in the root of the extension directory with the following content:

.. code-block: sql


	#
	# Table structure for table 'tx_news_domain_model_news '
	#
	CREATE TABLE tx_news_domain_model_news (
		location_simple varchar(255) DEFAULT '' NOT NULL
	);


TCA definition
""""""""""""""
The TCA defines which tables and fields are available in the backend and how those are rendered (e.g. as input field, textarea, select field, ...).

In this example, the table ``tx_news_domain_model_news`` will be extended by a simple input field.
Therefore, create the file ``Configuration/TCA/Overrides/tx_news_domain_model_news.php``.

.. code-block: php

	<?php
	defined('TYPO3_MODE') or die();

	$fields = array(
		'location_simple' => array(
			'exclude' => 1,
			'label' => 'My location',
			'config' => array(
				'type' => 'input',
				'size' => 15
			),
		)
	);

	\TYPO3\CMS\Core\Utility\ExtensionManagementUtility::addTCAcolumns('tx_news_domain_model_news', $fields);
	\TYPO3\CMS\Core\Utility\ExtensionManagementUtility::addToAllTCAtypes('tx_news_domain_model_news', 'location_simple');


Install the extension
^^^^^^^^^^^^^^^^^^^^^
Now you should be able to install the extension and if you open a news record, you should see the new field in the last tab.

TODO: what if something wrong


Register 