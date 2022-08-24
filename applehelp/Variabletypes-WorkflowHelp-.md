# "Variable types - Workflow Help"

*23-08-2022 22:31* 

> Use variables
Use variables

![](https://help.apple.com/workflow/en.lproj/GlobalArt/AppIconDefault_Workflow.png)

## Variable types

Workflow lets you create variables automatically or manually.

## Magic Variables

Throughout your workflow, each action’s output is automatically available as a *Magic Variable*. This means that unlike manual variables, Magic Variables don’t require you to save the output of an action for later use—simply tap the Magic Variable button (the unlabeled magic wand above the iOS keyboard), and select the output of any previous action to use it as a variable.

![Make Top 25 Playlist workflow screen showing Variables and Magic Variable buttons above the iOS keyboard](https://help.apple.com/workflow/en.lproj/Art/S0261_MagicVariableButton.png)

Using Magic Variables, you can switch to a special view of the workflow composer that shows all of the outputs of the actions in your workflow as selectable variables; a later action can pull an arbitrary output of an earlier action. Magic Variables are visually useful as well, displaying the icon of the action from which they are generated.

Making the variables truly magic, however, is your ability to change the variable type—simply tap a Magic Variable to change its format, and to [specify which of its details to use](https://help.apple.com/workflow/#/apda36b9018b).

In most cases, using Magic Variables simplifies building workflows and is preferable to manually creating variables.

![Select a Magic Variable screen](https://help.apple.com/workflow/en.lproj/Art/S0195_VariablesMagic.png)

## Manual variables

You can add manual variables to a workflow using the Set Variable action or the Add to Variable action. Either of these actions must be placed in the workflow immediately after an action that provides the output you want to store.

*Set Variable* allows you to set a new variable for the first time or overwrite a previously stored variable.

![Set Variable screen](https://help.apple.com/workflow/en.lproj/Art/S0196_VariablesManual.png)

*Add to Variable* allows you to add multiple pieces of content to the same variable by appending to the variable each time, storing the data as an ordered list.

![Set Variable and Add to Variable screen](https://help.apple.com/workflow/en.lproj/Art/S0183_VariablesAdd.png)

Setting variables manually tends to lengthen workflows and make them harder to read. In most cases, manual variables are unnecessary—Magic Variables do much of the same work more concisely. For example, you can replicate most of the Add to Variable functionality by placing variables into a List action and retrieving the List Items variable later.

![Variables in a List action](https://help.apple.com/workflow/en.lproj/Art/S0184_VariablesAddList.png)

For step-by-step information about adding variables to your workflows, see [Use variables](https://help.apple.com/workflow/#/apdd02c2780c).

[Previous](https://help.apple.com/workflow/#/apdb5506f698) [Next](https://help.apple.com/workflow/#/apdd02c2780c)

© 2018 Apple Inc. All rights reserved.
***

==**2167**== Words

- **[Variable types - Workflow Help](https://help.apple.com/workflow/#/apdd2b316022)**