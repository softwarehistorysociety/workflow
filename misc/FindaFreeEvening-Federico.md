# "Find a Free Evening"

*23-08-2022 23:02* 

> Get help and suggestions for your iOS shortcuts and productivity apps.
Get help and suggestions for your iOS shortcuts and productivity apps.

## [Find a Free Evening](https://club.macstories.net/posts/find-a-free-evening)

I was inspired by a question sent by member Steven, who asked us for a way to easily find a free evening in his calendar to go out with friends after work:

**Question:** I often find myself trying to schedule post-work events with friends and colleagues. The first inevitable step is to send over a list of dates on which I have no appointments scheduled after [COB](https://en.wikipedia.org/wiki/End_of_day) (6 PM in my case). It would be incredible if I could select two dates and have a list of dates with free evenings exported out. (Steven Tartick, [@Tartick](http://twitter.com/Tartick))

To my knowledge, the Workflow team had already put together an excellent workflow to share your availability for an entire single day. The workflow, which [can be found on the Workflow Gallery](https://workflow.is/workflows/703443a0652c4c6596d541b218bff567), is incredibly clever as it takes advantage of start dates and variables to find free slots between events in your calendar.

However, as I kept thinking about this request, I realized that I wanted to create something *slightly* different – a workflow optimized for finding free evenings across multiple days at once. This has been a problem for me as well – to be able to find some free time to relax after work – and I figured it’d be fun to solve it with a workflow.

Before I dive into the details of this automation, here’s what the final result looks like:

[![](https://gallery.mailchimp.com/9f4b80a35728f7271fe3ea6ff/images/b2af05de-dc6d-4197-8491-919a3bdc1e73.jpeg)](https://2672686a4cf38e8c2458-2712e00ea34e3076747650c92426bbb5.ssl.cf1.rackcdn.com/2017-04-06-15-37-20.jpeg)

Essentially, what we’re putting together is a workflow that looks into a calendar of your choice for multiple days in a row, and that can find free slots of times within a specific time range – your idea of “evening” when you typically go out and relax.

There’s some setup we need to do. At the beginning of the workflow, you’ll see three ‘Text’ actions. The first one features the plain text name of the calendar you’ll want to parse for events. This has to be the **exact name** of a calendar that is already configured natively on your iOS device, otherwise the workflow will fail. To find a complete list of your calendar names, you can go into Apple’s Calendar app and tap on the ‘Calendars’ button to open a popup with every calendar you’ve configured.

![](https://2672686a4cf38e8c2458-2712e00ea34e3076747650c92426bbb5.ssl.cf1.rackcdn.com/2017-04-06-15-38-23.jpeg)

First, configure your calendar name and time range to indicate when an “evening” starts and ends.

The other two ‘Text’ actions specify the time range you want Workflow to consider. For this workflow, I used “6 PM” and “11 PM”, but you can change that to other times as long as the second action doesn’t go beyond midnight (rolling into the following day). The idea is to isolate a block of time that represents an evening when you’re available to go out. If you’re someone who works night shifts, you can change these to afternoon times.

The main functionality of the workflow starts with an ‘Ask for Input’ action that asks you to enter a number for the days you want to pick. This wouldn’t be necessary if Workflow had a native month picker that let you select multiple days at once, but, unfortunately, such a feature hasn’t been added to the app. The number of days you choose is used as the repetition value in a ‘Repeat’ action. Each pass of the repeat block brings up another ‘Ask for Input’ action, but this time set to ‘Date’ as the input type, which will show you a standard date picker (the scrolling wheel) where you can select a day to parse for events. If you tell the workflow you want to analyze 4 days in a row, you’ll be presented with the date picker 4 times.

![](https://2672686a4cf38e8c2458-2712e00ea34e3076747650c92426bbb5.ssl.cf1.rackcdn.com/2017-04-06-15-48-47.jpeg)

Picking the number of days and dates with different ‘Ask for Input’ actions.

At this point, the workflow is inside a repeat loop and it knows which day has been picked. To create a single list for multiple days, we need to append lines of text to the same variable using the ‘Add to Variable’ action. Thus, before searching for events, the workflow creates a header for the day being analyzed that will act as a separator in the final text message. To make this more readable, I used a ‘Format Date’ action with a custom format string.

![](https://2672686a4cf38e8c2458-2712e00ea34e3076747650c92426bbb5.ssl.cf1.rackcdn.com/2017-04-06-15-46-30.jpeg)

Formatting dates in Workflow.

Now, it’s time for the repeat loop to look into your calendar and find events for the day being processed. For this, we need to use the ‘Find Calendar Events Where’ filter action, which will find all events that belong to the calendar you chose and that have a start date within the time range you entered. These events are sorted by start date (oldest first) and they’re counted with a subsequent ‘Count’ action.

The reason for counting events is simple: if the count equals 0, it means Workflow hasn’t found any events for Day `x` between, say, 6 PM and 11 PM. That means you have no scheduled appointments and you’re free to go out. If the count equals 0, a line that says “Free all evening” is appended to the aforementioned variable, the repeat loop is over, and the workflow can start processing the other day you’ve picked.

If the count isn’t 0, though, it means Workflow has found events within the selected time range, and it’s time to parse them. This is where I had to make some assumptions to simplify the workflow as much as possible. If events are found, the workflow calculates the following free times:

-   Free time between your ideal start time and the start date of the *first* event;
-   Free time between the end time of the *last* event and your ideal end time.

When I was creating the workflow, I assumed that, if you’re planning to go out, you don’t want to know about the 20 minutes you have free between one event and another in the same evening. You want to know when you have good chunks of time either before a late evening event, or after the last appointment of the day has passed and you can go out and meet with friends. It made more sense in my mind to find the time before the first event and after the last event ends.

Workflow has built-in support for the concept of “first” and “last” in a group of items. To find the first event among multiple ones, we just need to get the Magic Variable for the ‘Find Events’ action (remember, events were sorted by start date) and combine it with ‘Get Item from List: First Item’. To calculate the time between our going-out time and the event’s start time, we can use ‘Get Time Between Dates’ to extract the difference in minutes between the two points in time.

If the result of this calculation is 0, it means the event starts at the same time we’d like to go out, which means we’re busy. If the value is greater than 0, however, it means we have *some* free time between 6 PM (or whatever you picked) and until the first event starts. This information is appended to the ‘Free Times’ variable. A nice touch: if the value in minutes is over 90, the Workflow converts it to hours. It doesn’t make sense to tell someone “I have 180 minutes free”, so the workflow takes care of that as well.

The block of actions to find time between the last event’s end time and 11 PM is roughly the same as above. The only difference is that Workflow outputs a negative number if the event’s end time is before our preferred evening end time; I had to remove the minus sign with a simple ‘Replace Text’ action.

At the end of the repeat loop, two empty lines of text are added to the ‘Free Times’ variable as separators between days. Finally, a ‘Combine Text’ action joins every line of text from the Free Times variable, resulting in a complete text message from every day that was evaluated by the workflow to find free time slots in the evening. This text message is then passed to extensions so you can share it with friends using your favorite apps.

I had fun putting this together: Workflow abstracts much of the complexity traditionally involved with date calculations, and Magic Variables have been essential in helping me fetch data from actions inside the repeat loop as well as convert data between formats. This is a complex workflow, but it would have been much longer and more difficult to understand before [Workflow 1.7 and Magic Variables](https://www.macstories.net/ios/workflow-1-7-introduces-magic-variables-for-easier-more-powerful-visual-automation/).

If you’ve also been struggling to communicate your free times with friends, and if you would like a way to automate your calendar and see when you don’t have appointments in the evening, you should give this a try.

You can [get the workflow here](https://workflow.is/workflows/3581ddde8eca4bb3a7d71eb981b14769).

[Submit a Shortcut Request](https://docs.google.com/forms/d/e/1FAIpQLSeViYJRP69lNKgbmNWqxY1iEnz851gLE375swzC12Qarm-RxA/viewform?usp=sf_link)
***

==**8132**== Words

- **[Find a Free Evening](https://club.macstories.net/posts/find-a-free-evening)**