# "Choose from Menu - Workflow Help"

*23-08-2022 22:31* 

> Advanced workflows
Advanced workflows

![](https://help.apple.com/workflow/en.lproj/GlobalArt/AppIconDefault_Workflow.png)

## Choose from Menu

The Choose from Menu action gives you the ability to decide what a workflow should do when it’s run. You can pick from a predefined list of options to have each option run a different series of actions. This allows workflows to maintain their rigid structure but remain flexible (depending on the realtime context).

Think of the Choose from Menu action as creating a fork in the road of your workflow—the workflow is sent in a different direction depending on the chosen option, resulting in a unique behavior.

![Choose from menu screen](https://help.apple.com/workflow/en.lproj/Art/S0216_ChooseFromMenuiPad.png)

For each menu option, the Choose From Menu action provides markers that represent the different pathways the workflow may take at that point. Place the actions that you want the workflow to run through when the corresponding option is chosen below each marker.

When the workflow runs, you are prompted to choose an option from the menu.

![Choose from Menu upper screen](https://help.apple.com/workflow/en.lproj/Art/S0151_ChooseFromMenuTop.png)

The first action under the marker receives the input that was passed into Choose from Menu (not the name of the option). The output of the last action under that marker becomes the output of the Choose from Menu action as a whole.

*Note:* Although you may notice a line in the center of the screen that connects each action in Choose from Menu, the workflow actually skips the actions for the options you didn’t select. Choose from Menu only lets you pick one option, and that selection determines what actions are used.

![Choose from Menu lower screen](https://help.apple.com/workflow/en.lproj/Art/S0150_ChooseFromMenuBottom.png)

**Tip:** You can also use [variables](https://help.apple.com/workflow/#/apdd02c2780c) in the names of each menu option to make them dynamic. However, the resulting sequence of actions must still be predefined when building the workflow.

## Add a Choose from Menu action to a workflow

In the workflow composer, do one following:

-   *Add a Choose from Menu action on iPhone:* Tap Actions (the magic wand), drag the Choose from Menu action (from the Scripting category in the Actions list) to the right, then position the action in the workflow.
    
-   *Add a Choose from Menu action on iPad:* Drag the Choose from Menu action (from the Scripting category in the Actions list) into position in the workflow.
    

[Previous](https://help.apple.com/workflow/#/apd142384946) [Next](https://help.apple.com/workflow/#/apd83dcd1b51)

© 2018 Apple Inc. All rights reserved.
***

==**2128**== Words

- **[Choose from Menu - Workflow Help](https://help.apple.com/workflow/#/apdd7bf369da)**