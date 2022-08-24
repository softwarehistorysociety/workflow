# "Handling lists using the Repeat with Each action"

*23-08-2022 22:31* 

> Work with JSON
Work with JSON

![](https://help.apple.com/workflow/en.lproj/GlobalArt/AppIconDefault_Workflow.png)

This section discusses using the data returned by the Dark Sky API (in the [previous topic](https://help.apple.com/workflow/#/apdf01294032)) to retrieve the average temperature for each day in the forecast using the [Repeat with Each](https://help.apple.com/workflow/#/apdc11deb2c1) action. The Repeat with Each action allows a workflow to act on every item in a list, one after another.

To work with the set of eight days of data, you must pass the output into the Repeat with Each action, then set up actions within each loop to retrieve a single day’s data at a time.

To get the average daily high and low temperatures, create a repeat loop by using a List action with two Repeat Item variables. Tap the first Repeat Item variable, change the content type to Dictionary, then enter the key `temperatureMax` to obtain the maximum temperature of each day. Do the same for the second Repeat Item variable, providing the key `temperatureMin` to obtain the minimum temperature of each day.

Next, use the Calculate Statistics action to average the two new values and use the Round Number action to make the value a nice and readable version of average temperature for the day.

![Calculate Statistics action and Round Number action in the workflow composer](https://help.apple.com/workflow/en.lproj/Art/S0170_Repeat04.png)

To make sure the raw data values are useful once they’re passed out of the repeat loop, extract the day of the week to use in your alert. Using another Repeat Item variable set to the `time` key, you can extract a time value from the API and use the Adjust Date action to calculate the correct date from the time value. Place the variables for the day of the week (extracted from Adjust Date) and average temperature (extracted from Round Number) into a Text action, so that the final output of each loop is a line of text with the newly formatted data.

![Date action, Adjust Date action, and Text action in the workflow composer, with variables applied](https://help.apple.com/workflow/en.lproj/Art/S0171_Repeat05.png)

Once the workflow is run and reaches the Repeat with Each action, it loops through each day’s dictionary of data, performs the calculations, then passes the result into the End Repeat action. After all eight repeats, all of the numbers are grouped together and passed out of the End Repeat action, available to use as input into another action or retrievable as a Repeat Results variable.

Continue to the [next section to learn how to display your custom weather data as an alert](https://help.apple.com/workflow/#/apd9cf19a736).

[Previous](https://help.apple.com/workflow/#/apdf01294032) [Next](https://help.apple.com/workflow/#/apd9cf19a736)

© 2018 Apple Inc. All rights reserved.
***

==**2213**== Words

- **[Handling lists using the Repeat with Each action - Workflow Help](https://help.apple.com/workflow/#/apd9ba41d21b)**