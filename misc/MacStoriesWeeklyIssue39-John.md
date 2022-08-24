# "MacStories Weekly: Issue 39"

*23-08-2022 23:00* 

> Get help and suggestions for your iOS shortcuts and productivity apps.
Get help and suggestions for your iOS shortcuts and productivity apps.

We recently got a few questions about TaskPaper automation in OmniFocus for iOS, which I wanted to address as they’re quite similar:

**Question:** On a recent episode of Canvas, Frasier mentioned using Workflow to create an OmniFocus project for reading a book (with tasks on a weekly basis to read a chapter). Any chance you can elaborate on how this is done with Workflow? (George Wenzel, [@georgewenzel](http://twitter.com/georgewenzel))

**Question:** I’m looking for a workflow that uses Drafts to send a project to OmniFocus 2.14 using the recently introduced TaskPaper format. Ideally this workflow takes the first line of the draft as the name of the project, and uses all subsequent lines as tasks within that project. (Chris Calmeijer Meijburg, [@chrismb](http://twitter.com/chrismb))

What Chris and George are looking to automate is ideal for the TaskPaper format in OmniFocus, which is meant to simplify the generation of a project template through plain text.

I’m going to use George’s request as an example as it requires the first line of text (followed by a colon) to be the name of a project, and all subsequent lines to be tasks within the project. That’s the basic syntax we need to use for this to work.

![](https://gallery.mailchimp.com/9f4b80a35728f7271fe3ea6ff/images/f5f2e6c3-2622-427a-bd1d-30586ec0b1ea.jpeg)

![](https://gallery.mailchimp.com/9f4b80a35728f7271fe3ea6ff/images/d5427c96-83a7-43fa-a469-38e1898e58eb.jpeg)

All we need to do is set up a workflow that takes input text from the action extension and uses ‘Add TaskPaper to OmniFocus’ to create a new project in the app. In Workflow, make sure to check the ‘Projects’ control so that tasks won’t end up in the Inbox.

In Drafts, create an action that shares an entire draft with the workflow, and save it in the action list. Then, remember to add the first line as the project title (followed by a colon) and tasks as lines preceded by a hyphen. You can check out the TaskPaper documentation for OmniFocus [here](https://discourse.omnigroup.com/t/implementation-details-for-omnifocus-2-14-automation/24179), which can help you understand what you can do with context and date tags as well.

Write out the project in Drafts, run the action, Workflow will launch, and you’ll end up with a new project in OmniFocus within two seconds. You can download the workflow [here](https://workflow.is/workflows/0fc4bb82be8c44a4a6bc86bdc5ebac8a) and the Drafts action [here](https://drafts4-actions.agiletortoise.com/a/1oX).

We also received a lot of requests about using the TaskPaper syntax to add new tasks into **existing** OmniFocus projects. Unfortunately, that still isn’t possible. But here’s the good news: The Omni Group is working on it, and [it should be available in the app soon](https://twitter.com/kcase/status/748197633022275584).

**Question:** I often use a workflow that copies show notes from Overcast to Evernote. As I try to move away from Evernote I would like a similar workflow towards Notes instead of Evernote. I tried to modify the one I use without success as I online end up with txt notes.

The workflow I use: [Overcast Notes to Evernote](https://workflow.is/workflows/ea8448b306104381a24c26a0ac7721e6) (Laurent Ruyssers, [@Lorreruy](http://twitter.com/Lorreruy))

The problem here, as we’ve covered in the past, is Apple Notes’ poor support for rich text.

Unfortunately, while Workflow is able to convert rich text between a variety of formats, the Notes extension doesn’t support creating a note with rich text. iOS’ rich text framework is so bad, most of the time not even manually copying rich text from one app and pasting it into another works consistently. I’m afraid it’s not possible to replicate the workflow you have for Evernote with Apple Notes yet.

**Question:** I have a daily task that consists of:

1.  Receiving a shared Dropbox link of an .MP3 file (They can’t share the entire folder with me or create a new, shareable one);
2.  Opening the link to listen to the file and make sure it’s correct;
3.  Manually saving it to my own Dropbox;
4.  Running a workflow that copies it to my iCloud Drive, deletes it from my Dropbox, and opens iMovie so I can edit a video using this audio file.

I’ve tried to find a way to automate steps 1, 2 and 3, and attach this to my workflow that starts on step 4, but I haven’t been able to do that. Either I end up saving the HTML of the Dropbox shared page, or I end up creating a text file with the shared link on my clipboard written on it. (Marcus Mendes, [@mvcmendes](http://twitter.com/mvcmendes))

To download a file with Workflow from a shared Dropbox link, we first have to “trick” Dropbox into giving us the actual file. To do this, we have to change the `dl=0` bit at the end of a Dropbox shared link to `dl=1`, which I did with a simple regular expression and Replace Text action.

With the proper link, we can then use ‘Get Contents of URL’ to fetch the file, preview it with Quick Look, and do other things with it, such as saving it to iCloud Drive or sharing it again.

I structured my workflow so that it accepts a Dropbox link from the clipboard, which will be expanded to the full `dropbox.com` version before running the regular expression. All the key parts of the workflow are in there, and you should be able to modify it and combine it with any other action or workflow you already have.

You can download the workflow [here](https://workflow.is/workflows/8cea7803c20c498eb5a0e9766481e252).

**Question:** Is it there a way with Workflow to automatically add an identified song from Shazam to a playlist on Apple Music? (Justin Mabee, [@jmabeebiz](http://twitter.com/jmabeebiz))

I wasn’t expecting Shazam to be scriptable with Workflow, but there is something we can do, and it was fun to put together.

![](https://gallery.mailchimp.com/9f4b80a35728f7271fe3ea6ff/images/2d1529b6-02a7-4bea-a84b-04cb959209e7.jpeg)

After tagging a song in Shazam, you can tap on it, then hit Share -> Other Apps to share the selected song with the share sheet. When doing so, the song will be shared as a plain text string formatted as follows:

> I just used Shazam to discover Mirrors by Justin Timberlake. http://shz.am/t80773489

My idea was to use a regular expression to isolate the name of the song and the artist from that standard message. After matching the string with a pattern, the workflow uses capture groups to save the song’s name and artist into two variables, which are then used in a ‘Search iTunes Store’ action to return the first result. Hopefully, if the iTunes API works as expected, that result should be the relevant song shared from Shazam.

![](https://gallery.mailchimp.com/9f4b80a35728f7271fe3ea6ff/images/14eb11d2-f0f0-4163-8bb3-39befd2f5430.jpeg)

Finally, the workflow uses the native Apple Music integration to save the song into a playlist of your choice. I’ve been testing this workflow with my tag history in Shazam, and it’s worked remarkably well – though you may need to modify it if you’re not using Shazam in English and the sentence shared from the app is different. In that case, you can change the first action (the one with the regex pattern) to match your language while keeping all the special characters and groups.

You can download the workflow [here](https://workflow.is/workflows/8dae964835304264b5cfd31e6d06c161).

**Question:** I have been trying to get simple weather (high and low temperatures for the day) information based on my location built into a workflow, but have had no luck. (Jeremy, [@Jeremyfrick](http://twitter.com/Jeremyfrick))

I don’t think I could do a better job than what’s already been done by the Workflow community in this case (at best, I’d remake the same workflows). There are two Reddit threads with some excellent weather workflows built for the Yahoo and Forecast.io APIs. You can find them [here](https://www.reddit.com/r/workflow/comments/2xnv9e/is_this_possible_create_a_workflow_runs_every/) and [here](https://www.reddit.com/r/workflow/comments/2wgo5s/today_weather_forecast_forecastio/). There are some instructions to follow, but the authors did a good job in explaining what you’ll need to do.

**Question:** I’m not a big Workflow user, so this may be obviously not be possible. I was hoping to take an Apple note and export it to Day One, capturing the text as well as the date created. My habit is to go to Apple Notes for default note creation, but I may have to change that habit as I try to use Day One more often. (Nathan)

Sending text from Apple Notes to Day One would be as simple as running this workflow as an action extension in Notes:

![](https://gallery.mailchimp.com/9f4b80a35728f7271fe3ea6ff/images/00fe04a7-1268-47f4-b2cf-b137dfb7f60f.jpeg)

However, Apple Notes doesn’t currently expose date information for individual notes, which means you wouldn’t be able to recreate entries in your diary matching the date created in Notes.

**Question:** I’m looking for a way to automate my Instagram workflow using Due much like the DueMessage workflow you explained in [a past issue](http://us8.campaign-archive1.com/?u=9f4b80a35728f7271fe3ea6ff&id=fc706e9cf2&e=79be37a0b8), is there any way to:

1.  Select a photo;
2.  Store that photo (Dropbox or iCloud?);
3.  Enter a caption;
4.  Set a Due reminder;
5.  At posting retrieve all these things, add the caption to the clipboard, and post to Instagram.

I’ve tried this, but I can’t get Workflow to find the photo at posting time. (Chad, [@chadlenberg](http://twitter.com/chadlenberg))

This was a fun variation of my original DueMessage workflow, which for the occasion I renamed ‘DuePicture’ and that uses Workflow’s native Instagram action to send a photo to the app.

Much like the original workflow, this one uses a custom text separator to divide two text lines and embed them in a Workflow URL scheme to be included in a reminder inside Due. However, because this time we’re dealing with a picture, the first line of text before the separator is a filename, not a phone number.

I’ve thought about how to upload an image before saving the reminder in Due, and I chose to settle with iCloud Drive. iCloud has superior integration than Dropbox on iOS, and it’s easier (and faster) to retrieve files from the /Workflow/ directory in iCloud Drive just by using their filenames. Therefore, every time you run the workflow for the first time, you’ll be asked to pick a picture from your library, which will be saved in the Workflow folder in iCloud Drive for later. You’ll also be asked to enter a caption.

![](https://gallery.mailchimp.com/9f4b80a35728f7271fe3ea6ff/images/9b0bd2ef-ba16-4c49-9a9e-a25470d16b88.jpeg)

Once you mark the reminder as complete in Due, run the workflow, and the image will be fetched using the original filename again (make sure you don’t change it in the meantime, or the workflow will break) and the caption will be copied to the clipboard. Instagram will launch with the picture already open in editing mode, and you’ll be able to paste the text caption in the appropriate field.

![](https://gallery.mailchimp.com/9f4b80a35728f7271fe3ea6ff/images/c8b5c721-8721-4eb6-b0c2-9b19cf581e92.jpeg)

I’m quite happy with the structure of my original DueMessage workflow, which could be applied to DuePicture as well (and I assume it could work just as well for any other type of file). You can download the workflow [here](https://workflow.is/workflows/336b1a9674894b43a974ce51a9d8af86).

**Question:** Is there a way to open a text file from Dropbox in Drafts, edit it and save changes to Dropbox in the exact same file? (Rafał Sobolewski, [@Sobolowy](http://twitter.com/Sobolowy))

There’s no native way to open, edit, and sync existing Dropbox files with Drafts alone, but we can work around it thanks to Workflow.

Here’s my idea: with a workflow, we can fetch a text file from Dropbox, send the filename and text to Drafts, make edits there, and relaunch the same workflow to change the text contents back into the same file.

The reason we need to fetch the filename as well is that we need a way to tell Workflow which original file to overwrite after we’ve made changes in Drafts. The method is similar to the DueMessage and DuePicture workflows – we’re going to join two text strings (the filename and body text) with a custom separator that Workflow will later break into a list of two items.

When running the workflow for the first time, you’ll be asked to pick a file, which will be sent to Drafts. In Drafts, the file will be presented with the filename as the first line and the body text below. **Do not change the filename line**, or the workflow won’t be able to update the original file later.

After making edits to the body text in Drafts, Drafts will launch the same workflow again. Because the workflow sees that there’s some input this time, a conditional block will force it to process the input text instead of picking a Dropbox file again. In the input text, Workflow will separate the filename from the updated body text and it’ll overwrite the original file in Dropbox for you, creating a new version of it.

There’s one caveat to keep in mind: Workflow can’t fetch the file path of the original file as a variable. This means you’ll have to modify the directory where your text files are located in the final ‘Save to Dropbox’ action (mine is `/Apps`), or enter a directory each time if files don’t always come from the same folder in Dropbox.

You can download the workflow [here](https://workflow.is/workflows/4b6fceb531184af684afda0a8517ff08) and the Drafts action [here](https://drafts4-actions.agiletortoise.com/a/1oY).

**Question:** I’d like to start with three lines in Drafts (a date, a number, and another number) and end up with that info in a spreadsheet (Numbers, Excel, Sheets, Airtable, doesn’t matter, provided it can produce a graph of the data). The best I can do is a Drafts action that copies the info and opens the correct Sheets where I can paste it, but that puts that data in one column, whereas I want it in one row. Any ideas? (Mark Miller, [@MarkDMill](http://twitter.com/MarkDMill))

The best way to do this, in my opinion, is to rely on [Workflow and its IFTTT integration](https://www.macstories.net/ios/workflow-adds-ifttt-integration/) to send data to Google Sheets.

From Drafts, you can type out three lines of text normally, then run an action to send the`[[draft]]` to Workflow, which will split the three lines in a list. Each line is saved to a variable, so that we can later use them all as ingredients in an IFTTT recipe. These will be the entries that will be appended as a row in Google Sheets.

![](https://gallery.mailchimp.com/9f4b80a35728f7271fe3ea6ff/images/3f36afc3-1fb9-4e67-afec-3ec3e2ef5cfd.jpeg)

On IFTTT, all you need to do is prepare a recipe that takes input from Workflow and communicates with an existing spreadsheet in Google Sheets to save three ingredients as a new row. You can take a look at my recipe above – the setup is simple. Once you run the workflow, the new row will show up in Google Sheets within seconds.

You can download the workflow [here](https://workflow.is/workflows/b9f29f4a48d3447db3b48070c494f185).

**Question:** This might be a workflow request but figured I would ask it as a question first - is there a way to compose an email on a Mac using Markdown natively within Apple’s Mail.app (e.g., using AppleScript)? I’m not yet a fan of Airmail or Postbox which can do this natively so am sticking with Mail.app. I also realize I could compose a draft using a Markdown editor like Byword and then copy and paste RTF into an email in Mail.app but that’s a lot of friction. (Anand Mandapati, [@anandman](http://twitter.com/anandman))

Anand, based on your question, I assume you want to compose email messages in Markdown and then convert them to rich text before sending. If that’s the case, Brett Terpstra has a great solution. [Brett has a series of OS X Services](http://brettterpstra.com/projects/markdown-service-tools/) designed to make writing in Markdown on the Mac easier. One of those services, called ‘Convert - MultiMarkdown to RTF’ can take Markdown-formatted text and convert it to rich text in place in any text field that supports rich text.

In Mail.app all you need to do is compose your email in Markdown, highlight the text, pick the services menu item by right-clicking (or from the menu), and pick ‘md Convert - MultiMarkdown to RTF’ to convert your Markdown to rich text. Keep in mind that Brett’s service requires that MultiMarkdown be installed on your Mac. Complete instructions on installing MultiMarkdown, customizing the rich text that is output by the service, and other details, are available on [Brett’s website](http://brettterpstra.com/2013/03/08/new-in-the-markdown-service-tools-in-place-markdown-to-rtf/).

[Submit a Shortcut Request](https://docs.google.com/forms/d/e/1FAIpQLSeViYJRP69lNKgbmNWqxY1iEnz851gLE375swzC12Qarm-RxA/viewform?usp=sf_link)

Your weekly correspondence with the MacStories team.

**Question:** I recently set up iCloud Photo Library on my MacBook Air (128 GB) and my iPhone 6s (64 GB). My photo library is 45 GB. I have enabled the ‘Optimize \[Mac/iPhone\] Storage’ setting on both devices. My iPhone now has 30 GB of photos and videos stored on device, and my Mac has (what looks to be) all 45 GB. My questions are: Do you know when the storage optimization begins? Is there a way to trigger the optimization to begin manually? If I reset my iPhone, and started fresh, would I have access to my iCloud Photo Library with fewer photos and videos being stored on device? (Ryan, [@internetryan](http://twitter.com/internetryan))

I wasn’t able to find any details from Apple on how iCloud Photo Library uploads and subsequent optimization works [other than](https://support.apple.com/en-us/HT204264) “your photos and videos will upload after you connect to the Internet with Wi-Fi and your battery is charged”.

The general consensus from websites and forums (plus personal experience) is that “it takes some time” for optimization to kick in. Here’s what I would do: once you think all your media has been uploaded, go to iCloud.com with a desktop web browser and make sure that all your photos and videos are in there. If optimization doesn’t start working on your devices, try rebooting them and wait a few more days. If you still don’t see the optimization setting in effect, I’d personally get an appointment at the Genius Bar and explain the problem.

I’ve never run into this issue myself – storage optimization always removes local photos from my devices within a few days after the upload is done.

**Question:** Is it possible to disable a specific news source from the Spotlight Suggestions page (the page to the left of the Home Screen)? My feed is constantly populated with articles from a particular news source that requires a paid subscription (NY Times). How do I prevent NY Times articles from appearing on the Spotlight Suggestions page? (Jason Williams, [@jet\_pilot](http://twitter.com/jet_pilot))

I don’t believe there’s any setting to exclude specific sources from Spotlight news suggestions in iOS 9.

However, because iOS 10 is introducing a new Apple News widget, it might be possible to mute and block sources in Apple News and have that reflected in the widget as well. If you’re on the iOS 10 beta, I’d suggest trying that.

Have you got a question for the MacStories team? If you do, you can submit it here. Your question can be about almost anything, it doesn’t need to be related to iOS or Apple.

[Submit your own question](https://docs.google.com/forms/d/e/1FAIpQLScFW-260aVnSpIsa4Uq6OXQOSQ9s5Z07BPpTb_A6slIFdLMgg/viewform?usp=sf_link)

Friends of MacStories share their iPhone, iPad, and Apple Watch Home screens.

![](https://gallery.mailchimp.com/9f4b80a35728f7271fe3ea6ff/images/ea4117f6-9d6a-4b55-a8f1-664ca8bcee83.png)

### Steve

*Club MacStories Member*

[![](https://gallery.mailchimp.com/9f4b80a35728f7271fe3ea6ff/images/dd84c0cc-ebb7-4c18-8109-a9ba843f47e8.jpg)](http://ecfa0642b72b7d727ffc-14520dd7230e61cd34ae17e34731e7a7.r15.cf1.rackcdn.com/IMG_2730.jpg)

I, like many of your readers (just guessing), took the Grey challenge to organise my Home screen. A blank bottom row really does make it look so much more elegant (I never would have guessed it), and there is no going back for me (although his 3-in-the-dock idea breaks the symmetry, which I still don’t get).

I’m right-handed and hold the phone in my left hand – originally so that I could type with my right hand index finger, but now out of habit (I have since learnt to use both thumbs for text entry). Voice Memos occupies the prime real estate for a quick launch with my left thumb. I use it for taking quick memos which I send to different places through the share sheet…and for secretly recording my daughter when she is being cute. Overcast has the next best quick-launch-with-my-thumb spot.

The bottom row contains my messaging apps – left to right in terms of importance. My big frustration is that there is no room on that row for Telegram (my 5th most used messaging app); I wish we had a Franz equivalent for iOS. No Phone icon anywhere – I use Launch Center Pro to make actual phone calls, should the need arise.

[Coffitivity](https://itunes.apple.com/us/app/coffitivity/id669576390?mt=8&uo=4&at=10l6nh&ct=ms_weekly) is my white noise generator of choice – I only need ambient coffee shop sounds. I like the easy way I’m able to adjust the relative levels of their ambient sounds and my music playlist.

I’m currently using [Focus](https://itunes.apple.com/us/app/focus-productivity-timer/id975017240?mt=8&uo=4&at=10l6nh&ct=ms_weekly) as my Pomodoro timer and time tracker. It was an impulse buy and I’m not entirely convinced. I may go back to [Toggl](https://itunes.apple.com/us/app/toggl-work-time-tracker/id885767775?mt=8&uo=4&at=10l6nh&ct=ms_weekly). Another app that might get replaced on my Home screen is PDFScan+ – it takes pictures automatically far too quickly, and I usually have to do it multiple times (even with white paper on a black background). Your Canvas episode came too late to save me some money!

One app that is central to my daily workflow, but really shouldn’t be on my Home screen, is Due. I only use the reminder function to keep me to my routine, and that runs on its own in the background through notifications. I even use Launch Center Pro to add new reminders (with a script that adds emoji). The only reason it is still there is because I can’t decide what should take its spot (Telegram, Airtable, DO Button, and Alto are the current contenders).

I use Xero to track work and personal expenses, and Intro to exchange contact information. Photos makes it because my phone is my only camera. I use Drafts for nearly all text input (which is why the Notes app is in my ‘Reading’ folder), but am now preferring to enter calendar info straight into Fantastical, because of their text entry that makes it so much easier. Fantastical is the one app that makes me smile every time I use it (still!!), although I can’t wait for Calendar Sets to make it to iOS.

My daily workhorse apps are OmniFocus, Trello, and Airmail. I use Trello (with IFTTT integration with Slack) for collaborative work, project retrospectives, and big picture visual stuff (goals, Christmas presents, editorial calendars, etc). I am not a developer, but I think that Kanban boards and agile project management principles should really go out to ordinary people as well. Trello works flawlessly on all platforms, sync is lightning fast, and it kind of terrifies me that we get so much for free.

I use Airmail together with SaneBox, which is the ultimate combination. For the first time in my life I am at 0% anxiety & 100% zen when it comes to email.

In addition to the 4 folders on the top row, I have 8 folders on a second screen: Navigation (Google Maps, Waze), Other Coms (Phone, FaceTime, Telegram, WeChat), Utilities, (cr)Apple, Music & Audio, Health, and Games.

The photo I use for my Lock screen is one I took when on holiday at a resort in Thailand… which also happens to be an elephant sanctuary and a refuge for at-risk women. It’s an amazing [place](https://www.tripadvisor.com/Hotel_Review-g2237291-d3640765-Reviews-The_Chai_Lai_Orchid-Mae_Wang.html) to visit.

If you think you have an interesting iPhone or iPad Home screen, please feel free to submit it! Simply attach a screenshot of your Home screen and in one or two sentences explain what makes it interesting. Please do not send us a full description, we will contact you if we want to feature your Home screen.

[Submit your own Home Screen](mailto:homescreens@macstories.net?subject=Reader%20Home%20Screen&body=If%20you%20think%20you%20have%20an%20interesting%20iPhone%20or%20iPad%20Home%20screen%2C%20please%20feel%20free%20to%20submit%20it!%20Simply%20attach%20a%20screenshot%20of%20your%20Home%20screen%20and%20in%20one%20or%20two%20sentences%20explain%20what%20makes%20it%20interesting.%20Please%20do%20not%20send%20us%20a%20full%20description%2C%20we%20will%20contact%20you%20if%20we%20want%20to%20feature%20your%20Home%20screen.%C2%A0 "Submit your own Home screen")
***

==**21056**== Words

- **[MacStories Weekly: Issue 39](https://club.macstories.net/posts/macstories-weekly-issue-39)**