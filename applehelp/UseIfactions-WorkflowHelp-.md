# "Use If actions - Workflow Help"

*23-08-2022 22:31* 

> Advanced workflows
Advanced workflows

![](https://help.apple.com/workflow/en.lproj/GlobalArt/AppIconDefault_Workflow.png)

## Use If actions

Use the If action (also known as a *conditional*) to set up a workflow that checks for certain conditions and operates differently depending on which condition is met. If conditionals give you the flexibility to set up different paths that your actions can take depending on conditions that are known only when the workflow runs.

Simply put, the If action lets you express the following in a workflow: *If a condition is true, do this; otherwise, do that*. A different series of actions is run for each result.

You can use the If action to test whether content that’s passed into the action as input meets a certain condition. For example, you could use the If action to verify that a webpage fetched from a previous action contains the word “meatloaf.”

*Note:* If you’re unfamiliar with the concept of inputs and outputs, see [How workflows work](https://help.apple.com/workflow/#/apd1d10ec518).

![Setting up an If action](https://help.apple.com/workflow/en.lproj/Art/S0162_IfLargeiPad.png)

Once placed in your workflow, the If action includes three parts: If, Otherwise, and End If.

Within the If parameters, you can configure the Input and Value parameters. Tap the Input parameter to choose one of the four available conditions:

-   *Equals:* Tests if the input is an exact match to the value you’ve specified, whether text or a number
    
-   *Contains:* Tests if the input (which may be a body of text or a list) contains text you’ve specified at least once
    
-   *Is Greater Than:* Tests if the input is greater than a certain number
    
-   *Is Less Than:* Tests if the input is less than a certain number
    
    ![Selecting Contains from the four available Input conditions](https://help.apple.com/workflow/en.lproj/Art/S0164_IfOptions.png)
    

Greater Than and Less Than apply only when a number is passed as input.

Because the If action has two possible outcomes—the condition is true or the condition is false—you can place actions in two paths. When the workflow runs, a true condition causes the input to be passed to the first action just after If, while a false condition causes the input to be passed into the first action after Otherwise.

![If action placed in two paths](https://help.apple.com/workflow/en.lproj/Art/S0165_IfTrick.png)

The last action to produce output in the If case or Otherwise case passes its content through the End If as output (available to retrieve as an “If Results” Magic Variable). This means that the last action in each path of the If action affects the output of the block as a whole.

## Add an If action to a workflow

In the workflow composer, do one of the following:

-   *Add an If action on iPhone:* Tap Actions (the magic wand), drag the If action (from the Scripting category in the Actions list) to the right, then position the action in the workflow below the action that contains output you want to check with the conditional.
    
-   *Add a If action on iPad:* Drag the If action (from the Scripting category in the Actions list) into the workflow below the action that contains output you want to check with the conditional.
    

**Tip:** You can place If actions within each other to create a more advanced tree of decisions in your workflow.

[Previous](https://help.apple.com/workflow/#/apdd7bf369da) [Next](https://help.apple.com/workflow/#/apdc11deb2c1)

© 2018 Apple Inc. All rights reserved.
***

==**2872**== Words

- **[Use If actions - Workflow Help](https://help.apple.com/workflow/#/apd83dcd1b51)**