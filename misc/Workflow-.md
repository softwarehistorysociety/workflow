# "Workflow"

*23-08-2022 22:47* 

> Powerful automation made simple.
-   [![](https://workflow.is/static/landing/img/transparent-w.png)](https://workflow.is/)
-   [What’s New](https://workflow.is/whatsnew)
-   [Documentation](https://workflow.is/docs)
-   [Docs](https://workflow.is/docs)
[Get](https://workflow.is/download)

## Shortcuts 2.0

#### September 17, 2018

With iOS 12, Workflow app users are upgraded to the Shortcuts app. [Learn about the latest features.](https://support.apple.com/en-us/HT209087)

## Workflow 1.7.8

#### March 7, 2018 Cheese

-   Added a new **Mask Image** action
-   Added new fields to the **Add Things To-Do** action
-   Dictionary items are now reorderable in the **Dictionary** action
-   The URL scheme now supports opening workflows — [see documentation here](https://help.apple.com/workflow/#/apd621a1ad7a)
-   Improved the PDF to text coercion; extracting text from PDFs now works much better
-   Improved drag and drop handling; you can now drop content onto a workflow in My Workflows without waiting for spring-loading

### New Actions (1)

![](https://workflow.is/static/gallery/icons/Image.png)Mask Image

### Bug Fixes

-   Workflow names are now case-insensitive
-   Fixed a crash when running the **Edit Image** action
-   Fixed Todoist and Slack authentication when using a Google account
-   Fixed an issue where icons from **Search App Store** and **Get My Workflows** were saved as JPEG, not PNG
-   Fixed an issue where the **Encode Media** action may not delete temporary files properly when encoding to MP3
-   Fixed an issue where the Custom X-Success URL parameter of the **Open X-Callback-URL** action did not work
-   Fixed an issue where variables could not be added to arrays in the **Dictionary** action
-   Fixed an issue where booleans could not be added to dictionaries inside dictionaries in the **Dictionary** action
-   Fixed an issue where a duplicate workflow could appear after searching for a workflow
-   Fixed an issue where Workflow could crash when deleting many workflows at once
-   Fixed an issue where double-tapping a variable button cleared the variable
-   Fixed an issue where the **Tweet** and **Post on Facebook** actions did not work from the Today Widget or Apple Watch
-   Fixed an issue where passing the output of **Scan QR Code** to **Open URL** did not work properly
-   Fixed an issue where workflows could not be edited after being opened via 3D Touch
-   Performance improvements to workflow running
-   VoiceOver improvements
-   Other bug fixes and minor additions

## Workflow 1.7.7

#### November 8, 2017 Cherries

-   Optimized for iOS 11 and iPhone X
-   Drag and drop content onto a workflow to run the workflow with that input
-   Added HEIF support to the **Convert Image** action
-   Added HEVC support to the **Encode Media** action
-   Added support for iOS 11 Health data types: Insulin Delivery, V02 Max, Waist Circumference, Resting Heart Rate, Walking Heart Rate Average, and Heart Rate Variability
-   Added the ability to retrieve and save multiple files at a time in the **Get File** and **Save File** actions
-   Added the ability to specify a default “From” address for the compose sheet in the **Send Email** action
-   **Add TaskPaper to OmniFocus** now supports adding TaskPaper under specific folders, projects, and tasks

### Bug Fixes

-   Fixed the **Tweet** and **Post on Facebook** actions on iOS 11
-   Fixed an issue where text items could unexpectedly be converted to image metadata dictionaries
-   Fixed an issue where granting access to Ulysses may not work
-   Fixed an issue where workflows launched from the Complication would not run on watchOS 4
-   Fixed an issue where the **Text** action may randomly scroll to the top while typing
-   Fixed an issue where the **Send Message via WhatsApp** action contact field did not work properly
-   Fixed an issue where the **Convert Image** action may crash in the Today Widget or Action Extension
-   Fixed an issue where the **Show Directions** action may not use the correct travel mode when opening Google Maps
-   Fixed an issue where messaging the attendees of an event may include yourself
-   Fixed an issue where VoiceOver may not focus on an action after it’s added to a workflow
-   Fixed an issue where the **Select Photos** action did not work with VoiceOver when “Select Multiple” was turned on
-   Fixed an issue where a Workflow Input variable may not be editable after being added from the variable bar
-   Fixed a crash when inserting variables into the **List** and **Dictionary** actions
-   Fixed an issue where some files may not be selectable in the Dropbox and Box file pickers
-   Fixed an issue where a ghost workflow may appear while workflows are being reordered
-   Fixed an issue where passing a comma-separated list of email addresses into the **Send Email** action did not work
-   Fixed an issue where the **Get Contents of URL** action did not support passing a JSON body in `DELETE` requests
-   Fixed an issue where saving a file to Dropbox when a file already exists with the same name did not properly append a number to the filename
-   Other bug fixes and minor additions

## Workflow 1.7.6

#### August 19, 2017 String Bean

-   Fixed a crash that affected devices running iOS 9

## Workflow 1.7.5

#### August 14, 2017 Schiacciata

-   The “Otherwise” group in **If** actions can now be deleted
-   Fixed an issue where the **Run Script Over SSH** action may fail
-   Fixed an issue where tapping on a variable may insert it into a text field twice instead of once
-   Fixed an issue where the **Send Email** action would not work with e-mail accounts that require TLS
-   Fixed an issue where the **Show Notification** and **Create Day One Entry** actions may crash or unexpectedly include images of the text passed as input
-   Fixed an issue where signing in to Trello with a Google account may not work
-   Fixed an issue where the **Get File** action could crash when downloading files from the document picker
-   Fixed an issue where the **Save File** action would crash when saving an empty file to Dropbox
-   Fixed an issue where Evernote actions did not allow saving files larger than 100 MB
-   Fixed an issue where variables could not be entered for Peak Expiratory Flow Rate in the **Log Health Sample** action
-   Fixed a crash that occurred when running an action with a variable that has a chosen property but which has an empty value when the workflow is run
-   Fixed an issue where passing text as a variable to an on/off switch in an action was not handled correctly. Passing values like “yes” or “true” should result in the switch being turned on, but instead resulted in the switch being turned off.
-   Other bug fixes and minor additions

### Improvements for iOS Beta

-   Fixed an issue where the **Open In**, **Post to Instagram**, **Create Note**, and **Save with Transmit** actions may not work
-   Fixed an issue where workflows run from the Action Extension may crash
-   Fixed an issue where workflows run from the Today Widget may freeze after switching to the Workflow app
-   Fixed an issue where workflows would become invisible while being rearranged
-   Fixed an issue where items in the **List** action could not be rearranged
-   Fixed an issue where document icons would not appear properly
-   Fixed multiple issues when using Contacts actions

## Workflow 1.7.4

#### May 8, 2017 Cookies & Cream Popcorn

-   Bug fixes and improvements
-   Restored the Google Chrome and Pocket actions
-   Add music to your Up Next queue with the **Add Music to Up Next** and **Clear Up Next** actions

### New Actions (2)

![](https://workflow.is/static/gallery/icons/Music.png)Add Music to Up Next

![](https://workflow.is/static/gallery/icons/Music.png)Clear Up Next

### More Improvements

-   **Get Distance** now supports getting the distance from a specified location
-   The order of items passed from a **Dictionary** action to **Choose from List** is now preserved
-   Fixed getting prices for books in **Search iTunes Store**
-   Fixed making archives with special characters in the filename on iOS 10.3 and later
-   Fixed an issue where workflow glyphs in the Today Widget may be stretched and cut off
-   Fixed an issue where latitude and longitude may be formatted incorrectly in international locales
-   Fixed an issue where `.wflow` files may fail to open on iOS 10.3 and later
-   Fixed an issue where improperly formatted URLs from Pinboard could cause Workflow to crash
-   Fixed an issue where booleans may not update when their value is changed inside dictionary fields
-   Fixed an issue where handing off clipboard content from the Today Widget or Action Extension may throw a “The file Clipboard could not be opened” error
-   Fixed an issue that could cause Workflow to crash on launch
-   Other bug fixes and minor additions

## Workflow 1.7.3

#### March 22, 2017 Custard

This update includes compatibility requirements and other miscellaneous tweaks.

-   Get Travel Time and Get Distance are now powered by Apple Maps
-   Translate Text is now powered by Microsoft Translate
-   Get Street View Image, Google Chrome, Pocket, LINE, Telegram, Uber, and Workflow Gallery submissions are no longer supported
-   Added support for converting PDFs to images
-   Made the Workflow Input variable always available in the variable tray
-   Fixed an issue with deleting actions using VoiceOver
-   Other bug fixes

## Workflow 1.7.2

#### March 17, 2017 Potage

-   Revamped file storage actions, adding Box integration and more complete support for iCloud Drive
-   The new **Get Ulysses Sheet** action lets you get sheets from Ulysses

### New Actions (8)

![](https://workflow.is/static/gallery/icons/Documents.png)Get File

![](https://workflow.is/static/gallery/icons/Documents.png)Get Link to File

![](https://workflow.is/static/gallery/icons/Documents.png)Save File

![](https://workflow.is/static/gallery/icons/Documents.png)Create Folder

![](https://workflow.is/static/gallery/icons/Documents.png)Append to File

![](https://workflow.is/static/gallery/icons/Ulysses.png)Get Ulysses Sheet

![](https://workflow.is/static/gallery/icons/Documents.png)Delete Files

![](https://workflow.is/static/gallery/icons/Ulysses.png)Get Details of Ulysses Sheet

### More Improvements

-   The Dropbox and iCloud Drive actions have merged into a single set of file storage actions
-   **Get File** now supports selecting multiple files at a time from Dropbox and Box
-   **Get File** now supports starting the Dropbox or Box file pickers in a particular directory
-   **Save File** now supports providing a destination file path without needing to use a **Set Name** action first
-   Enabled Emoji and scribble input in Ask When Run on Apple Watch
-   Updated the workflow color palette on Apple Watch
-   Because Instagram no longer supports pre-filling an image caption, **Post to Instagram** now automatically copies your caption to the clipboard
-   In the variable tray, variables with custom names set are now prioritized in suggestions
-   Added SHA-256 and SHA-512 to **Generate Hash**
-   Fixed a crash when appending a variable to itself
-   Fixed an issue where **Get Details of iTunes Product** set to Description may not work for TV shows
-   Fixed an issue where **Resize Image**, **Flip Image**, and **Crop Image** may crash in the Action Extension
-   Fixed an issue where **Combine Images** in grid mode cropped all images into squares
-   Fixed an issue where the Excerpt and Body fields of articles were not filterable in **Filter Articles**
-   Fixed an issue where files could end up with "-2" appended to their names when running workflows repeatedly
-   Fixed Pinyin text input in **Set Variable** fields
-   Fixed issues running workflows from the Complication on Apple Watch
-   Fixed the **Send Email** and **Run Workflow** actions on Apple Watch
-   Fixed an issue where **Dictate Text** would stop listening when the dictation time limit was reached
-   Fixed an issue where reordering action favorites did not work
-   Fixed Today Widget sizing issues
-   Improved accessibility
-   Other bug fixes and minor additions

## Workflow 1.7.1

#### February 28, 2017 Inka Corn

-   Run workflows inside your workflows with the new **Run Workflow** action
-   New and improved workflow glyphs
-   All fields now support Magic Variables and the variable editor, including number and picker parameters

### New Actions (1)

![](https://workflow.is/static/gallery/icons/Workflow.png)Run Workflow

### More Improvements

-   Tap a Magic Variable in any field, including in the **Get Variable** action, to edit its details
-   The **List** action will now pass single variable items straight through, without converting them to text. This means you can use a List action to create a collection with multiple types of content, such as photos and text.
-   Updated the launch appearance for workflows run from the Home Screen
-   Health samples now have a "Duration" property (useful for sleep, for example)
-   Added a "Locations" parameter to **Add 2Do Task**
-   Added a "Description" property to **Get Details of iTunes Products** for books
-   **Adjust Date** now supports adjusting to the start of a year, month, day, hour, or minute
-   Fixed an issue where the cursor may jump to the end of a field when typing in actions
-   Fixed a crash when opening certain workflows with variables and repeat blocks
-   Fixed a crash on iOS 9 and earlier when running workflows via the URL scheme
-   Fixed a crash when changing calendars in **Find Calendar Events** with malformed calendars
-   Fixed a crash when attaching some types of files in **Send Email**
-   Fixed an issue where the workflow may scroll forever when dragging "End Repeat" actions
-   Fixed an issue where some types of files, including ZIP files, did not successfully upload using **Save with Transmit**
-   Fixed an issue where filtering queries such as "Last Played Date is in the last 20 years" did not work
-   Fixed an issue where **Find Health Samples** may incorrectly say that you haven’t granted access to Health data
-   Other bug fixes and minor additions

## Workflow 1.7

#### February 9, 2017 Frozen La Croix

<table><tbody><tr><td><img src="https://workflow.is/static/landing/img/release-notes-wand.png"></td><td><h3>Magic Variables</h3>Workflows are now easier to build, easier to read, and more powerful than ever. With Magic Variables, workflows take far fewer actions to build, because there’s no need to manually create variables or store information for later.<br><a href="https://www.macstories.net/ios/workflow-1-7-introduces-magic-variables-for-easier-more-powerful-visual-automation/">Learn more on MacStories ›</a></td></tr></tbody></table>

### Magic Variables

-   **Grab the output of any action.** Eliminate Set Variable actions from your workflows. Just tap the Magic Variable button to select and use the output of any previous action in your workflow.
-   **Customize a variable to get specific details.** Eliminate Get Details actions from your workflows. You can now tap on a variable to dive deeper and choose which details to extract.
-   The new **Current Date** variable automatically provides the current date and time.
-   The new **Workflow Input** variable grabs the input passed to an Action Extension workflow.
-   Date variables can now be formatted inline, without the need for a **Format Date** action.
-   You can now retrieve values from dictionary variables inline, without the need for a **Get Dictionary Value** action.
-   There’s now a variable tray directly above the keyboard for easy access, including suggestions for variables you may want to use.

### More Improvements

-   Universal Links is now supported for workflows shared on the web
-   **Find Health Samples** now supports reproductive health, mindfulness, and sleep samples
-   The URL scheme now supports opening to a Gallery search (`workflow://gallery/search?query=soup`)
-   **Request Uber** now supports UberPOOL and showing price estimates
-   **Get Contents of URL** now supports DELETE requests
-   **Add to Bear Note** now supports returning to Workflow after finishing
-   **Adjust Date** now supports decimal number adjustments
-   The Select All Initially option in **Choose from List** now works for images
-   Improved the accuracy of workflow double-tap gesture
-   Improved the speed of opening the Action Extension

### Bug Fixes

-   Fixed handling of special characters in **Extract Archive**
-   Fixed an issue where **Log Workout** was missing units
-   Fixed an issue where **Log Health Samples** didn’t pass any output
-   Fixed an issue where some e-mail accounts may not have been able to be added in the **Send Email** action
-   Fixed an issue where Workflow would ask repeatedly to open another app after answering "Cancel" the first time
-   Fixed an issue where **Find Health Samples** failed with an error when run from the Today Widget on a locked device
-   Fixed an issue where Find actions with filters like "In the last 7 days" didn’t include today
-   Fixed an issue where **Split Text** with newlines sometimes generated empty items
-   Fixed an issue where Workflow incorrectly believed that Evernote was not installed
-   Fixed a crash when passing videos from the photos library to **Save File**
-   Improved the style of the Today Widget on iOS 9
-   Other bug fixes and minor additions

## Workflow 1.6.1

#### December 8, 2016 Chocolate Croissant

-   Added a "Recently Added" collection for exploring the newest workflows added to the Gallery
-   Added seven new actions, including support for Bear and Opener
-   Added support for Reproductive Health, Mindfulness, and Sleep to the **Log Health Sample** action

### New Actions (7)

![](https://workflow.is/static/landing/img/icons/net.shinyfrog.bear-IOS@2x.png)Add to Bear Note

![](https://workflow.is/static/landing/img/icons/net.shinyfrog.bear-IOS@2x.png)Open Bear Note

![](https://workflow.is/static/landing/img/icons/net.shinyfrog.bear-IOS@2x.png)Create Bear Note

![](https://workflow.is/static/landing/img/icons/net.shinyfrog.bear-IOS@2x.png)Search in Bear

![](https://workflow.is/static/landing/img/icons/net.shinyfrog.bear-IOS@2x.png)Create Bear Note from URL

![](https://workflow.is/static/landing/img/icons/com.tijo.opener.Opener@2x.png)Open URL in Opener

![](https://workflow.is/static/landing/img/icons/net.shinyfrog.bear-IOS@2x.png)Get Contents of Bear Note

### More Improvements

-   Added a "Customize Workflow" button in workflow settings to show Import Questions
-   Local data is now automatically stripped when sharing workflows with Import Questions
-   Improved Select Multiple in **Choose from List**: rich items are now supported, and there’s now an option to start with every item selected
-   Fixed an issue where **Trigger IFTTT Applet** may fail when run from the Today Widget after not launching the Workflow app for some time
-   Fixed an issue where iCloud photos didn’t show up in **Select Photos** with Select Multiple turned on
-   Fixed issues with workflow dragging in My Workflows
-   Fixed an issue where non-English keyboards didn’t work in **List** or **Dictionary** actions
-   Fixed an issue where workflows showed up blank after answering Import Questions from the web
-   Fixed issues preventing "Find reminders where due date is" queries from working
-   Fixed an issue where **Get Contents of URL** did not encode space or ’+’ characters properly as part of a form
-   Other bug fixes and minor additions

## Workflow 1.6

#### November 17, 2016 Chiclets

### More Improvements

-   Design refinements across the app, adding a bit more shine and shimmer
-   The **Choose from List** action now shows rich information about each item in a list. For example, a list of map items from **Search Local Businesses** now includes each location’s distance from you, a list of songs show album artwork, and more.
-   In a workflow’s settings, you can now set up **Import Questions**, which make it easy for others to customize workflows you share. Import Questions are asked when you get a workflow, and the answers are automatically filled into the workflow.
-   The **Choose from Menu** action now supports variables
-   Added PATCH support to **Get Contents of URL**
-   You can now pass a **Dictionary** item to **Choose from List** to show its keys and values as a list
-   The first-time user experience has been rebuilt from scratch, accessible in Settings **›** Open Intro

### Bug Fixes

-   Fixed a crash on launch related to older workflows that post to WordPress
-   Fixed a crash on iOS 8.1 and earlier
-   Fixed an issue where YouTube URLs would not open
-   Fixed an issue where the wrong value may be removed when deleting values in a dictionary
-   Fixed an issue where an Action Extension workflow that opens another app may hang when run twice in a row
-   Other bug fixes and minor additions

## Workflow 1.5.3

#### October 18, 2016 Drinkable Yogurt

-   Workflow can now use any API! The **Get Contents of URL** action now supports custom headers and POST and PUT requests.
-   Added two actions to create and expand many types of archive files (zip, .tar.gz, .tar.bz2, cpio, iso, and more!)
-   Added two actions for working with APIs: Dictionary (to create a dictionary) and Set Dictionary Value (to update a dictionary).
-   Several other enhancements — much more to come very soon!

### New Actions (4)

![](https://workflow.is/static/gallery/icons/Documents.png)Make Archive

![](https://workflow.is/static/gallery/icons/Documents.png)Extract Archive

![](https://workflow.is/static/gallery/icons/Scripting.png)Dictionary

![](https://workflow.is/static/gallery/icons/Scripting.png)Set Dictionary Value

### More Improvements

-   **Get Dictionary Value** (formerly **Get Value for Key**) now supports getting a list of all keys or values in a dictionary
-   **Split Text** now supports getting each character of a piece of text
-   The `⌘-return` keyboard shortcut now works to finish dictation in **Dictate Text**
-   **Set Name** now has an option to rename a file with no file extension
-   Fixed an issue where some workflows would not complete in the Today Widget
-   Fixed an issue where some alert buttons didn’t display properly in the Today Widget
-   Fixed issues with Today Widget sizing when Dynamic Type is enabled
-   Fixed an issue where tags were used in place of categories in **Post to WordPress**
-   Fixed an issue where it was not possible to filter contacts based on URL or street address
-   Fixed an issue where **Quick Look** could get stuck loading on iOS 10
-   Fixed an issue where the Evernote actions’ notebook fields did not work with variables
-   Fixed an issue where **Set Name** did not work properly on videos
-   Fixed an issue where running workflows from Siri’s "remind me about this" feature didn’t work
-   Fixed a crash when adding an email account
-   Improved Today Widget accessibility
-   Improved Today Widget colors
-   Other bug fixes and minor additions

## Workflow 1.5.2

#### September 13, 2016 Grape

-   Redesigned Today Widget for iOS 10
-   Speech recognition with the new Dictate Text action
-   Several other improvements

### New Actions (4)

![](https://workflow.is/static/gallery/icons/Dictation.png)Dictate Text

![](https://workflow.is/static/landing/img/icons/squibner.AmazonLinker@2x.png)Convert URL with Associate

![](https://workflow.is/static/landing/img/icons/squibner.AmazonLinker@2x.png)Search in Associate

![](https://workflow.is/static/landing/img/icons/com.evernote.iPhone.Evernote@2x.png)Delete Notes

### More Improvements

-   **Show Notification** now works when the app is frontmost and supports a title and attachments (iOS 10)
-   **Set Clipboard** now has Local Only and Expire Date options (iOS 10)
-   **Encode Media** now supports configuring the bitrate and stereo/mono setting when encoding MP3s
-   **Add OmniFocus Item** now supports autosave
-   **Show Web Page** now supports swipe-to-dismiss
-   Added an Add to Launcher button for quickly adding workflows to Launcher
-   Added a keyboard shortcut (`⌘-return`) for completing Ask When Run
-   Improved Evernote actions, including:
    -   **Get Note Link** now supports getting in-app links
    -   **Append to Note** now supports prepending to notes and creating notes if one doesn’t exist
-   With great courage, we’ve decided to remove 3D Touch shortcut workflows in favor of the shinier Today Widget. On iOS 10, the widget can be accessed by pressing firmly on Workflow app icon. Give it a try if you haven’t!

### Bug Fixes

-   x^y operations in **Calculate** now support decimal numbers, not just whole numbers
-   Fixed an issue where text may not enter properly into **Trigger IFTTT Recipe** name field
-   Fixed an issue where using Ask When Run for the repeat count in a **Repeat** action did not work properly
-   Fixed an issue where the cursor wasn’t placed in the correct location when using Ask When Run in text fields
-   Fixed an issue where you couldn’t enter negative numbers on iPhone in **Ask for Input**
-   Fixed an issue where a workflow may be deleted if you open it while tapping the "Create Workflow" button
-   Fixed an issue where **Find Health Samples** could fail from the Today Widget
-   Fixed an issue where **Play Sound** did not work in extensions
-   Fixed an issue where **Get Contents of Web Page** worked inconsistently with certain web pages, including Instagram
-   Fixed an issue where **Resize Image** may draw images with fractional pixels, resulting in poorly rendered images
-   Fixed an issue where public transit locations from **Search Local Businesses** may not open properly in Maps
-   Fixed an issue running **Search Giphy** from the Today Widget
-   Fixed an issue making PDFs of QR codes
-   Fixed an issue getting the external IP address with **Get IP Address**
-   Fixed issues when using ampersand characters in the **Post to WordPress** tag field
-   Fixed a crash when deleting e-mail accounts
-   Fixed crashes on Apple Watch when importing or hiding and showing workflows
-   Improved Apple Watch workflow syncing
-   Other bug fixes and minor additions

## Workflow 1.5.1

#### June 9, 2016 Pizza

-   Introducing [IFTTT](https://ifttt.com/) integration, allowing you to trigger IFTTT recipes in your workflows. With IFTTT’s hundreds of actions now accessible from Workflow, the possibilities are endless!
-   Four other new actions, including integrations with Blink and LINE
-   Other bug fixes and improvements

### New Actions (5)

![](https://workflow.is/static/landing/img/icons/com.ifttt.ifttt@2x.png)Trigger IFTTT Recipe

![](https://workflow.is/static/landing/img/icons/jp.naver.line@2x.png)Post to LINE

![](https://workflow.is/static/landing/img/icons/com.squibner.Blink@2x.png)Search in Blink

![](https://workflow.is/static/landing/img/icons/com.squibner.Blink@2x.png)Convert URL with Blink

![](https://workflow.is/static/gallery/icons/Downloads.png)Get Headers of URL

### More Improvements

-   **Make PDF** now supports Pages, Keynote, and Numbers documents
-   Added the ability to log Systolic and Diastolic blood pressure together in **Log Health Sample**
-   **Get Maps Link** now generates better links, including geographic coordinates and/or the street address
-   Improved international street address handling
-   Improved the presentation of dialogs in Ask When Run and **Ask for Input**
-   Added a Country option when searching by product ID with **Search App Store** and **Search iTunes Store**

### Bug Fixes

-   Fixed an issue where certain filters were ignored (such as Event Is All Day, or Reminder Is Completed)
-   Fixed variable bugs which caused errors when running filtering actions
-   Fixed issues when entering Japanese and Chinese characters in text fields
-   Fixed an issue where **Make PDF** may have included extra margins on documents
-   Fixed an issue where **Exit Workflow** did not dismiss the workflow when running in the Action Extension
-   Fixed an issue where using **Set Name** with a file extension did not work for Dropbox items
-   Fixed an issue where the Notebook field of **Get Evernote Notes** was ignored
-   Fixed an issue where Emoji may not be counted correctly by the **Count** action when counting characters
-   Fixed an issue where text in **Quick Look** would not wrap to new lines and would appear very small
-   Fixed an issue preventing the home screen icon picker from working on iPad
-   Fixed a crash on Apple Watch when logging health information using Ask When Run
-   Fixed a crash that affected certain actions, including **Post to Facebook**
-   Fixed a "Could not convert string to date" error when using the App Store actions
-   Other bug fixes and minor additions

## Workflow 1.5

#### May 24, 2016 Wintermelon

-   Twenty two new actions, including integrations with Trello, Ulysses, Apple Music, and the App Store
-   A completely rewritten workflow composer with greatly improved performance
-   A search bar at the top of My Workflows and in the Action Extension

### New Actions (22)

![](https://workflow.is/static/gallery/icons/Music.png)Add to Playlist

![](https://workflow.is/static/gallery/icons/iTunes.png)Search iTunes Store

![](https://workflow.is/static/landing/img/icons/com.fogcreek.trello@2x.png)Add Trello Card

![](https://workflow.is/static/landing/img/icons/com.fogcreek.trello@2x.png)Get Details of Trello Item

![](https://workflow.is/static/gallery/icons/Ulysses.png)New Ulysses Sheet

![](https://workflow.is/static/gallery/icons/Web.png)Show Web Page

![](https://workflow.is/static/gallery/icons/Music.png)Create Playlist

![](https://workflow.is/static/gallery/icons/iTunes.png)Show in iTunes Store

![](https://workflow.is/static/landing/img/icons/com.fogcreek.trello@2x.png)Create Trello Board

![](https://workflow.is/static/gallery/icons/Ulysses.png)Add to Ulysses Sheet

![](https://workflow.is/static/gallery/icons/Ulysses.png)Open Ulysses

![](https://workflow.is/static/gallery/icons/Text.png)Get Group from Matched Text

![](https://workflow.is/static/gallery/icons/AppStore.png)Search App Store

![](https://workflow.is/static/gallery/icons/iTunes.png)Get Details of iTunes Artist

![](https://workflow.is/static/landing/img/icons/com.fogcreek.trello@2x.png)Create Trello List

![](https://workflow.is/static/gallery/icons/Ulysses.png)Attach to Ulysses Sheet

![](https://workflow.is/static/landing/img/icons/com.omnigroup.OmniFocus2.iPhone@2x.png)Add TaskPaper to OmniFocus

![](https://workflow.is/static/gallery/icons/AppStore.png)Get Details of App Store App

![](https://workflow.is/static/gallery/icons/iTunes.png)Get Details of iTunes Product

![](https://workflow.is/static/landing/img/icons/com.fogcreek.trello@2x.png)Get Trello Items

![](https://workflow.is/static/gallery/icons/Ulysses.png)New Ulysses Group

![](https://workflow.is/static/gallery/icons/Calculator.png)Format File Size

### Workflow Composer Improvements

-   Added six keyboard shortcuts for editing workflows:
    -   `⌘R` to run the workflow,
    -   `⌘.` to stop the workflow,
    -   `⌘F` to search for an action,
    -   `⌘Z` to undo,
    -   `⌘⇧Z` to redo,
    -   and `⌘W` to close the workflow.
-   Faster workflow loading
-   Improved action dragging performance
-   On iPhone 6s and iPhone 6s Plus, there is now a Redo button next to the Undo button
-   On iPad, you can now drag actions from your workflow back to the actions pane to remove them
-   Long **If**, **Repeat**, and **Choose from Menu** actions can now be dragged

### Action Improvements

-   Filtering actions and Custom Fields in **Post to WordPress** now support Ask When Run
-   Added Album Artist to **Get Details of Music**
-   Added Reminder Location to **Get Details of Reminders**
-   Added Frame Rate to **Find Photos** and **Get Details of Image**
-   Updated **Add OmniFocus Item** and added support for attaching files to new items
-   **Save to Photo Album** now supports saving existing photos into new albums without creating a duplicate
-   **Encode Media** now supports specifying metadata to be added to the media file
-   **Match Text** now supports capture groups (with the new **Get Group from Matched Text** action)
-   **Get Item from List** now supports getting a range of items
-   **Adjust Date** has been redesigned to avoid accidental edits
-   The image editor in **Edit Image** has been updated
-   The "is anything" and "is not anything" operators in filtering actions can now be used to test the emptiness of a property
-   Improved URL handoff and callback behavior, particularly when opening URLs from the Today Widget and Action Extension

### Bug Fixes

-   Fixed issues with international addresses in actions with location parameters (including **Add New Event**, **Add New Reminder**, **Get Halfway Point**, **Get Travel Time**, and **Request Uber**)
-   Fixed an issue where **Edit Image** would crash when run from the Action Extension (Note: **Edit Image** produces lower resolution images when run in the Action Extension.)
-   Fixed issues with logging into Uber and CloudApp
-   Fixed an issue where certain actions wouldn’t run on watchOS, complaining that they required "watchOS 9.3 or later"
-   Fixed an issue where **Text** actions may lose their contents in a workflow
-   Fixed an issue where **Get Clipboard** would hang if the clipboard was empty
-   Fixed an issue with getting and filtering Dropbox file modification dates
-   Fixed an issue where workflows that save images from a web page would fail if the web page included SVG images
-   Fixed an issue where **Get Contents of Web Page** downloaded HTML instead of a web archive, causing images and other resources to be dropped
-   Fixed an issue when expanding/getting certain Pocket and `t.co` URLs
-   Fixed an issue where sentences ending in question marks were not capitalized in **Change Case**
-   Fixed an issue where screenshots edited in the Photos app may appear unedited in workflows
-   Fixed an issue where copying a portion of a text field’s contents would instead copy the field’s entire contents
-   Fixed an issue where **Repeat** blocks would be run even if the Repeat Count was set to 0
-   Fixed an issue where some `.plist` files may not be recognized as dictionary items
-   Fixed an issue where the **Print** action did not work at times
-   Fixed an issue where **Set Name** may have no effect on article or rich text items
-   Fixed issues using `x-callback-url` in iPad split-screen multitasking
-   Other bug fixes, stability improvements, and minor additions

## Workflow 1.4.5

#### March 17, 2016 Ham Steak

-   Added integration with [DeskConnect](https://deskconnect.com/) for easily sending links, documents, pictures, and everything else between your devices
-   Improved the speed and reliability of Workflow for Apple Watch, including the Workflow Complication
-   Other bug fixes and improvements

### New Actions (1)

![](https://workflow.is/static/gallery/icons/DeskConnect.png)Send via DeskConnect

### Bug Fixes

-   Fixed an issue where workflows may fail to sync to Apple Watch if the Workflow app is not in the foreground on the iPhone
-   Fixed an issue where Workflow for Apple Watch may crash or freeze while updating the Complication
-   Fixed an issue with number conversions that prevented some workflows from working, including Health-related workflows
-   Fixed an issue where the keyboard appeared over top of the Action Extension when running workflows from the "Share" button in the text editing menus of other apps
-   Fixed an issue where the keyboard appeared over top of certain fields when setting up email accounts
-   Fixed an issue where Evernote items failed to preview
-   Fixed an issue where Workflow may crash or hang when running a workflow that switches between apps over 100 times
-   Fixed an issue where **Add to Reading List** would use the URL as the name of the reading list item instead of the page title
-   Fixed issues encoding audio to MP3 using **Encode Media**
-   Fixed a crash when accessing CloudApp settings
-   Fixed a crash when getting images from the clipboard in the widget
-   Fixed a crash when getting photos from the photo library in the widget
-   Fixed multiple issues when getting images from rich text, including animated GIFs being converted to static images, image quality reduction, and crashes due to constrained memory
-   **Get IP Address** no longer displays errors when there is no active Internet connection
-   Improved accessibility of the Today Widget workflow manager

## Workflow 1.4.4

#### March 7, 2016 Bagels

-   Six new actions, including the ability to overlay images, add frames to GIFs, and unzip files
-   A whole host of bug fixes and improvements

### New Actions (6)

![](https://workflow.is/static/gallery/icons/Image.png)Overlay Image

![](https://workflow.is/static/gallery/icons/RichText.png)Make Markdown from Rich Text

![](https://workflow.is/static/gallery/icons/GIF.png)Add Frame to GIF

![](https://workflow.is/static/gallery/icons/Documents.png)Unzip

![](https://workflow.is/static/gallery/icons/Scripting.png)Get Device Details

![](https://workflow.is/static/gallery/icons/RichText.png)Get Details of Safari Web Page

### More Improvements

-   **Post to Tumblr** now supports posting animated GIFs
-   **Save with Transmit** now supports choosing a favorite to automatically connect to
-   **Make Zip** can now zip bundles (like .pages files)
-   Added an "Allow Comments" option to **Post to WordPress**
-   Improved usability of entering contact information into a workflow
-   **Get Name** now automatically gets the title of a web page when a URL is passed in
-   Added a "Project Name" option to **Add 2Do Task**
-   Made **Get Details of File** (set to File Size) work for URLs without actually having to download the remote file
-   **Open X-Callback-URL** can now be used with apps that support URL callbacks but aren’t `x-callback-url` compliant
-   **Get Travel Time** now uses Google Maps to get driving ETAs (with current traffic taken into consideration)
-   Improved the performance and reliability of Workflow for Apple Watch
-   Overall performance improvements, especially on older devices

### Bug Fixes

-   Fixed an issue where the list of workflows in the Today Widget could be cut short after rotating the device
-   Fixed an issue where Workflow may crash on first launch, especially on iPad Pro
-   Fixed an issue where a workflow may freeze if a `workflow://run-workflow` URL is opened from another workflow
-   Fixed an issue where photos in bursts were not retrieved in order
-   Fixed issues where Workflow could freeze when you open it until you restart your device
-   Fixed an issue displaying unicode characters after using the **Make Rich Text** actions
-   Fixed an issue in Ask When Run where the cursor wasn’t placed where the Ask When Run token was inserted
-   Fixed an issue parsing certain types of RSS feeds
-   Fixed an issue preventing **Get RSS Feeds from Page** from working
-   Fixed an issue where "**Find Calendar Events** where Start Date is exactly x" queries did not work
-   Fixed an issue where **Encode Media** could fail when using files from other apps via the Action Extension
-   Fixed an issue where **Make HTML from Rich Text** modified HTML documents with "Make Full Document" on
-   Fixed an issue where **Open In** could fail
-   Fixed an issue where duplicated workflows appeared in the wrong place when Workflow Sync is on
-   Fixed an issue where iCloud photo albums appeared in the list of albums in **Save to Photo Album** even though using them threw an error
-   Fixed an issue where items added to Instapaper had the URL set as the name instead of the actual title of the page
-   Fixed an issue where phone numbers and contacts used their labels as names (so if you passed two phone numbers into **Choose from List**, the options would appear as "Mobile" and "Mobile" rather than as "Conrad Kramer" and "Nick Frey")
-   Fixed an issue where re-ordering workflows could move the wrong workflow when dragging a long distance
-   Fixed an issue where running a workflow from the share sheet on a location in Maps didn’t work properly
-   Fixed an issue where **Make PDF** wouldn’t work in the Action Extension with documents passed in from other apps
-   Fixed an issue where Workflow’s syncing status may get "stuck"
-   Fixed an issue where Workflow sometimes mistakenly used the unedited versions of photos previously edited in the Photos app
-   Fixed an issue with the tag/category picker in **Post to WordPress** causing duplicate entries
-   Fixed an issue where videos passed to the Action Extension weren’t properly recognized as Photo Media
-   Fixed an issue where the wrong photo(s) could be chosen when running the Action Extension with edited photos selected from the Photos app
-   Fixed importing workflows from iCloud Drive
-   Fixed issues using **Expand URL** with certain URLs
-   Fixed issues using **Get Distance** and **Get Travel Time** from Apple Watch
-   Fixed issues with **Make GIF** causing some frames to be dropped
-   Fixed multiple issues posting photos to Tumblr
-   Fixed Todoist due dates always occurring at 12 PM on a day instead of being assigned to a whole day
-   Fixed various **Post to WordPress** issues
-   Fixed various other Contacts-related issues and crashes
-   Fixed a crash when filtering contacts that have invalid URLs
-   Fixed a crash when using **Exit Workflow**
-   Other bug fixes and minor additions

## Workflow 1.4.3

#### December 19, 2015 Latke

-   Take advantage of Bursts and Live Photos in your workflows
-   Make GIF now supports any number of images. That’s right, you can now make GIFs like never before... out of 100 photos, or even out of a long video.

### New Actions (3)

![](https://workflow.is/static/gallery/icons/Bursts.png)Get Latest Bursts

![](https://workflow.is/static/gallery/icons/LivePhotos.png)Get Latest Live Photos

![](https://workflow.is/static/gallery/icons/GIF.png)Get Frames from Image

### More Improvements

-   Added support for selecting multiple contacts with the **Select Contact** action
-   Added a relative date formatting mode to **Format Date**
-   Added a new "Group" property to **Find Contacts**
-   Added a new "Metadata Dictionary" property to **Get Details of Image**
-   Added "Photo Type", "Media Type", "Is Hidden", and "Is Favorite" properties to **Find Photos**
-   Added support for opening `data:` URLs with **Open URLs** and **Open URLs in Chrome**
-   Nearly everything photos-related has been rewritten, improving the reliability of **Save to Photo Album** and iCloud Photos

### Bug Fixes

-   Fixed a crash when opening Workflow from other apps on iOS 8 (including from `workflow://` URLs)
-   Fixed an issue where all files in the iCloud Drive app opened in Workflow by default
-   **Get File** now works with file packages (like Pages, Keynote, and Numbers files)
-   Fixed a crash when logging Health information from Workflow for Apple Watch
-   Fixed a crash when using **Get IP Address** while not connected to the Internet
-   Fixed a crash when passing an empty line to **Calculate Statistics**
-   Fixed an issue where buttons to dismiss alerts could not appear in Today Widget workflows
-   Fixed an issue where taking photos with the front-facing camera could unexpectedly flash the screen on iPhone 6s
-   Fixed an issue where the Action Extension may not dismiss properly or may freeze
-   Fixed an issue where videos over five minutes long appeared as images in Quick Look
-   Fixed an issue where "=" characters in `workflow://run-workflow?input=` URLs were not handled properly
-   Fixed an issue where **Adjust Date** used incorrect units when a time interval was passed as input (like from **Get Travel Time**)
-   Fixed an issue where passing the input from Safari into **Get Text from Input** with no text selected on the page resulted in no text rather than the page’s URL
-   Fixed an issue where **Expand URL** would output URLs named as the URL before it was expanded
-   Fixed an issue where **Send Message** didn’t work to multiple recipients from the Today Widget when no text was specified
-   Fixed an issue where using the Action Extension from a photo in the Photos app that has been edited may result in the wrong photo being passed into the workflow
-   Fixed issues loading certain non-HTTPS resources with **Get Contents of Web Page**
-   Fixed issues when filtering by "is not" with multiple items (for example, **Find Photos** with "Album is not Family" now correctly finds photos not inside the album Family)
-   Fixed multiple issues with **Upload to Imgur**, including problems authenticating and posting anonymously
-   Other bug fixes and minor additions

## Workflow 1.4.2

#### November 24, 2015 Bottled Water

-   Optimized for iPad Pro
-   Two new actions and a bunch of improvements to existing actions
-   **Save File** and **Get File** can now retrieve and save files locally to Workflow’s iCloud folder
-   **Send Message** and **Send Email** now open Messages and Mail directly when run from the Today Widget, when possible

### New Actions (2)

![](https://workflow.is/static/gallery/icons/Notes.png)Create Note

![](https://workflow.is/static/landing/img/icons/org.wordpress@2x.png)Post to WordPress

### Updated Actions

![](https://workflow.is/static/landing/img/icons/com.tinyspeck.chatlyio@2x.png)Post to Slack

Now supports being logged into multiple Slack accounts at a time.

![](https://workflow.is/static/gallery/icons/iBooks.png)Open in iBooks

Now supports opening ePub files.

![](https://workflow.is/static/gallery/icons/CloudApp.png)Upload to CloudApp

Now supports uploading multiple files at once.

![](https://workflow.is/static/gallery/icons/Documents.png)Get & Save File

Now support retrieving and saving files locally to Workflow’s iCloud Drive folder.

![](https://workflow.is/static/gallery/icons/Sound.png)Play Sound

Now plays audio files passed in as input.

![](https://workflow.is/static/gallery/icons/Messages.png)Send Message

Now opens the Messages app directly when run from the Today Widget, when possible.

![](https://workflow.is/static/gallery/icons/PDF.png)Make PDF

Now supports making PDFs of a single page or a range of pages.

![](https://workflow.is/static/gallery/icons/Mail.png)Send Email

Now opens the Mail app directly when run from the Today Widget, when possible.

![](https://workflow.is/static/gallery/icons/Downloads.png)Get Contents of URL

Now supports getting directory listings from FTP servers.

### More Improvements

-   Added a setting to turn off haptic feedback when running workflows on Apple Watch
-   Added a "Done" button to dismiss the tutorial if you’ve completed the tutorial before (stored in iCloud)
-   Replaced the "Inappropriate file type" error with a much more informative one, including why the type conversion failed
-   **Get Dictionary from Input** and **Get Value for Key** now support `plist` dictionaries
-   **Get *x* from Input** actions will no longer throw errors if the content cannot be converted (for example, running **Get Phone Numbers from Input** on text with no phone numbers will no longer stop the workflow with an error)
-   Improved performance of scrolling in My Workflows and Gallery
-   Improved speed of various file operations
-   Improved smoothness of Ask When Run

### Bug Fixes

-   Fixed App Transport Security errors in **Expand URL** and **Get Contents of URL**
-   Fixed an issue where **Adjust Date** with Ask When Run resulted in a plain alert in the Today Widget
-   Fixed an issue where **Choose from List** on a list of URLs did not show the URLs (and instead just showed "URL")
-   Fixed an issue where **Repeat with Each** nested inside other repeat actions may fail to run properly if empty input is passed in
-   Fixed an issue where **Tweet** and **Post on Facebook** didn’t work from the Today Widget
-   Fixed an issue where **Remove Calendar Events** and **Remove Reminders** didn’t work in a workflow handed off to the main app
-   Fixed an issue where the **Open In** action may fail if the action below it is not connected to it
-   Fixed an issue where action descriptions could not be dismissed while in landscape on iPhone 6 Plus
-   Fixed issues with Twitter, Dropbox, and Evernote authentication
-   Fixed issues with **Log Health Sample** and percentage units
-   Fixed issues with **Send Message** and **Send Email** where multiple phone numbers or email addresses could be added for the same recipient
-   Fixed issues with **Choose from List** in the Today Widget
-   Fixed issues with **Record Audio**, including audio being recorded at 2x speed on iPhone 6s
-   Fixed a crash when using calendar actions with a calendar that has a NULL name
-   Fixed a crash when using **Change Case** to convert text that’s only one character long to Title Case
-   Fixed a crash when using **Open X-Callback-URL** to open a `workflow://` URL
-   Fixed crashes when reading non-UTF-8 text files
-   Fixed crashes and slowness when picking many photos in **Select Photos**
-   Other bug fixes and minor additions

## Workflow 1.4.1

#### September 28, 2015 Chocolate Chia Seed Pudding

### Bug Fixes

-   Fixed an issue where **Open App**, **Call**, Add to Launch Center, and other URL scheme-based features could fail on iOS 9
-   Fixed an issue where workflows may not to sync from iPhone to the Apple Watch app
-   Fixed an issue where Workflow would crash when running a `workflow://run-workflow` URL if the source parameter was not set
-   Fixed a crash when renaming workflows on iPhone 6s
-   Fixed an issue where the Action Extension may fail to appear
-   Fixed the sort, order, and limit options in **Find Health Samples**
-   Fixed a crash when **Get Contents of URL** was run on Apple Watch
-   Fixed an issue where **Get Current Location** could hang
-   Fixed an issue where various location- or map-based operations may fail with a Google error
-   Fixed an issue where **Resize Image** mishandled image orientation and produced stretched images
-   Fixed **Open in GoodReader** on iOS 9
-   Fixed an issue where PDFs could not be made from Microsoft Office documents
-   Fixed an issue with **Wait to Return** in the Today Widget
-   Fixed an issue where **Add Todoist Item** would not correctly set up Push Notification reminders
-   Fixed an issue where **Make HTML from Rich Text** would fail on non-UTF-8 formatted pages
-   Fixed occasional App Transport Security and Invalid Type errors on URL-based actions such as **Get Contents of URL**, **Get Contents of Webpage**, and **Expand URL**
-   Fixed an issue where the Action Extension would crash from vCard input (causing issues using the Action Extension from Maps)
-   Fixed several other crashes

### New Features

-   Added video quality option to **Take Video**
-   Added "does not contain" operator in filtering actions
-   **Choose from Menu** now cancels the workflow when the cancel button is pressed (like **Choose from List** always has)
-   **Select Music** now includes Apple Music and iCloud Music Library content

We also fixed an issue where email addresses weren’t sent to us when requesting an app to be added to the **Open App** action. If you submitted a request for an app to be added to **Open App**, it may be worth requesting it again in this version so that we can tell you when it’s there!

## Workflow 1.4

#### September 24, 2015 Hoagie

-   Search for and run workflows from Spotlight on your home screen in iOS 9.
-   Use Workflow alongside other apps on iPad with iOS 9’s new split-screen multitasking.
-   3D Touch adds a new dimension to your workflows. On iPhone 6s, press firmly on a workflow to take a peek, or on the Workflow app icon for quick shortcuts to your workflows.
-   Use Siri in iOS 9 to remind yourself to run workflows later ("Siri, remind me to run this workflow in 30 minutes").
-   Workflow now runs natively on Apple Watch in watchOS 2.
-   Run workflows straight from your watch face with the new Workflow Complication.
-   Seven more actions are now supported directly from your watch.

### Optimized for Apple Watch (7)

![](https://workflow.is/static/gallery/icons/Phone.png)Call

![](https://workflow.is/static/gallery/icons/Maps.png)Show Directions

![](https://workflow.is/static/gallery/icons/FaceTime.png)FaceTime

![](https://workflow.is/static/gallery/icons/Maps.png)Show in Maps

![](https://workflow.is/static/gallery/icons/Microphone.png)Record Audio

![](https://workflow.is/static/gallery/icons/Notification.png)Vibrate Device

![](https://workflow.is/static/gallery/icons/Messages.png)Send Message

### More Improvements

-   Revamped the **Open App** and **Open In** actions with the ability to request support for new apps be added
-   Updated the Health actions to support the data types added in iOS 9, including water consumption
-   Health actions now can be run directly from the Today Widget, Action Extension, and Apple Watch app
-   Fixed issues opening URLs on iOS 9
-   Fixed an issue where **List** actions would not properly save their items
-   Merged Alert Time with Due Date in **Add New Reminder**
-   Text items can now be converted into other types of files by using the **Set Name** action with a file extension
-   Fixed an issue where **Find Health Samples** would error when input was passed into it
-   Fixed an issue where **Create Day One Entry** would error when non-image input was passed into it
-   Fixed an issue where Pinboard URLs were missing names
-   Fixed issues with alerts in the Today Widget
-   Removed the Apple Watch Glance in favor of the faster Complication
-   Improved accessibility of 1Password and forgot password

## Workflow 1.3.1

#### August 31, 2015 Prune

-   A large pile of bug fixes and four new actions

### New Actions (4)

![](https://workflow.is/static/gallery/icons/Text.png)Comment

![](https://workflow.is/static/gallery/icons/Translate.png)Detect Language

![](https://workflow.is/static/gallery/icons/Maps.png)Get Halfway Point

![](https://workflow.is/static/gallery/icons/Web.png)Search Web

### More Improvements

-   Added the ability to send messages to private Slack groups and individual users with **Post to Slack**
-   Fixed many issues with authorization in the Health actions
-   Fixed issues when running Health actions from Apple Watch
-   Fixed issues with Workflow Sync conflicts
-   Fixed a crash when opening a `workflow://run-workflow` URL if the URL did not include an "id" parameter
-   Fixed an issue where **Resize Image** and **Crop Image** would output images of the wrong size
-   Fixed an issue where **Open In** actions would not work from the Action Extension
-   Fixed an issue where **Find Music** may never finish or fail to return any results
-   Fixed an issue where the workflow compose screen may be sluggish while editing text or adjusting sliders
-   Fixed an issue where all of the workflows in the Today Widget could become disabled
-   Fixed an issue where **Send Email** would not send any emails when run from the Today Widget
-   Fixed an issue where dismissing the Today Widget while a workflow was running could cause the workflow to get stuck
-   Fixed an issue where all of the actions in a workflow might temporarily show up as "Missing Actions"
-   Fixed an issue where buttons sometimes would not show up in alerts on the Today Widget
-   Fixed an issue where making PDFs out of HTML files never finished
-   Fixed an issue where audio and video sometimes sent as images via WhatsApp
-   Fixed an issue where the List parameter would not show up in Wunderlist actions
-   Fixed an issue where the variable buttons above the keyboard may not be updated correctly
-   Fixed an issue where the Action Extension would sometimes not show up when activated
-   Fixed crashes when Ask When Run tokens were used in **Post to Tumblr**, **Tweet**, and **Send Email**
-   Fixed crashes when deleting a workflow on one device while it’s open on another
-   Fixed a crash when deleting email accounts on iPad
-   Fixed a crash when running **Make HTML from Rich Text** with blank input
-   Fixed a crash when removing a custom image from a workflow’s icon
-   Fixed many other crashes

## Workflow 1.3

#### August 27, 2015 Ice Cream

-   The new **Today Widget** lets you quickly run workflows from any app by pulling down Notification Center. [Learn more.](https://workflow.is/widget)
-   Introducing **Workflow Sync**, a service to automatically back up your workflows and sync them between your devices.

### New Actions (11)

![](https://workflow.is/static/landing/img/icons/com.panic.iOS.Transmit@2x.png)Share with Transmit

![](https://workflow.is/static/gallery/icons/Health.png)Log Workout

![](https://workflow.is/static/gallery/icons/Calculator.png)Calculate Statistics

![](https://workflow.is/static/gallery/icons/WiFi.png)Get Current IP Address

![](https://workflow.is/static/gallery/icons/Health.png)Log Health Sample

![](https://workflow.is/static/landing/img/icons/com.mipsoft.blindsquare@2x.png)Show in BlindSquare

![](https://workflow.is/static/gallery/icons/Network.png)Get Network Details

![](https://workflow.is/static/gallery/icons/Health.png)Find Health Samples

![](https://workflow.is/static/gallery/icons/Workflow.png)Get My Workflows

![](https://workflow.is/static/gallery/icons/Handoff.png)Continue Workflow in App

![](https://workflow.is/static/gallery/icons/Health.png)Get Details of Health Samples

### Updated Actions

![](https://workflow.is/static/landing/img/icons/com.guidedways.2Do@2x.png)Add 2Do Task

Added the ability to include an action for the task.

![](https://workflow.is/static/gallery/icons/Image.png)Image Actions

Added GIF support to Combine Images, Crop Image, Flip Image, Resize Image, and Rotate Image.

![](https://workflow.is/static/gallery/icons/Tumblr.png)Post to Tumblr

Added the ability to publish a post as a draft, queued, or private.

![](https://workflow.is/static/landing/img/icons/com.todoist.ios@2x.png)Add Todoist Item

Added the ability to choose a reminder service (email, push notification, or text message).

![](https://workflow.is/static/gallery/icons/Photos.png)Edit Image

Now can output high-resolution images (previously the output was constrained to 1024 pixels).

![](https://workflow.is/static/landing/img/icons/net.whatsapp.WhatsApp@2x.png)Send Message via WhatsApp

Now additionally supports sending video and audio.

![](https://workflow.is/static/gallery/icons/Scripting.png)Ask for Input

Improved usability on iPhone 4s.

![](https://workflow.is/static/gallery/icons/Scripting.png)Exit Workflow

Now works in the Action Extension.

![](https://workflow.is/static/gallery/icons/Camera.png)Take Photo

Added the ability to take a photo immediately without needing to tap the shutter.

![](https://workflow.is/static/gallery/icons/Scripting.png)Choose from Menu

Added the ability to provide a prompt to the top of the menu.

![](https://workflow.is/static/gallery/icons/PDF.png)Make PDF

Improved reliability of making PDFs from web pages in the Action Extension.

![](https://workflow.is/static/gallery/icons/Twitter.png)Tweet

Added support for tweeting videos.

### More Improvements

-   Added a URL property to calendar events
-   Improved the reliability of geocoding and reverse geocoding operations
-   Fixed an issue regarding copying locations to the clipboard
-   Fixed an issue where Todoist tasks were saved with incorrect due dates
-   Fixed an issue where **Show Notification** prevented subsequent actions from running in the Action Extension
-   Fixed an issue where traffic would not be taken into consideration in the **Get Travel Time** action
-   Fixed an issue where file extension variants were ignored (i.e. `.jpg` was always replaced with `.jpeg`)
-   Fixed an issue where some actions never finished running if they were offscreen
-   Fixed potential crashes when Workflow for Apple Watch was opened for the first time
-   Fixed an issue where Action Extension workflows received no input when run from a file being displayed in Safari
-   Fixed an issue where HTML entities in web page titles were not properly handled
-   Fixed an issue where albums with multiple discs could not be sorted properly by track
-   Fixed an issue where you could not redo workflow changes on iPhone
-   Other bug fixes and minor additions

## Workflow 1.2.3

#### June 7, 2015 Hummus Sphere

-   Fixed an issue where **Ask for Input** did not work in Action Extensions
-   Improved accessibility

## Workflow 1.2.2

#### June 3, 2015 Energy Truffle

-   Seven new actions that integrate with additional to-do list apps, Imgur, and more
-   Added the ability to send emails immediately without manually pressing Send
-   Made the **Request Uber** action happen immediately without switching to the Uber app

### New Actions (7)

![](https://workflow.is/static/landing/img/icons/com.todoist.ios@2x.png)Add Todoist Item

![](https://workflow.is/static/landing/img/icons/com.realmacsoftware.clear@2x.png)Add Clear List

![](https://workflow.is/static/landing/img/icons/com.6wunderkinder.wunderlistmobile@2x.png)Add Wunderlist Task

![](https://workflow.is/static/landing/img/icons/imgurmobile@2x.png)Upload to Imgur

![](https://workflow.is/static/landing/img/icons/com.marcoarment.instapaperpro@2x.png)Get Instapaper Bookmarks

![](https://workflow.is/static/gallery/icons/Scripting.png)Base64 Encode

![](https://workflow.is/static/gallery/icons/Pinboard.png)Get Pinboard Bookmarks

### iPhone and iPad App Improvements

-   Added a bigger text field to **Ask for Input** with autocorrection
-   Added biking and transit time estimates to **Get Travel Time**
-   Improved action search relevance
-   Workflow now automatically prevents the device from falling asleep while a workflow is running
-   Improved the speed of making PDFs from web pages
-   Added support for Citymapper to **Get Directions**
-   Improved **Record Audio** and fixed crashes with it on iPhone 5 and earlier
-   Fixed making PDFs of web pages that require you to be logged in
-   Fixed issues when reordering workflows
-   Fixed issues getting URLs as input from Tweetbot
-   Fixed display bug in text fields with variables
-   Fixed a crash when authenticating with 1Password on iPad
-   Fixed an issue parsing JSON returned by certain servers
-   Fixed an issue where incorrect workflows were shown in the Action Extension
-   Fixed the ability to paste rich text from Workflow into Mail
-   Fixed an issue where a **Repeat** action inside another **Repeat** action did not work correctly
-   Fixed an issue where a **Repeat** action’s Repeat Index variable was inaccurate
-   Fixed an issue where actions could disappear at the bottom of a workflow
-   Fixed an issue where the keyboard dismissed itself after ten seconds while editing a workflow
-   Improved accessibility
-   Many other bug fixes and minor additions

### Watch App Improvements

-   Added option to **Ask for Input** to directly start voice dictation when run on a watch
-   Added support for **Send Email**, **Select Music**, **Show Notification**, and **Request Uber**
-   Added a character counter to the Twitter compose sheet
-   Added privacy settings when posting to Facebook
-   Improved **Quick Look** for rich text, music, images, and web pages
-   Simplified the main Workflow page by removing View Mode
-   Workflows can now run in the background for up to 3 minutes
-   Improved support for Dynamic Type
-   Improved handling of permissions
-   Fixed an issue where Workflow crashed when it is opened
-   Fixed a crash when generating images of maps
-   Fixed an issue handing off images from the photo library
-   Fixed an issue where **Select Photos** did not work with photos stored in iCloud
-   Improved accessibility

## Workflow 1.2.1

#### April 17, 2015 Toast

-   Many bug fixes and improvements for [Workflow for Apple Watch](https://workflow.is/watch)
-   Added the ability to sign out of services you have authorized Workflow to access, like Dropbox, Evernote, or Tumblr

## Workflow 1.2

#### April 14, 2015 Potato

-   Introducing **Workflow for Apple Watch**, giving you the power of Workflow from your wrist! [Learn more.](https://workflow.is/watch)
-   Eight new actions that take advantage of more of your apps

### New Actions (8)

![](https://workflow.is/static/gallery/icons/Music.png)Get Playlist

![](https://workflow.is/static/landing/img/icons/com.phocusllp.due@2x.png)Add Due Reminder

![](https://workflow.is/static/gallery/icons/QRCode.png)Generate QR Code

![](https://workflow.is/static/landing/img/icons/com.guidedways.2Do@2x.png)Add 2Do Task

![](https://workflow.is/static/gallery/icons/Smiley.png)Get Name of Emoji

![](https://workflow.is/static/landing/img/icons/com.blackfoggames.Schemes@2x.png)Run Schemes Workflow

![](https://workflow.is/static/landing/img/icons/com.tinyspeck.chatlyio@2x.png)Post to Slack

![](https://workflow.is/static/gallery/icons/Handoff.png)Continue on iPhone

### More Improvements

-   Updated workflow type selection
-   Added AIFF option to **Encode Media**
-   Added ability to post videos from the photo library to Instagram
-   Added sentence case to **Change Case**
-   Added the ability to get the organizer of an event from **Get Details of Calendar Events**
-   Added support for Transit app to **Show Directions**
-   Added ability to prepend to files in Dropbox
-   Added an option to overwrite a file in **Save to Dropbox** if it already exists
-   Added an option to not throw an error if a file cannot be found with **Get Files from Dropbox**
-   Fixed an issue with **Make Video from GIF**
-   Fixed a crash downloading Kindle eBooks
-   Fixed making PDFs from files in Dropbox
-   Fixed issues with downloading JSON arrays and dictionaries
-   Fixed an issue where **Expand URL** didn’t fully remove `utm` query strings from some URLs
-   Fixed an issue with opening multiple URLs from the Action Extension on iOS 8.2+
-   Fixed an issue where some workflows did not show up in the Action Extension
-   And a bunch of others, of course!

## Workflow 1.1.2

#### March 13, 2015 Bubble Tea

-   Five new actions, including one to translate text between different languages
-   Added a button to turn a workflow into an action in Drafts
-   Added a plus/minus button to number keypads for typing negative numbers
-   Added a grid mode to **Combine Images** and improved memory handling (it should work in extensions now)
-   Fixed a crash when deleting workflows on iOS 8.3
-   Fixed a crash when running workflows from the home screen

### New Actions (5)

![](https://workflow.is/static/gallery/icons/Translate.png)Translate Text

![](https://workflow.is/static/landing/img/icons/com.skype.skype@2x.png)Call via Skype

![](https://workflow.is/static/landing/img/icons/com.agiletortoise.Tally2@2x.png)Get Tally

![](https://workflow.is/static/landing/img/icons/com.agiletortoise.Tally2@2x.png)Update Tally

![](https://workflow.is/static/landing/img/icons/com.potionfactory.TheHitListMobile@2x.png)Add Task to The Hit List

### More Improvements

-   Fixed an issue where **Edit Image** would shrink images and updated Aviary tools
-   Fixed an issue where **Delete Files from Dropbox** did not properly finish
-   Fixed an issue where adding an event with an alert did not save the alert
-   Fixed an issue where **Play Music** wouldn’t always work
-   Fixed sharing ZIP files
-   Fixed getting workflows from the gallery when using VoiceOver
-   Fixed issues with **Quick Look** at the bottom of the workflow
-   Fixed a bunch of other bugs

## Workflow 1.1.1

#### February 27, 2015 Fruit Salad

-   Quickly search for GIFs with the new **Search Giphy** action
-   New actions to fetch information and contents from articles on the web
-   Fixed issues where certain workflows could crash
-   Fixed an issue where green workflows could not be added to the home screen (yes, really)
-   Updated the Gallery with new workflows
-   Fixed a bunch of other bugs

### New Actions (9)

![](https://workflow.is/static/gallery/icons/DownloadArticle.png)Get Article from Web Page

![](https://workflow.is/static/gallery/icons/Date.png)Get Time Between Dates

![](https://workflow.is/static/gallery/icons/Image.png)Convert Image

![](https://workflow.is/static/gallery/icons/RichText.png)Filter Articles

![](https://workflow.is/static/landing/img/icons/ph.telegra.Telegraph@2x.png)Send Message via Telegram

![](https://workflow.is/static/gallery/icons/RichText.png)Get Details of Articles

![](https://workflow.is/static/gallery/icons/Giphy.png)Search Giphy

![](https://workflow.is/static/gallery/icons/RSS.png)Get RSS Feeds from Page

![](https://workflow.is/static/landing/img/icons/fm.overcast.overcast@2x.png)Add to Overcast

### More Improvements

-   Added Date support to **Ask for Input**
-   Added ability to reorder favorited actions
-   Added proper title case support in **Change Case**
-   Added Atom feed compatibility to **Get RSS Feed Items**
-   Added keyboard commands: ⌘R to run the currently open workflow, ⌘**.** to stop.
-   Added Last Modified Date and Creation Date properties to files
-   Added 1Password support for logging into some services
-   Improved filtering by screenshots
-   Fixed an issue where workflows containing filtering actions could crash
-   Fixed an issue where viewing certain workflows on the Gallery could crash
-   Fixed an issue where **Make Video from GIF** would not work
-   Fixed an issue where **Random Number** would not produce a random number
-   Fixed an issue where **Record Audio** would not work on older devices
-   Fixed an issue where adding a workflow with an apostrophe in its name to the home screen would not work
-   Fixed an issue causing older workflows with repeat loops to not work
-   Fixed an issue that could cause the app to hang on launch
-   Various other fixes

## Workflow 1.1

#### February 12, 2015 Soup

-   Quickly run workflows from My Workflows by double tapping on them
-   Use the selected text from Safari as input to an Action Extension workflow
-   Actions to filter and get details of all the content on your device
-   Duplicate workflows to make your own versions
-   Create a custom home screen icon for your workflow using photos from your library
-   Now accessible for VoiceOver users
-   Added Apps section for easy discovery of actions that interact with your other apps
-   Added the ability to mark actions as favorites to quickly use them later
-   Improved the Workflow URL scheme — [see documentation here](https://help.apple.com/workflow/#/apd621a1ad7a)
-   Improved overall responsiveness, speed, and launch time

### New Actions (54)

![](https://workflow.is/static/gallery/icons/Date.png)Add New Event

![](https://workflow.is/static/gallery/icons/Pinboard.png)Add to Pinboard

![](https://workflow.is/static/gallery/icons/Text.png)Change Case

![](https://workflow.is/static/landing/img/icons/com.realmacsoftware.clear@2x.png)Add Clear Task

![](https://workflow.is/static/gallery/icons/Date.png)Filter Event Attendees

![](https://workflow.is/static/gallery/icons/Date.png)Find Calendar Events

![](https://workflow.is/static/gallery/icons/Reminders.png)Find Reminders

![](https://workflow.is/static/gallery/icons/Contacts.png)Get Details of Contacts

![](https://workflow.is/static/gallery/icons/Location.png)Get Details of Locations

![](https://workflow.is/static/landing/img/icons/com.ideashower.ReadItLaterPro@2x.png)Get Items from Pocket

![](https://workflow.is/static/gallery/icons/Calculator.png)Random Number

![](https://workflow.is/static/gallery/icons/Calculator.png)Round Number

![](https://workflow.is/static/gallery/icons/Calendar.png)Show in Calendar

![](https://workflow.is/static/gallery/icons/CloudApp.png)Upload to CloudApp

![](https://workflow.is/static/gallery/icons/Reminders.png)Add New Reminder

![](https://workflow.is/static/landing/img/icons/com.ideashower.ReadItLaterPro@2x.png)Add to Pocket

![](https://workflow.is/static/gallery/icons/Image.png)Combine Images

![](https://workflow.is/static/gallery/icons/Image.png)Crop Image

![](https://workflow.is/static/gallery/icons/Documents.png)Filter Files

![](https://workflow.is/static/gallery/icons/Contacts.png)Find Contacts

![](https://workflow.is/static/gallery/icons/Scripting.png)Generate Hash

![](https://workflow.is/static/gallery/icons/Date.png)Get Details of Event Attendees

![](https://workflow.is/static/gallery/icons/Music.png)Get Details of Music

![](https://workflow.is/static/gallery/icons/Videos.png)Make Video from GIF

![](https://workflow.is/static/gallery/icons/Microphone.png)Record Audio

![](https://workflow.is/static/landing/img/icons/net.whatsapp.WhatsApp@2x.png)Send Message via WhatsApp

![](https://workflow.is/static/landing/img/icons/com.flexibits.fantastical2.iphone@2x.png)Show in Fantastical

![](https://workflow.is/static/gallery/icons/URL.png)URL Encode

![](https://workflow.is/static/landing/img/icons/com.flexibits.fantastical2.iphone@2x.png)Add Reminder via Fantastical

![](https://workflow.is/static/gallery/icons/Date.png)Adjust Date

![](https://workflow.is/static/landing/img/icons/com.dayonelog.dayoneiphone@2x.png)Create Day One Entry

![](https://workflow.is/static/gallery/icons/Dropbox.png)Delete Files from Dropbox

![](https://workflow.is/static/gallery/icons/Image.png)Filter Images

![](https://workflow.is/static/gallery/icons/Music.png)Find Music

![](https://workflow.is/static/gallery/icons/Battery.png)Get Battery Level

![](https://workflow.is/static/gallery/icons/Documents.png)Get Details of Files

![](https://workflow.is/static/gallery/icons/Reminders.png)Get Details of Reminders

![](https://workflow.is/static/landing/img/icons/com.goodiware.goodreader4@2x.png)Open in GoodReader

![](https://workflow.is/static/gallery/icons/Date.png)Remove Events

![](https://workflow.is/static/landing/img/icons/net.whatsapp.WhatsApp@2x.png)Send Photo via WhatsApp

![](https://workflow.is/static/landing/img/icons/com.outerspaceapps.itranslate@2x.png)Show in iTranslate

![](https://workflow.is/static/landing/img/icons/com.marcoarment.instapaperpro@2x.png)Add to Instapaper

![](https://workflow.is/static/gallery/icons/Calculator.png)Calculate

![](https://workflow.is/static/gallery/icons/Dropbox.png)Create Folder in Dropbox

![](https://workflow.is/static/gallery/icons/URL.png)Expand URLs

![](https://workflow.is/static/gallery/icons/Location.png)Filter Locations

![](https://workflow.is/static/gallery/icons/Photos.png)Find Photos

![](https://workflow.is/static/gallery/icons/Date.png)Get Details of Calendar Events

![](https://workflow.is/static/gallery/icons/Image.png)Get Details of Images

![](https://workflow.is/static/gallery/icons/Maps.png)Get Distance

![](https://workflow.is/static/gallery/icons/Tumblr.png)Post to Tumblr

![](https://workflow.is/static/gallery/icons/Reminders.png)Remove Reminders

![](https://workflow.is/static/gallery/icons/Dictionary.png)Show Definition

![](https://workflow.is/static/landing/img/icons/com.blackfoggames.TextTool@2x.png)Transform Text with TextTool

### Updated Actions

![](https://workflow.is/static/gallery/icons/Calculator.png)Calculate

Now supports the modulus operator and scientific calculations.

![](https://workflow.is/static/gallery/icons/Date.png)Format Date

Now supports formatting into RFC 2822, ISO 8601, or any arbitrary format.

![](https://workflow.is/static/gallery/icons/Scripting.png)If

Now supports checking whether the input is equal to, greater than, or less than a certain value.

![](https://workflow.is/static/gallery/icons/Image.png)Resize Image

Now can maintain the original image aspect ratio by leaving either the width or height blank.

![](https://workflow.is/static/gallery/icons/Scripting.png)Speak Text

Now can speak in different languages and at different pitches.

![](https://workflow.is/static/gallery/icons/Scripting.png)Choose from List

Now shows an image picker when choosing from a list of images and can display a prompt message.

![](https://workflow.is/static/gallery/icons/Dropbox.png)Get Files from Dropbox

Now supports fetching entire folders of files.

![](https://workflow.is/static/gallery/icons/GIF.png)Make GIF

Now supports creating animated GIFs from videos passed into the action.

![](https://workflow.is/static/gallery/icons/Camera.png)Save to Photo Album

Now supports saving to a specific photo album rather than just the Camera Roll.

![](https://workflow.is/static/gallery/icons/Camera.png)Take Photo

Now supports using the volume buttons to snap photos.

![](https://workflow.is/static/gallery/icons/Photos.png)Edit Image

Now supports selecting a default tool and can be used in Action Extensions.

![](https://workflow.is/static/gallery/icons/Date.png)Get Upcoming Events

Now supports retrieving events from a specific calendar.

![](https://workflow.is/static/gallery/icons/Apps.png)Open App

Now supports opening a wider variety of apps, including with the Open In action.

![](https://workflow.is/static/gallery/icons/QRCode.png)Scan QR/Bar Code

Now supports tap-to-focus and camera flash settings.

![](https://workflow.is/static/gallery/icons/Scripting.png)Wait to Return

Now waits until after a phone call or FaceTime call finishes before continuing.

![](https://workflow.is/static/gallery/icons/QuickTime.png)Encode Media

Now supports speed adjustment and exporting as MP3.

![](https://workflow.is/static/gallery/icons/Reminders.png)Get Upcoming Reminders

Now supports retrieving events from a specific list.

![](https://workflow.is/static/gallery/icons/Web.png)Open URLs

Now supports opening multiple URLs at once in Safari and Google Chrome.

![](https://workflow.is/static/gallery/icons/Maps.png)Search Local Businesses

Now supports specifying a maximum distance from your current location to search for businesses.

![](https://workflow.is/static/gallery/icons/Scripting.png)Nothing

Continues to do nothing.

### Noteworthy Bug Fixes

-   Fixed an issue with the Action Extension which caused a workflow to be emptied of its actions
-   Fixed an issue where actions would disappear while scrolling through long workflows
-   Decimal numbers are now correctly handled in international locales
-   When importing workflows, existing workflows with the same name are no longer overwritten
-   All keyboards now provide "Done" buttons for easy dismissal
-   Imported workflows now ask for user permission before running for the first time
-   Special characters in workflow names are now handled properly
-   The app badge has been removed to reduce confusion
-   Resolved some issues surrounding unicode characters (Some issues still remain, especially regarding **Quick Look**. We’re working on it!)
-   Fixed an issue where the output of a workflow would not be displayed
-   Replaced ugly green color with wintermint green
-   ...and many more!

### Noteworthy Action Fixes

-   **Make Zip** now works
-   **Phone Number** now supports international phone numbers and short codes
-   **Run Pythonista Script** now properly handles input
-   **Rotate Image** now correctly handles images of any orientation
-   Fixed issues causing Twitter and Evernote authentication to not work
-   Photos passed into Action Extension workflows can now be deleted
-   **Get Contents of URL** now correctly handles network errors
-   **Append to Dropbox File** now supports appending to files inside folders
-   Getting text from Dropbox files now works properly
-   **Trim Video** now works properly on iPhone
-   **Run Script from SSH** now handles output without crashing
-   **Combine Text** now supports blank separators
-   Improved creating Evernote notes from HTML or from other notes
-   Improved **Date** action and other date entry fields
-   Fixed compatibility with some apps (such as Transmit) in **Share with Extensions**
-   Improved detection of screenshots in **Get Latest Screenshots** for varied device sizes
-   The **URL** action now supports URLs that are just a scheme
***

==**66482**== Words

- **[What's New - Workflow](https://workflow.is/whatsnew)**