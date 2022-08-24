# "Direct Download to Dropbox"

*23-08-2022 23:02* 

> Get help and suggestions for your iOS shortcuts and productivity apps.
Get help and suggestions for your iOS shortcuts and productivity apps.

## [Direct Download to Dropbox](https://club.macstories.net/posts/direct-download-to-dropbox)

As we’ve discussed several times on MacStories Weekly in the past, downloading files is one of the areas where iOS is still lagging behind macOS.

Unlike the desktop version, Safari doesn’t have a full-featured download manager on iOS, nor does the iOS UI clearly indicate what type of file is being “downloaded” when you tap on a link and the progress bar starts loading. Some of the issues, however, are inherent to the nature of iOS: unlike desktop computers, which are connected to WiFi most of the time, iOS devices are primarily used on the go; cellular usage becomes a hurdle when downloading large files.

I’ve been thinking about this problem lately, looking for a better solution than having to connect to a [Synology](https://www.synology.com/) NAS to initiate a download. When I was researching the [Dropbox API](https://www.dropbox.com/developers) for the [latest version of Workflow](https://www.macstories.net/ios/workflow-update-brings-ability-to-interact-with-any-web-api/), I came across a method to [start a download for a remote URL](https://www.dropbox.com/developers/documentation/http/documentation#files-save_url), saving the file directly into your Dropbox account without having to download it locally on-device first. After playing around with it for a few days, I realized that the Dropbox API could be combined with Workflow and used to download files from the web to Dropbox while overcoming iOS Safari’s shortcomings and the system’s lack of a download manager. Thus, I wrote a workflow to download files to Dropbox directly over the API.

Before you can use the workflow, you’ll have to create a Dropbox app, set it to “In Development” status, and copy its access token, which is exclusive to your account. This is a necessary step to ensure Workflow can communicate with the Dropbox API, but don’t let the idea scare you. Registering a Dropbox app takes less than a minute and the process is extremely intuitive:

1.  Go [here](https://www.dropbox.com/developers/apps) and create a new app:
2.  Give it a unique name, which stays private to you;
3.  Grant the app access to your full Dropbox and set it to “In Development” for personal use;
4.  Tap the app’s name, scroll, and generate an access token;
5.  Paste the access token at the top of the workflow in the first Text action.

![](https://gallery.mailchimp.com/9f4b80a35728f7271fe3ea6ff/images/26084d52-ce78-40ab-a8d1-c5bf25a5c66a.jpeg)

Only you will be able to use this Dropbox app (provided you don’t share the token with anyone else), so store your credentials somewhere safe, like 1Password.

Now, let’s take a look at the workflow. The token is stored in a text variable that will be used as the header of a POST request later on. Before making any API calls, the workflow assumes you have a link to a public download in your clipboard; Workflow will fetch the link and use a regular expression to extract the filename and extension at the end of the URL (more specifically: any character after a forward slash followed by a dot and a word item before the end of a string – e.g. http://example.com/MyDownload.mp3).

![](https://gallery.mailchimp.com/9f4b80a35728f7271fe3ea6ff/images/3afc7f42-c352-48b9-a309-3e23c79246be.jpeg)

I chose to do it this way so that the downloaded file would have the same filename of the URL version; by default, the workflow will put downloads in the root of your Dropbox as defined by the single ‘/’ in the Name variable. If you want to change the location of the download, modify the base path of the Text action that goes into the Name variable.

The method that Workflow calls on the API is https://api.dropboxapi.com/2/files/save\\\_url, which tells Dropbox to start downloading a file stored at a specific URL without having to pass through a native client first. The request is a POST one, with a JSON request body where the two parameters – url and path define where the file comes from and where it’ll be saved in your Dropbox, respectively.

![](https://gallery.mailchimp.com/9f4b80a35728f7271fe3ea6ff/images/2d3d5841-b022-4559-9fec-daa9a1b30dee.jpeg)

At this point, I could have stopped the workflow and hoped for the best. But that wouldn’t have been fun, and it would have added a layer of confusion to the experience. Because after Workflow makes the request, Dropbox *should* begin the download of the file directly to your account, but it’d be useful to check on the status of the download and know if it was accepted, how it’s going, and when it’s done.

After the first request, Dropbox returns a dictionary where one key – `async_job_id` – gives us an ID of the download task that was started for your account. With that ID, we can hit another API endpoint at `https://api.dropboxapi.com/2/files/save_url/check_job_status` to see the status of the download. Dropbox will return this information in two ways: as in-progress or complete.

![](https://gallery.mailchimp.com/9f4b80a35728f7271fe3ea6ff/images/bb26d1eb-17a3-4762-9ecd-52c048aaa75c.jpeg)

Normally, small files should download within a couple of seconds, but larger files may require a few minutes to be saved into your Dropbox. For this reason, I put a series of checks into the workflow that iterate over the task’s ID and ask you to check again on the completion status of the download until it’s complete.

If, after the first check, the download is reported as complete, an alert will tell you so. However, if the download is still in progress, Workflow will tell you about the ongoing download and ask you if you want to check again.

![](https://gallery.mailchimp.com/9f4b80a35728f7271fe3ea6ff/images/fef0d879-fc87-47db-aca9-7ea5531d9541.jpeg)

![](https://gallery.mailchimp.com/9f4b80a35728f7271fe3ea6ff/images/643252bd-fd2e-4523-af21-15060e38bdea.jpeg)

This repetition is based on a Repeat loop with a custom value of 1000 – a high number that means you’ll be able to check on an ongoing download up to 1000 times (ideally, you will only need to check a handful of times). The loop will repeat itself over and over while the download is in progress on Dropbox.

Once the download is done, the alert will change and the loop will break.

![](https://gallery.mailchimp.com/9f4b80a35728f7271fe3ea6ff/images/90275aae-8add-469c-b87e-de4914b7563e.jpeg)

At this point, you’ll have the choice of creating a shared link for the newly downloaded file, opening it in the Dropbox app as a Universal Link.

![](https://gallery.mailchimp.com/9f4b80a35728f7271fe3ea6ff/images/f5230fba-18de-40e7-9f32-1beaaaff874c.jpeg)

The API call to https://api.dropboxapi.com/2/sharing/create\_shared\_link accepts a single parameter to create a shared link for a file – the same Name variable with the download path we created at the beginning of the workflow. After creating the link, Workflow will copy it to the clipboard and open it in the Dropbox app (if installed), letting you confirm that the file now lives in your Dropbox with the option of sharing it with others.

I’ve been working from iOS for almost five years now, and I can’t tell you how many times I had to wait for downloads to finish in a third-party download manager or just give up and remember to download a file later on my Mac. With this workflow, I can leverage the app’s fantastic web API actions to save bandwidth on my device, reclaim storage, and, more importantly, let Dropbox’s fast servers download files on my behalf and put them on my account in seconds.

In my tests, the workflow has worked well for the majority of servers and file URLs, but some CDNs (like Rackspace) often refused to let Dropbox fetch files for download. Furthermore, if you want to download a file stored behind a short URL, you’ll have to use the ‘Expand URL’ action to reveal the complete path of the download on the web.

Whether you want to download podcast episodes, videos, or other assets you keep in Dropbox, this workflow should improve how you deal with downloads on your iPhone and iPad. As someone who has gone all-in on cloud storage and backups, an easy way to add downloads directly to my Dropbox account was the missing piece of the puzzle.

You can get the workflow [here](https://workflow.is/workflows/c9d822cda12c48768c5ef9c8a2d92519).

### Save Safari Links as Rich Cards in Trello

In an effort to consolidate our editorial calendar in [Trello](https://trello.com/federicoviticci/recommend), I recently moved three text files I was keeping in Apple Notes – App Debuts, Weekly Links, and The Album – to our Club MacStories Trello board. These notes are updated every day with new content; there was no reason I shouldn’t let the rest of the team know what I was saving for Friday, so it made sense to move those to Trello as well.

Workflow ships with native Trello actions, but they lack one feature we rely upon for our board’s organization: labels. We use labels on Trello to indicate whether the entire team or specific members are responsible for certain tasks, and I need to be able to filter tasks that have been assigned to me with the yellow Federico label. This alone was worth experimenting with the [Trello API](https://developers.trello.com/) and learning how to enhance what Workflow can already do with it.

First, I had to [create an API key](https://trello.com/app-key) and a token to make requests to the Trello API. Then, before moving onto the main workflow, I had to fetch the IDs of the Trello boards, lists, and labels I was going to automate.

Thankfully, these IDs can be fetched through dedicated endpoints: as you can see in these [two](https://workflow.is/workflows/1ae745b518024f20a78e3add449c7806) [workflows](https://workflow.is/workflows/f3543a04b8ec4b7c82ddffe54da3b22e), it was all a matter of making a GET request with my account and copying the IDs returned in the response from the Trello API. I temporarily stored the IDs in [Copied](https://itunes.apple.com/us/app/copied-copy-paste-everywhere/id1015767349?mt=8&uo=4&at=10l6nh&ct=ms_weekly) so I could paste them later in Workflow.

![](https://gallery.mailchimp.com/9f4b80a35728f7271fe3ea6ff/images/6ec92c5a-3f52-4dec-8486-d426e3498c3c.jpeg)

For my Weekly Links note, I knew I wanted to make a workflow that, when passed a URL, would save it as a rich Trello card with:

1.  The article’s title as name;
2.  The lead image of the story as cover image in Trello;
3.  A description containing a tappable link at the top (to reopen the link).

That meant I had to work with three types of article details: URL, title, and cover image. Fortunately, Workflow ships with a built-in ‘Get Article from Web Page’ action that, when combined with ‘Get Details of Articles’, returns a variety of details about web articles (this action is powered by [diffbot](https://www.diffbot.com/) behind the scenes). Using those actions was key to assembling the variables needed to turn an article into a rich Trello card.

To create a card with the Trello API, we need to make a POST call with a Form request body containing the list’s ID, a card’s title and due date (`null` in my case) and, optionally, a description (which can be in Markdown), a URL source, and labels. This is where the previously copied IDs for lists and labels came in handy.

![](https://gallery.mailchimp.com/9f4b80a35728f7271fe3ea6ff/images/2bacca3b-a346-4de7-8264-15d69ec239f4.jpeg)

The Trello API, however, doesn’t attach a cover image to a new card upon adding it; putting a cover image on a card has to be a second API call. Thus, the workflow makes another POST request with a multipart Form body that passes the image file parsed from the article, which will be used to present the card in the Trello list.

![](https://gallery.mailchimp.com/9f4b80a35728f7271fe3ea6ff/images/d9dce1ae-8196-47b9-bac5-27e7f29542b3.jpeg)

The final product is a list where each link I (and others) save is a beautiful card with the necessary context to remember why we saved it and read the story again. Overall, this is much better than what I used to do with Notes by myself, and it’s only the beginning of my experiments with the Trello API.

You can get the workflow [here](https://workflow.is/workflows/8f934603b0e440a1a4458d3a51b13e1f).

[Submit a Shortcut Request](https://docs.google.com/forms/d/e/1FAIpQLSeViYJRP69lNKgbmNWqxY1iEnz851gLE375swzC12Qarm-RxA/viewform?usp=sf_link)
***

==**10174**== Words

- **[Direct Download to Dropbox](https://club.macstories.net/posts/direct-download-to-dropbox)**