.. ==================================================
.. FOR YOUR INFORMATION
.. --------------------------------------------------
.. -*- coding: utf-8 -*- with BOM.

.. include:: ../../Includes.txt

.. _installation:

Installation
============
The extension needs to be installed as any other extension of TYPO3 CMS:

#. Switch to the module “Extension Manager”.

#. Get the extension

   #. **Get it from the Extension Manager:** Press the “Retrieve/Update”
      button and search for the extension key *news* and import the
      extension from the repository.

   #. **Get it from typo3.org:** You can always get current version from
      `http://typo3.org/extensions/repository/view/news/current/
      <http://typo3.org/extensions/repository/view/news/current/>`_ by
      downloading either the t3x or zip version. Upload
      the file afterwards in the Extension Manager.

#. The Extension Manager offers some basic configuration which is
   explained :ref:`here <extensionManager>`.

Latest version from git
-----------------------
You can get the latest version from git by using the git command:

.. code-block:: bash

   git clone git://git.typo3.org/TYPO3CMS/Extensions/news.git

Preparation: Include static TypoScript
--------------------------------------
Be aware that before any plugin can be rendered in the frontend it is
necessary to include the static TypoScript of news. This is very easy:

#. Switch to the template module and to the your template record.

#. Add the news extension to the “Include Static” list as shown in the
   screenshot


TODO: duplicate content