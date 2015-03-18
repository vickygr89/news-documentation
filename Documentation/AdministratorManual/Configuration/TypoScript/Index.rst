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

	==================================== ===============
	Property                             Type
	==================================== ===============
	cssFile_                              string
	format_                               string
	overrideFlexformSettingsIfEmpty_      string
	displayDummyIfNoMedia_                boolean
	detailPidDetermination_               string
	defaultDetailPid_                     integer
	orderByAllowed_                       string
	`analytics\.social`_                  array
	relatedFiles_                         array
	demandClass_                          string
	`link\.hrDate`_                       integer
	`link\.typesOpeningInNewWindow`_      string
	`link\.skipControllerAndAction`_      integer
	facebookLocale_                       string
	disqusLocale_                         string
	googlePlusLocale_                     string
	interfaces_                           string
	opengraph_                            array
	`detail\.media`_                      array
	`detail\.errorHandling`_              string
	`detail\.checkPidOfNewsRecord`_       boolean
	`detail\.registerProperties`_         string
	`detail\.showSocialShareButtons`_     boolean
	`detail\.disqusShortname`_            string
	`list\.media`_                        array
	`list\.paginate`_                     array
	`list\.rss`_                          array
	`search\.fields`_                     string
	==================================== ===============


cssFile
"""""""

.. container:: table-row

   Property
         cssFile
   Data type
         string
   Description
         Description of the property
   Default
         Default value (if any). Leave out entirely if not defined.


Path to the css file. This is included with the Layouts.

format
""""""

.. container:: table-row

   Property
         format
   Data type
         string
   Description
         Set a different format for the output. Use e.g. “xml” for RSS feeds.
   Default
         html


overrideFlexformSettingsIfEmpty
"""""""""""""""""""""""""""""""

.. container:: table-row

   Property
         overrideFlexformSettingsIfEmpty
   Data type
         string
   Description
         The default behaviour of extbase is to override settings from
         TypoScript by the one of the flexforms. This is even valid if the setting is
         left empty in the flexforms.

         Therefore you can define those settings which's value should be taken from TypoScript if nothing
         is set in the plugin.
   Default
         cropMaxCharacters,dateField,timeRestriction,orderBy,orderDirection,backPid,listPid,startingpoint,recursive,list.paginate.itemsPerPage,list.paginate.templatePath


displayDummyIfNoMedia
"""""""""""""""""""""

.. container:: table-row

   Property
         displayDummyIfNoMedia
   Data type
         boolean
   Description
         If set and no preview image is defined, a placeholder image is shown.
         The placeholder itself is defined with TypoScript ::

			plugin.tx_news.settings.list.media.dummyImage = typo3conf/ext/news/Resources/Public/Images/dummy-preview-image.png
   Default
         1


detailPidDetermination
""""""""""""""""""""""

.. container:: table-row

   Property
         overrideFlexformSettingsIfEmpty
   Data type
         string
   Description
         This settings defines which page is used for the link to the detail view.
         3 possible options are available which processed in the given order until a page has been found.

         - flexform
         - categories
         - default

         **flexform**

         This type tries to get the detail page from the plugin's setting *PageId for single news display* which
         can also be set by using TypoScript. ::

			# If set via TypoScript, also add detailPid to the setting "overrideFlexformSettingsIfEmpty"
			plugin.tx_news.settings.detailPid = 123

         **categories**

         A detail page can also be defined for every category. Use the field **Single-view page for news from this category** for that

         **default**

         This type tries to get the value from the setting *defaultDetailPid*. ::

			plugin.tx_news.settings.defaultDetailPid = 456

   Default
         flexform, categories, default


defaultDetailPid
""""""""""""""""

*See above*

orderByAllowed
""""""""""""""
.. container:: table-row

   Property
         orderByAllowed
   Data type
         string
   Description
         Due to restrictions of extbase itself it is required to define all fields which are allowed for
         sorting results.

   Default
         sorting,author,uid,title,teaser,author,tstamp,crdate,datetime,categories.title

analytics.social
""""""""""""""""
.. container:: table-row

   Property
         analytics.social
   Data type
         array
   Description
         Use additional code for google analytics tracking of the social functionalities.

   Default
         ::

			analytics.social {
				facebookLike = 1
				facebookShare = 1
				twitter = 1
			}

relatedFiles
""""""""""""
.. container:: table-row

   Property
         relatedFiles
   Data type
         array
   Description
         Configuration to render the related files. This is used in the ViewHelper :code:`n:format.fileDownload`.
   Default
         ::

			relatedFiles {
				fileSizeLabels =
				download {
					labelStdWrap {
						cObject = TEXT
					}
				}
			}

demandClass
"""""""""""
.. container:: table-row

   Property
         demandClass
   Data type
         string
   Description
         Overload the demand object which is used to build the queries.

         .. note::
			This is just important if you want to extend EXT:news. TODO: add link


link.hrDate
"""""""""""

.. container:: table-row

   Property
         link.hrDate
   Data type
         boolean
   Description
         The url to a single news record contains only the uid of the record.
         Sometimes it is nice to have the date in url too (e.g.
         domain.tld/news/2011/8/news-title.html). If enabled, the date is added
         to the url.

         Each parameter (day, month, year) can be separately configured by using
         the full options of the `php function date()
         <http://at2.php.net/manual/en/function.date.php>`_ . This example will
         add the day as a number without leading zeros, the month with leading
         zeros and the year by using 4 digits. ::

            link {
                    hrDate = 1
                    hrDate {
                            day = j
                            month = m
                            year = Y
                    }
            }

         .. danger::
			TODO Add link to realurl
   Default
         0

link.typesOpeningInNewWindow
""""""""""""""""""""""""""""

.. container:: table-row

   Property
         link.typesOpeningInNewWindow
   Data type
         string
   Description
         Comma separated list of news types which open with target="_blank"
         Default is 2 which is the type "Link to external page"
   Default
         2

link.skipControllerAndAction
""""""""""""""""""""""""""""
.. container:: table-row

   Property
         link.skipControllerAndAction
   Data type
         boolean
   Description
         If set, the arguments *controller** and *action* are **not** added to the link.
   Default
         2

facebookLocale
""""""""""""""

.. container:: table-row

   Property
         facebookLocale
   Data type
         string
   Description
          Facebook locale which is used to translate facebook texts. Examples are de\_DE, fr\_FR, ...
   Default
         en\_US



disqusLocale
""""""""""""

.. container:: table-row

   Property
         disqusLocale
   Data type
         string
   Description
          Locale used for disqus
   Default
         en


googlePlusLocale
""""""""""""""""

.. container:: table-row

   Property
         googlePlusLocale
   Data type
         string
   Description
          Locale used for google+
   Default
         en


interfaces
""""""""""

.. container:: table-row

   Property
         interfaces
   Data type
         array
   Description
          Media types like youtube videos are rendered with custom media renderers.
          Those are registered in TypoScript with their class names and processed by order.
   Default
         ::

			 interfaces {
				media {
					video = GeorgRinger\News\MediaRenderer\Audio\Mp3Html5,GeorgRinger\News\MediaRenderer\Audio\Mp3,GeorgRinger\News\MediaRenderer\Video\Quicktime,GeorgRinger\News\MediaRenderer\Video\File,GeorgRinger\News\MediaRenderer\Video\Youtube,GeorgRinger\News\MediaRenderer\Video\Vimeo,GeorgRinger\News\MediaRenderer\Video\Videosites
				}
				falMedia {
					video = GeorgRinger\News\MediaRenderer\Video\Fal
				}
			}

opengraph
"""""""""

.. container:: table-row

   Property
         interfaces
   Data type
         array
   Description
          Additional open graph properties can be defined using TypoScript.
          Those are included in the the template partial :code:`EXT:news/Resources/Private/Partials/Detail/Opengraph.html`.

          The most important properties are filled automatically:

          - *og:title* is filled with the field **Alternative title** or if that is empty with the **Title**.
          - *og:description* is filled with the field **Description** or if that is empty with the **Teaser**.
          - *og:image* is filled with the first preview image.
          - *og:url* is filled with the current url.
   Default
         ::

		opengraph {
			site_name =  {$plugin.tx_news.opengraph.site_name}
			type = article
			admins =
			email =
			phone_number =
			fax_number =
			latitude =
			longitude =
			street-address =
			locality =
			region =
			postal-code =
			country-name =
		}

detail.media
""""""""""""

.. container:: table-row

   Property
         detail.media
   Data type
         array
   Description
        Configuration for media elements in the detail view.

        .. attention::
			If you need different options like using **width** instead of **maxWidth** you need also
			to adopt the template files!

   Default
         ::

			detail.media {
				image {
					maxWidth = 282
					maxHeight =

					# Get lightbox settings from css_styled_content
					lightbox {
						enabled = {$styles.content.imgtext.linkWrap.lightboxEnabled}
						class = {$styles.content.imgtext.linkWrap.lightboxCssClass}
						width = {$styles.content.imgtext.linkWrap.width}
						height = {$styles.content.imgtext.linkWrap.height}
						rel = lightbox[myImageSet]
					}
				}

				video {
					width = 282
					height = 300
				}
			}

detail.errorHandling
""""""""""""""""""""
.. container:: table-row

   Property
         detail.errorHandling
   Data type
         string
   Description
         If no news entry is found, it is possible to use various types of error handling.

         - **redirectToListView**: This will redirect to the list view on the same page.
         - **redirectToPage**: Redirect to any page by using the syntax redirectToPage,<pageid>,<status>. This means e.g. redirectToPage,123,404 to redirect to the page with UID 123 and error code 404.
         - **pageNotFoundHandler**: The default page not found handler will be called.
   Default
         pageNotFoundHandler

detail.checkPidOfNewsRecord
"""""""""""""""""""""""""""
.. container:: table-row

   Property
         detail.checkPidOfNewsRecord
   Data type
         boolean
   Description
         If set, the detail view checks the incoming news record against the defined starting point(s).
         If those don't match, the news record won't be displayed.
   Default
         0


detail.registerProperties
"""""""""""""""""""""""""
.. container:: table-row

   Property
         detail.registerProperties
   Data type
         string
   Description
         Define a list of properties you want to be able to use via the TypoScript option *register*.
         TODO: link


         ::

         	lib.fo = TEXT
         	lib.fo {
         		# title becomes newsTitle, keywords becomes newsKeywords, ...
         		data = newsTitle
         	}

         .. danger::
			TODO Check that!

   Default
          keywords,title

detail.showSocialShareButtons
"""""""""""""""""""""""""""""
.. container:: table-row

   Property
         detail.showSocialShareButtons
   Data type
         boolean
   Description
         If set, the social share functionality is shown. This includes facebook, twitter, google+
   Default
         1

detail.disqusShortname
""""""""""""""""""""""
.. container:: table-row

   Property
         detail.disqusShortname
   Data type
         string
   Description
         If set, the commenting system of disqus (www.disqus.com) is used with the given name.

list.media
""""""""""

.. container:: table-row

   Property
         list.media
   Data type
         array
   Description
        Configuration for media elements in the list view.

        .. attention::
			If you need different options like using **width** instead of **maxWidth** you need also
			to adopt the template files!

   Default
         ::

		list.media {
			image {
				maxWidth = 100
				maxHeight = 100
			}
		}

list.paginate
"""""""""""""

.. container:: table-row

   Property
         list.paginate
   Data type
         array
   Description
         EXT:news uses a custom ViewHelper to render the pagination.

         The following settings are available:

         **itemsPerPage**

         Define how many items are shown on one page.

         **insertAbove**

         Set it to TRUE or FALSE to either show or hide the pagination before
         the actual news items.

         **insertBelow**

         Set it to TRUE or FALSE to either show or hide the pagination after
         the actual news items.

         **maximumNumberOfLinks**

         If set, not all pages of the pagination are shown but only the given amount. Imagine
         1000 news records and 10 items per page. This would result in 100
         links in the frontend.

         **prevNextHeaderTags**

         Add additional header tags <link rel="prev" href"" /> and
         <link rel="next" href"" /> to tell google about the pagination.
         Read more at http://googlewebmastercentral.blogspot.co.at/2011/09/pagination-with-relnext-and-relprev.html

         **templatePath**

         Set a custom template file for the paginate widget.
         The path has to point to the template file, for example :code:`EXT:foobar/Resources/Private/Templates/ViewHelpers/Widget/Paginate/Index.html`

         .. important::
         	`list.paginate.templatePath` needs to be added to the setting `overrideFlexformSettingsIfEmpty`!


   Default
         ::

		list.paginate {
			itemsPerPage = 10
			insertAbove = 1
			insertBelow = 1
			templatePath =
			prevNextHeaderTags = 1
			maximumNumberOfLinks = 3
		}

list.rss
""""""""

.. container:: table-row

   Property
         list.rss
   Data type
         array
   Description
        Additional settings for the RSS view

        TODO: add link

   Default
         ::

		rss {
			channel {
				title = {$plugin.tx_news.rss.channel.title}
				description = {$plugin.tx_news.rss.channel.description}
				language = {$plugin.tx_news.rss.channel.language}
				copyright = {$plugin.tx_news.rss.channel.copyright}
				generator = {$plugin.tx_news.rss.channel.generator}
				link = {$plugin.tx_news.rss.channel.link}
			}
		}


search.fields
"""""""""""""

.. container:: table-row

   Property
         search.fields
   Data type
         string
   Description
        Comma separated list of fields which are used for the search.

        .. hint::
			You can also search in relations, e.g. the category title by using :code:`categories.title`
			TODO: check that!

   Default
        teaser,title,bodytext

