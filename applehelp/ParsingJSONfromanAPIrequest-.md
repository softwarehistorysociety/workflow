# "Parsing JSON from an API request"

*23-08-2022 22:31* 

> Work with JSON
Work with JSON

![](https://help.apple.com/workflow/en.lproj/GlobalArt/AppIconDefault_Workflow.png)

If you look at the [Dark Sky API response](https://help.apple.com/workflow/#/apd58d46713f?sub=apd93e5fad85), you can see that there’s a lot of data stored in JSON. While not easy to read at first, over time you’ll start to recognize the structures in JSON data, as well as how to identify dictionaries, lists, keys, and values. Often, developers include a nicely formatted version of the JSON data that their API will return, so look for that in their documentation. Additionally, it’s helpful to check your work using services like the [online JSON Editor](https://jsoneditoronline.org/).

![An example of JSON data](https://help.apple.com/workflow/en.lproj/Art/S0167_Repeat01.png)

Notice that the top-level object is a dictionary with the keys `latitude`, `longitude`, `timezone`, `currently`, and `minutely`. Some of these keys, such as `latitude` and `timezone`, simply contain a number or text value, but others, such as `daily`, have a dictionary value.

And the `daily` dictionary contains some keys with values that are simple text, such as the `summary`, with `Rain throughout the day`. But others, such as `data`, are lists containing a forecast (represented by a dictionary) for each hour.

![Dictionary containing keys and strings](https://help.apple.com/workflow/en.lproj/Art/S0168_Repeat02.png)

[Previous](https://help.apple.com/workflow/#/apd0f2e057df) [Next](https://help.apple.com/workflow/#/apdf01294032)

© 2018 Apple Inc. All rights reserved.
***

==**1098**== Words

- **[Parsing JSON from an API request - Workflow Help](https://help.apple.com/workflow/#/apdde2dfe749)**