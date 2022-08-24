# "Handling timestamps using Format Date"

*23-08-2022 22:31* 

> Further exploration with APIs
Further exploration with APIs

![](https://help.apple.com/workflow/en.lproj/GlobalArt/AppIconDefault_Workflow.png)

You may notice that time and date information in some API responses appear as long numbers with many digits. This is because the time is formatted in *UNIX time* (or *Epoch time*), which represents the time as the number of seconds that have elapsed since 00:00:00 UTC, Thursday, January 1, 1970.

UNIX time is used as a standard for all computers as a way to measure time from the same spot, or the start date of Coordinated Universal Time (UTC), and is also considered the birthday of the UNIX operating system. In Workflow, you can convert from the UNIX time format to a more human-readable time format by using the Date, Adjust Date, and Format Date actions.

The Date action is set to 00:00:00 UTC Jan 1, 1970. Add the UNIX Time variable to the UTC date to get the adjusted date. Next, use Format Date to remove the time component (as they are all 00:00:00).

![Workflow with actions to translate UNIX time to a more human-friendly date format.](https://help.apple.com/workflow/en.lproj/Art/S0258_DarkSkyExample13.png)

*Note:* Other APIs might use other time formats such as ISO 8601. For more information, see [Date and time formatting overview](https://help.apple.com/workflow/#/apd71b0ac246).

[Previous](https://help.apple.com/workflow/#/apd891a6c84e) [Next](https://help.apple.com/workflow/#/apd43b69f337)

© 2018 Apple Inc. All rights reserved.
***

==**1112**== Words

- **[Handling timestamps using Format Date - Workflow Help](https://help.apple.com/workflow/#/apdfb33b0e17)**