# "Custom formats - Workflow Help"

*23-08-2022 22:31* 

> Understanding date and time formatting
Understanding date and time formatting

![](https://help.apple.com/workflow/en.lproj/GlobalArt/AppIconDefault_Workflow.png)

## Custom formats

Despite all of the predefined date formatting options, you may want to craft a format specific to your needs. You can create a custom date format by choosing Custom from the Format Date options. An additional Format String text field is displayed, allowing you to enter a format string that consists of a pattern of special characters.

*Note:* For custom format strings, Workflow uses the patterns defined by the Unicode Technical Standard #35. For more information, see [Date Format Patterns](https://unicode.org/reports/tr35/tr35-dates.html#Date_Format_Patterns).

![Format Date action with a custom Format String, in the workflow composer](https://help.apple.com/workflow/en.lproj/Art/S0152_DateFormatCustom.png)

The following table lists a summary of example format strings and their results.

| 
Pattern

 | 

Result

 |
| --- | --- |
| 

`yyyy.MM.dd G 'at' HH:mm:ss zzz`

 | 

`1996.07.10 AD at 15:08:56 PDT`

 |
| 

`EEE, MMM d, ''yy`

 | 

`Wed, July 10, '96`

 |
| 

`h:mm a`

 | 

`12:08 PM`

 |
| 

`hh 'o''clock' a, zzzz`

 | 

`12 o'clock PM, Pacific Daylight Time`

 |
| 

`K:mm a, z`

 | 

`0:00 PM, PST`

 |

**Tip:** Custom patterns can include special characters like `.` or `/` in between the date characters. You can also include custom text in the custom patterns by placing single quotes around the string (see the word `'at'` in the first table entry, above).

You can see the complete set of custom date format characters in the Date Field Symbol Table included in [this workflow](https://workflow.is/workflows/90986961b95b4f7c8c42ade22ff182be), or you can view the full [Unicode #35 standard](http://unicode.org/reports/tr35/tr35-dates.html#Date_Format_Patterns).

[Previous](https://help.apple.com/workflow/#/apdfd459e13d) [Next](https://help.apple.com/workflow/#/apd8efa49a70)

© 2018 Apple Inc. All rights reserved.
***

==**1335**== Words

- **[Custom formats - Workflow Help](https://help.apple.com/workflow/#/apd8d9b19184)**