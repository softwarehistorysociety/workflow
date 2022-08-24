# "Adding Filters - Workflow Help"

*23-08-2022 22:31* 

> Use Find and Filter actions
Use Find and Filter actions

![](https://help.apple.com/workflow/en.lproj/GlobalArt/AppIconDefault_Workflow.png)

## Adding Filters

You can add filters to instruct a Find or Filter action on what criteria to use in its search query.

For example, if you add a filter to Find Photos, you can specify “Album” “is” “All Photos.” The first option, “Album,” lets you choose the property of the content to filter against. The second and third options, “is” and “All Photos,” further refine the filter. You can then, for example, set All Photos to a single photo album to retrieve only that album’s photos. Or you can change “is” to “is not” and filter out a particular album, such as Panoramas, from your result.

![Find Photos Where action in workflow composer](https://help.apple.com/workflow/en.lproj/Art/S0159_FindFilterPhotos.png)

You can continue to add additional filters to further isolate the results. When you add multiple filters, the “All of the following are true” or “Any of the following are true” options become available, requiring that every filter criteria be matched or at least one of the filters, respectively.

![Find Reminders Where action showing the “Any of the following are true” options](https://help.apple.com/workflow/en.lproj/Art/S0160_FindFilterReminders.png)

The Find and Filter actions also include parameters to sort and limit your results. The “Sort by” parameter allows you to choose a property to sort the results by (including Random to order randomly). Certain properties, such as Date Taken for photos, also reveal additional parameters (such as setting the Order parameter as Oldest First or Latest First.

The last parameter in the Find and Filter actions, Limit, allows you to cap the number of content items the action retrieves or filters. Once Limit is turned on, another parameter appears, letting you set the maximum number of retrieved items. Additionally, you can tap the Get Items field to set it using a [Magic Variable](https://help.apple.com/workflow/#/apdd2b316022) or an Ask When Run variable, allowing you to alter the limit while the workflow is running.

**Tip:** When working with a large amount of content or broad queries in the Find and Filter actions, a workflow’s performance may be impacted when run from iOS Today View or Apple Watch. In such cases, use a Continue In App action to switch to the Workflow app, or experiment with more specific filters that limit the number of possible results.

## Add a Find or Filter action

1.  Open a workflow, then tap Add Filter.
    
2.  Tap one of the filter’s colored components, then tap an option from the list to customize the filter.
    

[Previous](https://help.apple.com/workflow/#/apd3c845e881) [Next](https://help.apple.com/workflow/#/apd621a1ad7a)

© 2018 Apple Inc. All rights reserved.
***

==**2289**== Words

- **[Adding Filters - Workflow Help](https://help.apple.com/workflow/#/apdbdab3433f)**