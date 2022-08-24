# "The Content Graph engine - Workflow Help"

*23-08-2022 22:31* 

> How workflows work
How workflows work

![](https://help.apple.com/workflow/en.lproj/GlobalArt/AppIconDefault_Workflow.png)

## The Content Graph engine

Much of the magic of Workflow comes from its *Content Graph engine*, which intelligently converts data from iOS features and apps into workflow actions on the fly. When an action expects one type of content and you pass it another type of content, the Content Graph automatically converts that content to the appropriate type.

This smart data conversion lets Workflow integrate apps and services. The following example contains a Get Upcoming Events action followed by a Show Directions action.

![Example workflow showing actions that rely on content detection](https://help.apple.com/workflow/en.lproj/Art/S0023_DirectionsToNextEvent.png)

The first action outputs a Calendar event, which can include scheduling data as well as location data. Because the second action requires location data as input, the Content Graph extracts only the Maps data from the Calendar event, to produce driving directions.

The Content Graph also allows advanced, multistep content detection. This lets Workflow integrate with apps and services that seem unrelated, such as Music and Instagram. For example, you can create a workflow that contains a Get Current Song action followed by a Post on Instagram action. When run, this series of actions automatically extracts the album artwork from the song that’s currently playing and posts the album artwork to Instagram.

![Example of a workflow with complex content detection integrating unrelated apps](https://help.apple.com/workflow/en.lproj/Art/S0006_HowWork05.png)

With the Content Graph, you rarely have to consider whether you’re passing the right type of content from one action to another. Workflow assumes what you want to accomplish, and determines how to get there.

[Previous](https://help.apple.com/workflow/#/apd47913ad71) [Next](https://help.apple.com/workflow/#/apd2d07e340d)

© 2018 Apple Inc. All rights reserved.
***

==**1551**== Words

- **[The Content Graph engine - Workflow Help](https://help.apple.com/workflow/#/apda4856024a)**