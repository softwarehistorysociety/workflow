# "Desktop Cleanup"

*23-08-2022 23:02* 

> Get help and suggestions for your iOS shortcuts and productivity apps.
Get help and suggestions for your iOS shortcuts and productivity apps.

**Question:** Hi, could you highlight some of the lightweight stuff Hazel can help with that could be useful for time-saving? Like keeping a clean desktop, unzip and delete zip-files etc. What are some of the best hacks that could suit a lot of people? (Joakim)

[Hazel](https://www.noodlesoft.com/), by Noodlesoft, is a versatile rule-based utility for automating folder and file actions on the Mac. Here are some examples.

To clean up your desktop each day, first select, or add, the Desktop folder in the left pane of Hazel. To add a rule, select the ‘+’ button and then set up the conditions you want to match and the action you want Hazel to take.

In the screenshot below, I have set up a rule that checks the date that a file was added to the desktop and moves it if the file was added before the current date. Of course the beauty of Hazel is that you can adjust each of the parameters I set to suit your specific needs.

[![](https://gallery.mailchimp.com/9f4b80a35728f7271fe3ea6ff/images/5389d7d8-b748-4182-b38c-95e569f5cffa.png)](https://bddf794624247cea6a0b-b4761d2ba0154d0278c36dbf2b3c114d.ssl.cf1.rackcdn.com/screenshot-2016-03-09-16-26-061457562398902.png)

### Unzip and Delete

I use two actions for to unzip and delete files. The first unarchives ZIP and other archive file formats in my Downloads folder and moves the unarchived files to the Documents folder. The second moves archive files older than one month to the Trash.

[![](https://gallery.mailchimp.com/9f4b80a35728f7271fe3ea6ff/images/678abdbf-b07a-455e-8981-3cbceccf05d4.png)](https://bddf794624247cea6a0b-b4761d2ba0154d0278c36dbf2b3c114d.ssl.cf1.rackcdn.com/screenshot-2016-03-09-14-16-251457563271369.png)

### Consolidate Music, Movies, and Photos

There are several built-in rules to get you started with Hazel. One set that is nice are rules that move music files to the Music folder, movie files to the Movies folder, and images to the Photos folder. The rules below show rules for moving music and images.

[![](https://gallery.mailchimp.com/9f4b80a35728f7271fe3ea6ff/images/db8a1b17-15e3-4409-906d-52f5d50795d4.png)](https://bddf794624247cea6a0b-b4761d2ba0154d0278c36dbf2b3c114d.ssl.cf1.rackcdn.com/screenshot-2016-03-09-14-16-251457554948909.png)

### Take out the Trash

Another nice feature of Hazel is the Trash pane that lets you set a maximum trash can size, duration for holding files, and clean up after apps that scatter files across your Mac’s file system and are not normally deleted when you uninstall an app. This is particularly useful with laptops that have limited storage.

[![](https://gallery.mailchimp.com/9f4b80a35728f7271fe3ea6ff/images/07dd1922-772a-4705-94e5-0cb205126142.png)](https://bddf794624247cea6a0b-b4761d2ba0154d0278c36dbf2b3c114d.ssl.cf1.rackcdn.com/screenshot-2016-03-09-13-47-391457554422730.png)

**Question:** I’d like to send copied URLs to Instapaper via the Workflow Today widget, but while preserving the title of a page. The workflows I’ve tried so far (including the one you provided in MacStories Weekly Issue 20) don’t grab a page’s title, and anything added to Instapaper this way has the URL as a title instead. Not even re-downloading an article in Instapaper (via long-tap) fixes this. (Jerome Dahdah, [@parasight](https://twitter.com/parasight))

This has been fixed in the latest release of Workflow, version 1.4.4. URLs you send to Instapaper will now automatically grab the correct title from the original webpage, so you’ll have proper article titles in your Instapaper queue.

**Question:** I would like to use Spark to email cleaned links (Expand URL action). It looks like Spark has x-callback-url support, but I haven’t made it work yet. Also, if you know of any other Spark and Workflow uses that would be great. (Toby)

This can be done by using the [Spark URL scheme](https://helpspot.readdle.com/spark/index.php?pg=kb.page&id=791) and Workflow’s Open URL action. We can have a URL-encoded subject field in the Spark URL scheme (you could switch this to a variable of your choosing, or use a webpage’s title as subject – provided you always URL-encode this text) and use the Input variable to pass a cleaned link as body text. You can even set a recipient for the new message that will open in Spark’s composer.

![](https://gallery.mailchimp.com/9f4b80a35728f7271fe3ea6ff/images/ee1d1574-5694-4af3-ab9c-eaaa9df977e4.jpg)

I created a workflow that gets a link from your clipboard, fetches its name from the web using the Get Name action, and then asks you to pick a contact to send the link to. If the contact has multiple email addresses (extracted with Select Contact + Get Details of Contact), you’ll be asked to pick one, which will be used in the composer.

You can download the workflow [here](https://workflow.is/workflows/b8d93daa32af41c48de332e4e298ab3c).

**Question:** I do the social media for the small consignment store that I work for. Once a week, I go around and take a bunch of photos of the most interesting items in the store and post them to Instagram with the caption:

> `Lot: <lot number of item> <Description of item> Reserve: <reserve price of item>`

I’ve set up IFTTT to upload these photos to a new Facebook album each week, as well as post these photos to a Twitter account.

My only problem with this is typing the caption each time can be a little fiddly; I keep the basic template saved in Copied (which I access from the Today View Widget) but moving the insertion point on iOS can be a pain, and I’d prefer to use the iOS Camera app instead of the one built into Instagram (as I prefer to have the grid view overlaid over my camera to better line up my photos), but then I’d have to switch back and forth between Instagram and the camera app.

Is there a way I can run a Workflow from the share sheet once I take a photo, get it to prompt me for the 3 variables for the caption and throw me over to Instagram to post the photo? (Luke Bennett, [@luke\_bennett](https://twitter.com/luke_bennett))

Yes, with one minor caveat: you’ll have to paste the caption text manually into the Caption field of Instagram because setting the caption beforehand in Workflow doesn’t seem to be working right now.

With the workflow I put together, you’ll be able to share a photo from the Photos app with the share sheet. The workflow will ask you to enter three captions – the lot, description, and the reserve field. These three separate captions will be joined in one single caption by a Text caption, and the final text will be copied to the clipboard. Then, the workflow will send the selected picture to Instagram. After confirming the photo and applying effects, paste text in the Caption field, and you should be good to go.

You can download the workflow [here](https://workflow.is/workflows/422ed78b31b844a18b835ee1b4b62a2e).

## Top Workflows

I’m often asked by MacStories readers and Club MacStories members to share the workflows I use on a daily basis. While I have dozens of workflows in Workflow (I still don’t like saying this, by the way), there are some I consider my “top” ones. Here’s a list with links to download them.

[Combine Screenshots](https://workflow.is/workflows/222a4eb3342d4318956c6db5a556761e)

I use this workflow every day to combine screenshots (usually iPhone ones) in one final image I can use in MacStories articles. The workflow can be used as an action extension from the Photos app, or you can run it inside Workflow and pick the images you want to combine manually.

[Combine Frames](https://workflow.is/workflows/484ac75801374b7f835d77335a1bb62a)

Quite possibly, one of the most complex workflows I’ve created. With this one, I can put iPhone and iPad screenshots into Apple’s device frames (so the final result will be pretty and professional). I have [shared the details of how this works](https://www.macstories.net/ios/workflow-1-4-4-brings-more-image-automation-html-to-markdown-conversion/) earlier this week.

[Publish to WordPress](https://workflow.is/workflows/8084ce794c1949f09ccf0be0096a2a21)

This is the workflow I use every time I publish a post on MacStories from my iPhone or iPad. From Drafts, Editorial, or 1Writer (the workflow works with anything as long as the post’s title is copied to the clipboard first), I can share Markdown text with the workflow, which will ask me to confirm the post’s title, pick categories and tags, and choose if I want to have a normal post or a linked one. This is made specifically for our custom WordPress features at MacStories, but you can modify it to your needs. Here’s the [workflow I use in Editorial](http://www.editorial-workflows.com/workflow/5781669487312896/TuqvFrI9RHg) to send text to it.

[Resize Safari Image](https://workflow.is/workflows/38f272dc0d0e4cd2918741dbf50ff373)

The featured articles displayed at the top of MacStories require a smaller version of the “hero image”, usually around 640-pixel wide. Because I don’t want to save this image manually every time, I use this workflow to select an image from a post on the web, resize it, upload it to our CDN, and open it in a new tab to confirm it’s looking good.

[Markdown Selection](https://workflow.is/workflows/5fd67ead36cf4f219ce193b9f1851532)

When I create linked posts on MacStories, I want to keep the formatting of the original source intact. Using the copy & paste menu in Safari doesn’t copy as rich text, so I use this workflow to extract the selection on a webpage and convert it to Markdown, copying it to the clipboard.

[Submit a Shortcut Request](https://docs.google.com/forms/d/e/1FAIpQLSeViYJRP69lNKgbmNWqxY1iEnz851gLE375swzC12Qarm-RxA/viewform?usp=sf_link)
***

==**7628**== Words

- **[Desktop Cleanup](https://club.macstories.net/posts/desktop-cleanup)**