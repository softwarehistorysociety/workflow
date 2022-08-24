# "Automating Bear, Part 1"

*23-08-2022 23:02* 

> Get help and suggestions for your iOS shortcuts and productivity apps.
Get help and suggestions for your iOS shortcuts and productivity apps.

## [Automating Bear, Part 1](https://club.macstories.net/posts/automating-bear-part-1)

[Bear](https://itunes.apple.com/us/app/bear-beautiful-writing-app/id1016366447?mt=8&uo=4&at=10l6nh&ct=ms_weekly), a new note-taking app for iOS and macOS [I reviewed last week](https://www.macstories.net/stories/why-im-considering-bear-as-a-notes-app-replacement/), already offers [a solid selection of URL schemes](http://www.bear-writer.com/x-callback-url/) with x-callback-url support that can be used to automate different aspects of the app. While waiting for Workflow to implement native Bear actions, we can use these URL schemes “the old way” to integrate Bear with other iOS apps, and particularly Safari.

Today, I’m going to highlight two URL schemes from Bear’s initial library.

With the first scheme, Bear can grab the URL of a webpage, convert its contents to Markdown, and save it as a note. The primary purpose of this command is to turn web articles into readable Markdownified versions in plain text that preserve links and formatting. You might be familiar with existing web services that accomplish a similar goal, such as [Brett Terpstra’s excellent Marky](http://brettterpstra.com/2012/06/20/marky-the-markdownifier-reintroductions/).

![](https://gallery.mailchimp.com/9f4b80a35728f7271fe3ea6ff/images/a2469f22-ad2a-46b5-a1ff-033dceb266bd.jpeg)

The URL scheme is fairly easy to comprehend:

**bear://x-callback-url/grab-url?url=**

As you can see, all we need is a single `url` parameter where we’ll pass the URL of a webpage to convert to Markdown. This can be integrated with Workflow in four actions and run as an action extension from Safari or any other app that can share URLs with the share sheet.

First, we can set the workflow to run as an action extension that accepts Safari web pages as well as URLs. This ensures the workflow will show up in the extension both in Safari and third-party apps like Tweetbot. Then, we can use ‘Get URLs from Input’ to isolate the input URL, expand it to the full domain as a precaution, and combine the URL with Bear’s URL scheme. Finally, using ‘Open URLs’ will launch Bear, which will grab the URL, convert it to Markdown, and save it as a note.

![](https://gallery.mailchimp.com/9f4b80a35728f7271fe3ea6ff/images/625e251c-5c7b-43fa-9313-f61a0bbefb54.jpeg)

There are two optional parameters we could use to enhance the behavior of the URL-grabbing process. Including `noimages` would force Bear to exclude image URLs from the webpage’s source; `tags` would let us pass a comma-separated list of tags in case we want to save a webpage with some pre-defined tags. I don’t use these parameters, but you might find them useful.

You can [get the workflow here](https://workflow.is/workflows/a3cc278a3e0d41fda05d1a90a55351ba).

In the other workflow I created, we can use Bear’s standard URL scheme to create a new note and integrate it with Safari’s webpage selections to turn whatever is selected in a webpage and save it as a Markdown note.

The key idea is to take advantage of the Workflow extension’s ability to read what the user has selected on a webpage in Safari or Safari View Controller. Using the properties of a Safari web page, we can use the ‘Get Details of Safari Web Page’ action to specifically extract the Page Selection. This item will be returned as rich text directly from Safari; we need to use ‘Make Markdown from Rich Text’ if we want Bear to save the text with formatting intact.

![](https://gallery.mailchimp.com/9f4b80a35728f7271fe3ea6ff/images/92bc779b-6350-4489-a8dc-e3600d7c4b7f.jpeg)

From the same Safari web page item, we can also fetch the title of the webpage by isolating the ‘Name’ detail, saving it to a separate variable.

At this point, we need to mix and match the Bear URL scheme with previously saved variables. Here, you can see one of the many advantages of using Workflow to manage URL schemes: we don’t have to encode anything because Workflow takes care of doing that for us.

![](https://gallery.mailchimp.com/9f4b80a35728f7271fe3ea6ff/images/ee5cbd48-0358-4686-86d3-b1d9de739293.jpeg)

*Please note: the workflow has to be triggered from Safari with the action extension using the share icon in the Safari toolbar.*

I’ve found myself using this workflow quite a bit to save snippets from webpages into the app while keeping their links and formatting intact – something I can’t do with Apple Notes’ extension.

You can [get the workflow here](https://workflow.is/workflows/148730f7d1bb4dfbb3a5655d1c4545e4).

### Saving Tasks with Files to Todoist

Something I’ve recently noticed is that I waste a lot of time uploading files to Dropbox just to add their links as comments to tasks. I often need to refer back to files – usually spreadsheets and PDFs – for certain MacStories-related tasks, and I realized I could take advantage of [Todoist’s native attachment feature](https://support.todoist.com/hc/en-us/articles/205348311-Comments-and-Files) to create new tasks with files inside.

Unfortunately, the Todoist extension on iOS doesn’t support creating tasks with files passed from the system share sheet. However, its shortcomings can be easily remedied with Workflow and its built-in Todoist integration.

Obviously, a workflow running inside an action extension has no problem with interpreting whatever kind of file is passed to it as a variable. All it takes is setting a workflow to accept ‘Anything’ in the extension settings and then saving the input to a File variable at the beginning. Doing this will grab any kind of file you might share from any iOS app and put it aside as a variable.

![](https://gallery.mailchimp.com/9f4b80a35728f7271fe3ea6ff/images/147c7a2f-5c68-4aea-9ae3-497efd0297d4.jpeg)

Thanks to Todoist’s natural language support for dates, we can be creative and try to type a due date in plain English in an ‘Ask for Input’ variable, which will also save its contents to a variable. You can try to type queries such as “next Monday at 2 PM” or “tomorrow at noon” and Todoist will parse the date and set it accordingly.

Before invoking the ‘Add Todoist Item’ action at the end of the workflow, we need to get the File variable again. This way, Workflow will pass the file as input to the Todoist API, which will recognize it’s dealing with a file, and it’ll save it in the note area of the task.

![](https://gallery.mailchimp.com/9f4b80a35728f7271fe3ea6ff/images/285fd9ac-7012-4468-9678-7595c9ae02b2.jpeg)

Speaking of which: in my workflow, I set the Content and Project fields of the new task to use an ‘Ask When Run’ token; this will prompt you to type and pick a task’s name and project every time. If you want these values to be fixed, you can use any other variable or select a project beforehand in the Todoist action.

One last note: you might come across a bug in Todoist for iOS that will prevent you from tapping on the file attached to a task.

![](https://gallery.mailchimp.com/9f4b80a35728f7271fe3ea6ff/images/aa16029a-e283-45ec-9fc2-fd20f3db9b34.jpeg)

In my tests, opening the Todoist website in Safari confirmed that the file was attached successfully, and I could tap on it to open it in a new tab. Todoist will use its own CDN to host your file uploads – keep this in mind if you’re dealing with sensitive documents you don’t want to be uploaded anywhere else.

With this system, I can now create new Todoist tasks with file attachments in any iOS app (but usually my email client) without having to upload to Dropbox first.

You can [get the workflow here](https://workflow.is/workflows/e6979ee9de764f4483580cb6812c7d57).

### Zapier: From MailChimp Newsletter to Twitter and Airtable

I often get asked how and why I use [Zapier](https://zapier.com/app/explore) for web automation instead of IFTTT or native automation on iOS. Given my increased reliance on Zapier (I’m about to start paying for an Annual Business plan, which should give you an idea of how much I use the service), I thought the Workflow Corner section should be expanded to include Zapier as well. Starting with this issue, expect to find essential workflows and answers to members that include Zapier examples in addition to Workflow for iOS.

Today, I’m going to cover a basic Zapier workflow that runs automatically every week and that should give you an initial idea of the differences between Workflow, IFTTT, and Zapier.

Every week, I want the [@ClubMacStories](https://twitter.com/clubmacstories) Twitter account to tweet when a new issue of MacStories Weekly has been released. At the same time, I also want to build an archive of issues in [Airtable](https://airtable.com/). This is a perfect task for Zapier, which, unlike IFTTT, supports multiple actions after a trigger. This enables us to build simple workflows that perform one action in response to a trigger, as well as more advanced workflows that perform *dozens* of actions after a condition has been triggered.

Today’s workflow uses one trigger and two actions.

Zapier can connect to hundreds of web services natively, and MailChimp is one of them. Create a new zap (what Zapier calls its workflows), select MailChimp as a trigger, and then search for all supported MailChimp triggers. Like IFTTT, Zapier allows you to choose which kind of condition has to be met for a workflow to be triggered. In our case, we want to choose New Campaign, which triggers when a new campaign (like this issue of MacStories Weekly) is created or sent.

![](https://gallery.mailchimp.com/9f4b80a35728f7271fe3ea6ff/images/7952bd3f-dc38-488b-84df-51f1ac3c8d6b.jpeg)

In the Trigger Options step, you can choose which list Zapier has to monitor, as well as the sending status. I picked ‘Sent’ because I want Zapier to trigger this workflow when emails actually go out to subscribers, not when I create a campaign draft in the MailChimp backend.

![](https://gallery.mailchimp.com/9f4b80a35728f7271fe3ea6ff/images/ca62e922-c24c-4990-a86c-931e9630365f.jpeg)

With the trigger set, we can move to the actions Zapier should perform if there’s a positive match. The first action I added is Create Tweet, which sends a tweet on my behalf for a selected account. The text of the tweet can be edited in the action template, which reveals a major feature of Zapier: fields.

![](https://gallery.mailchimp.com/9f4b80a35728f7271fe3ea6ff/images/ec10c823-501c-45c8-b9ae-2519b5f59294.jpeg)

Like variables in Workflow and ingredients on IFTTT, fields in Zapier contain data that can be reused in actions. Fields can be generated by triggers and actions, and Zapier lets you mix and match fields from different steps with other fields and plain text, too. There is an incredible depth to Zapier fields, which I’ll touch upon in future issues of MacStories Weekly.

One of the fields generated by the MailChimp trigger is the Subject of the campaign that triggered the workflow. Using this field, we can then compose a message that also uses my own text to send the tweets you might have seen on Twitter.

![](https://gallery.mailchimp.com/9f4b80a35728f7271fe3ea6ff/images/7db88c39-d473-4cbf-9aed-c1b2accc2c39.jpeg)

At this point, the workflow could be over here with a single action in response to a trigger, but Zapier lets us go further than that. We can add another action to the mix – in this case, Airtable’s Create Record action.

![](https://gallery.mailchimp.com/9f4b80a35728f7271fe3ea6ff/images/01f1a5ef-d438-41e7-992a-2fca40574cfc.jpeg)

After connecting to an Airtable account, Zapier lets us pick a destination base and table, where we can create a record with Name and Time Sent fields. In the last two fields, we can also use variables automatically generated by Zapier in the first trigger, which will be used to name the record and give it a timestamp.

![](https://gallery.mailchimp.com/9f4b80a35728f7271fe3ea6ff/images/b5d74f77-fdce-439d-bb5d-955a7502afc4.jpeg)

I’ve been using this Zapier workflow for the past year, and it’s helped me build an automated log of campaign delivery times and a social feed that would have otherwise required manual interaction from me every week.

However, this is only a rudimentary example of what Zapier can do and how we can use it to make web services work for us. I plan to explain and demonstrate lots more in future installments of the Workflow Corner.

[Submit a Shortcut Request](https://docs.google.com/forms/d/e/1FAIpQLSeViYJRP69lNKgbmNWqxY1iEnz851gLE375swzC12Qarm-RxA/viewform?usp=sf_link)
***

==**10125**== Words

- **[Automating Bear, Part 1](https://club.macstories.net/posts/automating-bear-part-1)**