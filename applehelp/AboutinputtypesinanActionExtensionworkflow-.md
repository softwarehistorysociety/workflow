# "About input types in an Action Extension workflow"

*23-08-2022 22:31* 

> Run workflows from other apps
Run workflows from other apps

![](https://help.apple.com/workflow/en.lproj/GlobalArt/AppIconDefault_Workflow.png)

Limiting the input types in an Action Extension workflow helps streamline sharing options in an app, by hiding workflows that aren’t relevant to the app. For example, a workflow that accepts only contacts won’t appear as a sharing extension in the Maps app. (For details about how to limit the input types accepted by an Action Extension workflow, see step 4 of [Enable a workflow to run in other apps](https://help.apple.com/workflow/#/apd163eb9f95?sub=apd22188c0db).)

![Inputs list lets you choose the kind of content available to a workflow when run from another app.](https://help.apple.com/workflow/en.lproj/Art/S0118_Accepts.png)

In an Action Extension workflow, the default setting for input types is Anything, which allows the workflow to accept any type of input. Workflows that accept all input types are available for use in all apps—even apps that can’t produce the input type the workflow requires. This can lead not only to a cluttered list of available workflows, but it can introduce errors into the workflow fails to find the input it needs. Therefore, it’s a good idea to limit the types of input a workflow accepts.

It takes some testing to determine the types of input an app provides. Some apps provide multiple types of input. Photos, for example, provides both still images and video. For other apps, however, the shared content is less obvious.

You can preview the Action Extension input by placing a View Content Graph action at the beginning of your workflow.

See the full list of input types and their definitions in [Understanding Action Extension input types](https://help.apple.com/workflow/#/apd6e3d33040).

*Note:* Action Extension workflows have a limited amount of available memory (RAM). This means that workflows that process large volumes of data may crash when run from another app. If this happens, try this workaround: Place a Continue in App action in your workflow, which opens the Workflow app, where more memory is available.

[Previous](https://help.apple.com/workflow/#/apd163eb9f95) [Next](https://help.apple.com/workflow/#/apdbe2ceb96c)

© 2018 Apple Inc. All rights reserved.
***

==**1812**== Words

- **[About input types in an Action Extension workflow - Workflow Help](https://help.apple.com/workflow/#/apd367de00f4)**