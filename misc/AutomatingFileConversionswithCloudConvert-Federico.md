# "Automating File Conversions with CloudConvert"

*23-08-2022 23:02* 

> Get help and suggestions for your iOS shortcuts and productivity apps.
Get help and suggestions for your iOS shortcuts and productivity apps.

## [Automating File Conversions with CloudConvert](https://club.macstories.net/posts/automating-file-conversions-with-cloudconvert)

The most common questions from Club MacStories members involve some kind of file conversion. Whether it’s about converting PDFs to images (by far, the most frequent request we receive for this column) or exporting documents to formats that aren’t natively supported on iOS, I’ve read dozens of emails about converting files with Workflow over the past few months. I know what my solution was going to look like in the end, but I also wanted to take my time to do it right and provide a full-featured workflow that would solve everyone’s problems. This week, after I was done with [my iOS 11 concept](https://www.macstories.net/stories/ios-11-ipad-wishes-and-concept-video/) and before leaving for WWDC, I finally had the time to create the workflow I’ve been thinking about for a while.

I’ve been using a service called [CloudConvert](https://cloudconvert.com/) to handle “special” file conversions for the past year or so. CloudConvert is a web app and an [API](https://cloudconvert.com/api) that integrates with other automation tools (such as [Zapier](https://zapier.com/zapbook/cloudconvert/)) to receive files, convert them in the cloud, and feed them back to you in a different format. While a web service for file conversions may seem redundant, consider this: CloudConvert supports [over 200 file types](https://cloudconvert.com/formats), and it can queue multiple conversions in the background and notify you when they’re done with a link to download the converted file. This means that it doesn’t matter if you don’t have an app that can convert PDFs to PNGs, and it won’t be an issue if your old iPad is too slow to encode a 200 MB .MOV video file to .MP4 – CloudConvert can process the conversion in the cloud on your behalf. CloudConvert’s support for multiple file formats (some examples: 3GP, FLAC, and even Numbers/Pages files), combined with its extensible platform, makes it possible to send *anything* we want to the service and integrate its API directly with Workflow on iOS.

Before I dig into the details of the workflows I created, I should mention that CloudConvert is a web service that requires you to upload files for conversion. You should be aware of this if you’re dealing with private documents that you wouldn’t want to be stored on any cloud service. I recommend reading [CloudConvert’s privacy policy](https://cloudconvert.com/privacy) to understand how they will process your files. In addition, while CloudConvert can be used as a free service, there are daily limits for free users, and longer and more time-consuming conversions will require you to purchase paid packs of “conversion minutes”. There’s also a subscription option if prepaid packages aren’t enough for you.

The CloudConvert API can be used in web apps that display the status of a conversion in real-time and that embed native options to download converted files. Obviously, I wanted to offer something more straightforward in Workflow and that could integrate nicely with iOS apps, the share sheet, and the document picker. What I ended up creating is a CloudConvert workflow that supports converting both webpages (as URLs shared with the extension) and files (chosen from the document picker) and that previews the converted file *inside* Workflow, allowing you to share the result instantly with other apps.

Before running the workflow, you’ll have to get your CloudConvert API key. You can find yours [here](https://cloudconvert.com/user/profile) after creating a CloudConvert account. As with other web-based workflows I’ve shared before, I recommend fetching the key from a text file in iCloud Drive rather than pasting it as plain text in a workflow. You can use [this workflow](https://workflow.is/workflows/fe264e02e3de40ce8f823da9d8271da9) to save the API key to a file named ‘CloudConvert.txt’ into iCloud Drive/Workflow/Logins.

The workflow supports converting both websites to images or PDF, as well as any other file type mentioned on CloudConvert’s website. At the beginning of the workflow, a ‘Get URLs from Input’ action tries to filter a URL received from the action extension; if a URL isn’t found, the workflow assumes you didn’t run it via the action extension and thus didn’t want to convert a webpage. In that case, the workflow will present the document picker instead, allowing you to pick any file you want from any storage location on your device.

![](https://2672686a4cf38e8c2458-2712e00ea34e3076747650c92426bbb5.ssl.cf1.rackcdn.com/2017-05-25-15-58-42.jpeg)

Filtering URLs at the beginning of the workflow.

It was essential to keep the website and file conversions separate when the workflow starts because websites can only be converted to a subset of formats supported by CloudConvert. So while a webpage from Safari will only show three possible output options (JPG, PNG, and PDF), other files will present a longer menu with more popular choices, with an option to type a file extension manually. You can modify this list of file extensions to include anything you want as long as it matches the supported types described here.

![](https://2672686a4cf38e8c2458-2712e00ea34e3076747650c92426bbb5.ssl.cf1.rackcdn.com/2017-05-25-16-00-16.jpeg)

Different conversion options for files and websites.

Once the workflow has a file (both websites and actual documents are treated as “files” in the API), a name, and extensions for input and output, a call to the CloudConvert API will be made to start a conversion process.

![](https://2672686a4cf38e8c2458-2712e00ea34e3076747650c92426bbb5.ssl.cf1.rackcdn.com/2017-05-25-16-01-28.jpeg)

Starting a conversion process from Workflow.

Starting a process is an intermediary step that authenticates you with CloudConvert and checks whether the conversion you requested is possible. If you passed a conversion that isn’t available – such as converting an MP3 to EPUB – you’ll get an error message from CloudConvert and the workflow will stop. If the conversion can be made, CloudConvert will generate a process URL and move onto the actual POST request to perform the conversion.

The second ‘Get Contents of URL’ action is the one that passes the file to CloudConvert with specific parameters. A variable defines whether the “file” should be a URL or a base64-encoded file selected via the document picker; similarly, variables set in the initial If block provide the file name and extension that CloudConvert needs (amusingly, URLs have a “.website” file extension in the API). The output format is the extension selected from the list at the beginning.

![](https://2672686a4cf38e8c2458-2712e00ea34e3076747650c92426bbb5.ssl.cf1.rackcdn.com/2017-05-25-16-02-45.jpeg)

CloudConvert’s conversion happening in Workflow.

I set this API action so that Workflow can wait while the conversion is occurring in the cloud and visualize the result inline with a Quick Look preview. In addition, the converted file will be saved in your CloudConvert dashboard and you’ll get an email notification with a link to download the converted file. This system ensures that files large and small can be passed by Workflow to CloudConvert and previewed inside the app after a conversion has been successful.

At the end, you can choose to share the converted file from the Quick Look preview itself or from the subsequent ‘Open In…’ menu.

![](https://2672686a4cf38e8c2458-2712e00ea34e3076747650c92426bbb5.ssl.cf1.rackcdn.com/2017-05-25-16-07-36.jpeg)

From PDF to EPUB with CloudConvert in Workflow.

You can also customize the workflow if you don’t want to wait with the app open while the conversion is processing. To do so, delete the `wait` and `download` parameters from the action, delete the ‘Quick Look’ and ‘Open In…’ actions, and the workflow will simply send a file to CloudConvert. You’ll receive an email notification when the conversion is complete.

I tested this workflow with a variety of input files, and it always worked well. I converted .3gp videos from an old Nokia phone and received an .mp4 video file I could play in Workflow and save to the Photos app. I turned a note from [Bear](https://itunes.apple.com/us/app/bear-beautiful-writing-app-for-notes-and-prose/id1016366447?mt=8&uo=4&at=10l6nh&ct=ms_weekly) into a PDF and then converted the document to EPUB, which I sent to iBooks. The workflow successfully converted Numbers spreadsheets to JPEGs, .mp3 episodes from AppStories to .aac, and a .mov file of our concept video back to .mp4 – all through the CloudConvert API.

### Bonus: Compress PDFs

In addition to converting files between formats, the CloudConvert API supports other modes, some of which I plan to explore in future issues of MacStories Weekly. However, one mode in particular stood out to me as it relates to another common request from Club members: compressing PDFs to reduce their size.

![](https://2672686a4cf38e8c2458-2712e00ea34e3076747650c92426bbb5.ssl.cf1.rackcdn.com/2017-05-25-16-19-08.jpeg)

A compressed PDF returned by CloudConvert.

As a bonus for this week’s Workflow Corner, I created a separate workflow to upload a PDF to CloudConvert and receive a compressed version that can be saved elsewhere. The workflow is based on the main one detailed above: your CloudConvert API key is fetched from a text file, and you’ll have to choose a PDF file from the iCloud Drive document picker. The API calls are mostly the same, except that this workflow uses `mode=compress` to tell CloudConvert to optimize a PDF. As with the other workflow, you’ll be presented with a Quick Look preview after the conversion has finished, so you can hit the Share icon to copy the compressed PDF in other apps.

In my tests, CloudConvert successfully compressed PDFs up to 20%, but I haven’t been able to test with documents containing lots of graphics or spanning thousands of pages. You may be able to get even better results with heavier documents.

***

I’m aware of native iOS apps that can convert multiple file types (including [CloudConvert’s own client](https://itunes.apple.com/us/app/cloudconvert/id842077384?mt=8&uo=4&at=10l6nh&ct=ms_weekly)), but I wanted to create a system that supported automation and the service’s API. CloudConvert is a powerful service that abstracts much of the complexity (and computing time) involved with converting and encoding files to different formats. If you have to deal with file conversions on iOS regularly, I strongly recommend Workflow and CloudConvert to save precious time.

You can get the workflows here:

-   [CloudConvert](https://workflow.is/workflows/0d5b588479d143f383b6e98dcdb33afb)
-   [CloudConvert Compress PDFs](https://workflow.is/workflows/1e555f2b16cb4acaa43b27fd7fc88dba)

[Submit a Workflow Request](https://docs.google.com/forms/d/1_kFRDPvqOrYBuAizSullJ35marcuvg43kndJ9z8LOak/viewform?c=0&w=1 "Submit a Workflow Request")

[Submit a Shortcut Request](https://docs.google.com/forms/d/e/1FAIpQLSeViYJRP69lNKgbmNWqxY1iEnz851gLE375swzC12Qarm-RxA/viewform?usp=sf_link)
***

==**9375**== Words

- **[Automating File Conversions with CloudConvert](https://club.macstories.net/posts/automating-file-conversions-with-cloudconvert)**