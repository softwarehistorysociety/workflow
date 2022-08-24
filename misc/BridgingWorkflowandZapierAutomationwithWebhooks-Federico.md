# "Bridging Workflow and Zapier Automation with Webhooks"

*23-08-2022 23:02* 

> Get help and suggestions for your iOS shortcuts and productivity apps.
Get help and suggestions for your iOS shortcuts and productivity apps.

## [Bridging Workflow and Zapier Automation with Webhooks](https://club.macstories.net/posts/bridging-workflow-and-zapier-automation-with-webhooks)

I’ve [talked](https://www.relay.fm/connected) before about how I like to be woken up in the morning by my girlfriend with a good cup of espresso. We’re on two slightly different schedules: I usually go to sleep a couple of hours after her, and she tends to wake up considerably earlier than I do. And because she wants to make sure that I get at least 7 hours of sleep every night, we needed a system that could let her know when to wake me up based on when I went to sleep.

(I know, I’m incredibly lucky to be with someone who puts up with me and my weird obsession to avoid the sound of alarm clocks.)

For almost a year now, I’ve been using a workflow that generates a timestamp and sends it as an email to Silvia. The workflow creates the timestamp by reformatting a date variable: it fetches the current date, then uses ‘Format Date’ to extract a time string to use in the ‘Send Email’ action. It’s all very basic, but it gets the job done and Silvia likes that she can look at her notifications after waking up and see when I stopped reading or playing videogames and went to sleep.

[![](https://gallery.mailchimp.com/9f4b80a35728f7271fe3ea6ff/images/d0e5bfa5-f402-4236-ac04-8748eb7534d9.jpg)](https://2672686a4cf38e8c2458-2712e00ea34e3076747650c92426bbb5.ssl.cf1.rackcdn.com/2017-01-26-16-29-19.jpeg)

However, I also wanted a way to archive this sleep data (besides what is automatically captured by [AutoSleep](https://itunes.apple.com/us/app/autosleep.-track-sleep-from/id1164801111?mt=8&uo=4&at=10l6nh&ct=ms_weekly) and Health) to visualize my habits and trends over time. I knew I wanted to involve Zapier and Google Sheets in this process, but I wasn’t sure how to send data from Workflow to Zapier without having to dig too deep into the Zapier API.

After some research, I realized that I could use Zapier’s own webhooks to make Workflow communicate with it and pass text data from the iOS app to the web service. The result is a bridge between two different kinds of automation that opens up amazing possibilities for mixed workflows to combine iOS and the web.

First, a clarification. [Zapier’s support for webhooks](https://zapier.com/zapbook/webhook/) allows you to **POST** data to a specific URL or **catch** data to trigger actions on Zapier. In our case, we’re going to use the second option: we want to be able to send data *from* Workflow to Zapier using a web request; that data will then be used as a trigger for other actions on Zapier. Effectively, instead of waiting for a condition to be met on a web service to trigger a zap, we’ll make Workflow activate one by POSTing data to a webhook manually (for more on web requests and APIs in Workflow, [read my previous coverage here](https://www.macstories.net/ios/workflow-update-brings-ability-to-interact-with-any-web-api/)).

![](https://2672686a4cf38e8c2458-2712e00ea34e3076747650c92426bbb5.ssl.cf1.rackcdn.com/2017-01-26-16-24-08.jpeg)

Setting up a catch webhook in Zapier.

Setting up a webhook that listens for data on Zapier is fairly straightforward. Select the ‘Webhooks by Zapier’ action as a trigger, then choose ‘Catch Hook’; this will let Zapier wait for a POST or GET request to a specified URL before triggering something else. At the end of the setup process, Zapier will provide you with a URL for the webhook; copy this URL – you’ll have to paste it in Workflow later.

![](https://2672686a4cf38e8c2458-2712e00ea34e3076747650c92426bbb5.ssl.cf1.rackcdn.com/2017-01-26-16-24-55.jpeg)

Copy the webhook’s URL to paste it in Workflow.

Triggering a webhook (and therefore a zap) from Workflow only requires two actions: ‘URL’, to define the webhook URL provided by Zapier, and ‘Get Contents of URL’, to perform a web request that will trigger the webhook.

![](https://2672686a4cf38e8c2458-2712e00ea34e3076747650c92426bbb5.ssl.cf1.rackcdn.com/2017-01-26-16-27-47.jpeg)

Calling the webhook in Workflow with a POST request.

For my sleep log, I needed to pass data from Workflow to Zapier, which meant I had to build a POST request to send data to the webhook. To do this, set the Method of ‘Get Contents of URL’ to POST, then assemble a JSON request body that includes the variables you want Zapier to see. If you’re familiar with web APIs and dictionaries in Workflow, this should be relatively easy to grasp: each key contains a value, which in our case are the day and the time when I went to sleep and ran the workflow.

You can create a request body that is a dictionary or, alternatively, add individual Text keys that contain variables or arbitrary strings of text.

![](https://2672686a4cf38e8c2458-2712e00ea34e3076747650c92426bbb5.ssl.cf1.rackcdn.com/2017-01-26-16-28-26.jpeg)

The JSON request in Workflow.

The first time you set up a ‘catch’ webhook on Zapier, you’ll be asked to test it by waiting for data to be passed to it. To perform this configuration step, copy the webhook URL from Zapier, prepare the Workflow actions, and run the workflow with some test data; you just need Zapier to see that you can talk to the webhook, and you can finish setting up the data in Workflow later.

![](https://2672686a4cf38e8c2458-2712e00ea34e3076747650c92426bbb5.ssl.cf1.rackcdn.com/2017-01-26-16-31-06.jpeg)

A successful webhook test in Zapier.

Once the test on Zapier is successful, you’ll get a confirmation screen where you can inspect the data sent to the webhook. As you can see in the screenshot above, Zapier will show you the key (with a bold font) and the value associated with it. If you have multiple keys, you’ll also end up with multiple values and, therefore, multiple fields to use in other Zapier actions.

[![](https://gallery.mailchimp.com/9f4b80a35728f7271fe3ea6ff/images/a409118c-3ff2-49e6-b119-66022423f3fe.jpg)](https://2672686a4cf38e8c2458-2712e00ea34e3076747650c92426bbb5.ssl.cf1.rackcdn.com/2017-01-26-16-32-23.jpeg)

At this point, the zap has been triggered and the webhook has fetched data that Zapier interprets as fields. Now, you can add as many steps as you want and use variables sent by Workflow to fill actions for web apps in Zapier. For my sleep log, I used two variables from Workflow to append a new row to an existing document in Google Sheets (pictured below), but you can use any other action supported by Zapier to do whatever you want with the fields parsed by the webhook.

![](https://2672686a4cf38e8c2458-2712e00ea34e3076747650c92426bbb5.ssl.cf1.rackcdn.com/2017-01-26-16-33-24.jpeg)

Sleep data archived by Zapier in Google Sheets.

By combining Workflow and Zapier with this system, you’ll unlock a deeper level of automation – a way to mix and match iOS workflows and apps with Zapier’s multiple chained actions and web API interactions. Once a webhook is set up, calling it from Workflow will only take a second and you won’t have to go through any other test screen, making it an ideal solution to quickly send bits of data off to Zapier before finishing with the local workflow on iOS.

The possibilities created by the combination of Zapier and Workflow are virtually endless; if you’re both into iOS automation *and* web services, there’s a chance you’ll consider using this method for a variety of workflows going forward. To get started and understand the basics of Zapier actions triggered by Workflow, you can get my Sleep Log workflow [here](https://workflow.is/workflows/a2c4a16e68b546aaa007f80c81b0df9d).

[Submit a Shortcut Request](https://docs.google.com/forms/d/e/1FAIpQLSeViYJRP69lNKgbmNWqxY1iEnz851gLE375swzC12Qarm-RxA/viewform?usp=sf_link)
***

==**6031**== Words

- **[Bridging Workflow and Zapier Automation with Webhooks](https://club.macstories.net/posts/bridging-workflow-and-zapier-automation-with-webhooks)**