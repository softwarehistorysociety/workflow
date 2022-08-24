# "Understanding Action Extension input types"

*23-08-2022 22:31* 

> Advanced workflows
Advanced workflows

![](https://help.apple.com/workflow/en.lproj/GlobalArt/AppIconDefault_Workflow.png)

If you’ve set a workflow as an Action Extension, you can open the workflow from within other apps using the iOS share sheet. When run from the share sheet, the workflow receives input from the app it’s running within, such as a URL or an image. The input from the host app is passed into the first action of your workflow.

When a workflow is set as an Action Extension, you can specify which input types the workflow can accept. The default input type is Anything, which allows the workflow to appear when the Action Extension is run from any app.

When you change input types, the workflow will appear only in apps that share the specified type of content. For example, a workflow that accepts only URLs appears when you run the workflow from Safari, but does not appear when you run the workflow from Photos. Workflows that don’t work with the current app are hidden.

![List of input types, with selection checkmarks](https://help.apple.com/workflow/en.lproj/Art/S0166_InputTypes.png)

**Tip:** Specify an input type for each of your Action Extension workflows so that your share sheet is organized when opened.

*Note:* At times, workflows may appear in unexpected places. For example, a workflow that accepts images appears when sharing a webpage in Safari (because webpages can contain images).

The following table lists supported Action Extension input types.

| 
Input type

 | 

Definition

 |
| --- | --- |
| 

Phone numbers

 | 

Telephone numbers (automatically identified in text by Workflow)

 |
| 

Contacts

 | 

Contact cards shared from the Contacts app or vCard files

 |
| 

Email addresses

 | 

Email addresses (automatically identified in text by Workflow)

 |
| 

iTunes products

 | 

Items shared from the iTunes Store app, including music, movies, TV shows, music videos, ringtones, and alert tones (also includes iBooks content shared from the iBooks Store)

 |
| 

App Store apps

 | 

Apps shared from the App Store

 |
| 

Locations

 | 

Street addresses (automatically identified in text by Workflow) or locations shared from the Maps app

 |
| 

Maps links

 | 

Links to locations or directions from Maps or other navigation apps

 |
| 

URLs

 | 

Any URL, whether a web link (such as `http://`) or another scheme (such as `twitter://`)

 |
| 

Safari web pages

 | 

Pages shared from the Safari app or the Safari View Controller in third-party apps

 |
| 

Articles

 | 

Articles identified when a web URL is passed as input, including details such as Title, Author, Published Date, Body, Excerpt, Number of Words, and Main Image URL

 |
| 

Rich text

 | 

Text with formatting applied, including HTML from webpages and content in text editors, such as Microsoft Word

 |
| 

Text

 | 

Plain text with no applied formatting

 |
| 

Files

 | 

Any file, including documents, images, PDFs, zips, and more

 |
| 

PDFs

 | 

PDF files

 |
| 

Images

 | 

Image files. Includes images from apps and on the web, as well as photos shared from the Photos app

 |
| 

Media

 | 

Video and audio files

 |
| 

Dates

 | 

Dates and times automatically identified by iOS (To run a workflow with a date as input, in any app, touch and hold an underlined date, such as “tomorrow at 4 PM,” tap Share, then tap Run Workflow.)

 |

**Tip:** To explore the share sheet of an app and what it passes into Workflow, set up a workflow that accepts Anything and only includes a View [Content Graph](https://help.apple.com/workflow/#/apda4856024a) action. When run as an Action Extension in an app, the content items that the Content Graph can identify are displayed.

[Previous](https://help.apple.com/workflow/#/apd43b69f337) [Next](https://help.apple.com/workflow/#/apd71b0ac246)

© 2018 Apple Inc. All rights reserved.
***

==**3217**== Words

- **[Understanding Action Extension input types - Workflow Help](https://help.apple.com/workflow/#/apd6e3d33040)**