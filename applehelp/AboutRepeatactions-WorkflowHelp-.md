# "About Repeat actions - Workflow Help"

*23-08-2022 22:31* 

> Use Repeat actions
Use Repeat actions

![](https://help.apple.com/workflow/en.lproj/GlobalArt/AppIconDefault_Workflow.png)

## About Repeat actions

The Repeat action and the Repeat with Each action allow you to run a group of actions in a workflow multiple times in a row.

## Using the Repeat action

When you drag a Repeat action into your workflow, the action includes two markers: Repeat and End Repeat. Place the actions that you want to repeat between the Repeat and End Repeat markers, then specify the number of times you want the action to repeat. When the workflow runs, the actions placed between the markers loop the number of times that you specify.

For example, a repeat loop that contains a Vibrate Device action set to Repeat 3 Times vibrates three times when the workflow is run.

![Vibrate Device action set to repeat three times](https://help.apple.com/workflow/en.lproj/Art/S0173_RepeatBasic.png)

You can place unlimited actions within a repeat loop. The actions run in order (from top to bottom), and when the last action is reached, the workflow loops back to the first action, then runs again (the specified number of times).

## About input flow in a Repeat action

When you pass input into the Repeat action, that same input is passed into the beginning of the loop with each iteration. For example, if a workflow contains a Text action followed by a repeat loop with a Speak Text action, the workflow speaks same text multiple times.

![Text action followed by Repeat action set to loop 3 times](https://help.apple.com/workflow/en.lproj/Art/S0174_RepeatBasicEx.png)

For each iteration of a repeat loop, the last action’s output is gathered into a list, and that list becomes the output of the Repeat action as a whole.

![Repeat action example](https://help.apple.com/workflow/en.lproj/Art/S0264_RepeatExample.png)

For example, a Repeat action that runs four times and contains a Get Latest Photos action outputs the most recent photo saved to the Camera Roll in each iteration of the loop. After all four iterations run, the outputs are gathered together, and a list of four identical photos is created. The four photos become the output of the Repeat action as a whole, and are then passed to the next action after the repeat loop.

To learn more about the flow of inputs and outputs, see [How workflows work](https://help.apple.com/workflow/#/apd1d10ec518).

**Tip:** Tap the empty space around the plus (+) and minus (–) buttons and to set the number of repetitions to a [variable](https://help.apple.com/workflow/#/apdb5506f698). When set to [Ask When Run](https://help.apple.com/workflow/#/apd8b28e2166), you’ll be asked to choose how many times the loop should repeat when the workflow runs.

## Using the Repeat with Each action

The Repeat with Each action takes a list of items as its input, and then runs the same group of actions one time for each item in the list. This is useful if you’re working with multiple files or with multiple pieces of content. This type of loop repeats until every item that was passed into the Repeat with Each action iterates.

For example, if you have a Get Upcoming Events action set to retrieve the next four upcoming calendar events and you place a Repeat with Each action after the action, the repeat loop runs four times and each iteration receives one of the calendar events as input.

At the end of the repeat loop, the output passed to the End Repeat action during each iteration is gathered together and passed as the output of the Repeat with Each as a whole.

## The Repeat Item variable

Repeat with Each loops offer a special variable for tracking the current item called Repeat Item. The Repeat Item variable updates with each iteration of the loop, containing the item passed as input for that iteration.

For example, if you pass 10 calendar items into a Repeat with Each action, the Repeat Item variable represents one of the calendar events in each iteration as the workflow loops through each calendar item.

Repeat Item is available in the variable bar and tray.

*Note:* If you’ve placed a Repeat with Each action inside another Repeat with Each action, the variable name changes to Repeat Item 1 to represent the inner repeat item, to Repeat Item 2 for the deeper loop, and so on.

## The Repeat Index variable

All repeat loops offer a special variable called Repeat Index, which is used to keep track of the current iteration. The Repeat Index variable contains the number of times a loop has been repeated so far, starting at 1 for the first iteration of the loop and incrementing by one each time. The second time a loop runs, the Repeat Index is 2; the third time a loop runs, the Repeat Index is 3; and so on.

*Note:* If there are nested repeat loops (one Repeat action inside another), the inner Repeat action's variable name changes to Repeat Index 2. An additional nested Repeat action would offer a Repeat Index 3 variable, and so on.

To learn more about variables, see [Use variables](https://help.apple.com/workflow/#/apdd02c2780c).

## Creating infinite loops

Although Workflow doesn’t offer an action to repeatedly run a group of actions forever, you can emulate this behavior by using the Run Workflow action. The Run Workflow action allows you to run one workflow inside of another. Configure the Run Workflow action to run the same workflow that it’s contained within, and the workflow runs from start to finish repeatedly until you stop the workflow.

## Testing the output

When you’re learning to work with Repeat and Repeat with Each, it’s helpful to test the results that are produced after the End Repeat marker to ensure the content is what you intended. Place a Quick Look action after the End Repeat marker to preview the items that the repeat loop output.

You can also place a Show Alert action after the End Repeat marker and insert a Repeat Results [Magic Variable](https://help.apple.com/workflow/#/apdd2b316022) in the message box to display text that has been output by the loop. If you’re testing a loop that’s in the middle of a long workflow, it’s helpful to use a Show Alert action to preview results, as you can include a Cancel button in the alert to end the workflow at that point in the loop.

[Previous](https://help.apple.com/workflow/#/apd83dcd1b51) [Next](https://help.apple.com/workflow/#/apd6bd3e561d)

© 2018 Apple Inc. All rights reserved.
***

==**5542**== Words

- **[About Repeat actions - Workflow Help](https://help.apple.com/workflow/#/apdc11deb2c1)**