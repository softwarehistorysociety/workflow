# "Handling dictionaries using the Get Dictionary Value action"

*23-08-2022 22:31* 

> Work with JSON
Work with JSON

![](https://help.apple.com/workflow/en.lproj/GlobalArt/AppIconDefault_Workflow.png)

To get the value for a particular key in a dictionary, you can use the Get Dictionary Value action and specify the name of the key. To get the daily forecast, add the Get Dictionary Value action and set it to `daily`.

![Get Dictionary Value action in the workflow composer with the key set to daily](https://help.apple.com/workflow/en.lproj/Art/S0251_DarkSkyExample06.png)

If you want the weather summary, you can use the Get Dictionary Value action again with `summary`.

![Get Dictionary Value action in the workflow composer with the key set to summary](https://help.apple.com/workflow/en.lproj/Art/S0252_DarkSkyExample07.png)

The detailed forecast for each day is stored within `daily` as a dictionary called `data`.

![Get Dictionary Value action in the workflow composer with the key set to data](https://help.apple.com/workflow/en.lproj/Art/S0253_DarkSkyExample08.png)

Notice that the `data` dictionary is actually a list of dictionaries, represented at the start by the left bracket `[` in JSON. In the above image, a list of eight items (identified by the page dots above the Actions and Workflow buttons) is output from the Get Dictionary Value action. This represents the forecast data for each of the days requested from the API, which returns today and the next seven days to become a list of eight dictionaries of data.

For information on working with multiple items in a dictionary, see [Handling lists using the Repeat with Each action](https://help.apple.com/workflow/#/apd9ba41d21b).

[Previous](https://help.apple.com/workflow/#/apdde2dfe749) [Next](https://help.apple.com/workflow/#/apd9ba41d21b)

© 2018 Apple Inc. All rights reserved.
***

==**1085**== Words

- **[Handling dictionaries using the Get Dictionary Value action - Workflow Help](https://help.apple.com/workflow/#/apdf01294032)**