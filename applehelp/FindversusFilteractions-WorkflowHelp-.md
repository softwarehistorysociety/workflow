# "Find versus Filter actions - Workflow Help"

*23-08-2022 22:31* 

> Use Find and Filter actions
Use Find and Filter actions

![](https://help.apple.com/workflow/en.lproj/GlobalArt/AppIconDefault_Workflow.png)

## Find versus Filter actions

Actions with names that begin with “Find” and “Filter” accept the output of another action as input, filter the content, then pass the filtered results as output.

Find actions include Find Photos, Find Reminders, Find Calendar Events, Find Music, Find Health Samples, and Find Contacts. These actions filter photos, reminders, events, and other content passed as input. If nothing is passed into Find actions, however, they retrieve content on their own from their respective apps (similar to Get actions).

Filter actions include Filter Event Attendees, Filter Files, Filter Locations, Filter Articles, and Filter Images. These actions take content as input, narrow the content using filters that you specify, and then pass the matched results as output.

In other words, Find actions can locate and filter existing content on a device, but Filter actions filter only existing content.

![Find Calendar Events Where action and Filter Locations Where action in workflow composer](https://help.apple.com/workflow/en.lproj/Art/S0156_FindFilterLocFilter.png)

**Tip:** To use two Find actions in a row—without causing the second action to filter the output of the first—place a Nothing action in between the two Find actions. That way, “nothing” is passed as input to the second Find action, signaling it to retrieve its own content.

![Two Find Music Where actions in the workflow composer](https://help.apple.com/workflow/en.lproj/Art/S0161_FindFilterTwoAfterAnother.png)

[Previous](https://help.apple.com/workflow/#/apd2dc3575ec) [Next](https://help.apple.com/workflow/#/apdbdab3433f)

© 2018 Apple Inc. All rights reserved.
***

==**1307**== Words

- **[Find versus Filter actions - Workflow Help](https://help.apple.com/workflow/#/apd3c845e881)**