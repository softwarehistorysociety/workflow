# "Run a workflow - Workflow Help"

*23-08-2022 22:31* 

> Use URL schemes with Workflow
Use URL schemes with Workflow

![](https://help.apple.com/workflow/en.lproj/GlobalArt/AppIconDefault_Workflow.png)

## Run a workflow

The URL scheme also supports running a workflow that is saved in My Workflows. This functionality may be useful in automation systems that extend beyond Workflow itself, so that other apps can run a workflow in your collection. Or you could use this URL in a task manager like OmniFocus or Todoist for running a workflow as one step in a project.

A URL to run a workflow takes the following structure:

`workflow://run-workflow?name=[name]&input=[input]`

The following parameters can be provided in the URL:

-   *name:* The name of the workflow to run.
    
-   *input (optional):* Either the word `text` or `clipboard`. This value determines what is provided as input to the beginning of the workflow. When set to `clipboard`, the contents of the clipboard are used.
    
-   *text (optional):* When input is set to text, this text is used as input to the workflow.
    

By setting the `input` to `text`, you can provide your own URL-encoded text as input to the workflow. For example, a URL to provide the text `soup` as input to a workflow named “Make PDF” would look like this:

`workflow://run-workflow?name=Make%20PDF&input=text&text=soup`

By setting the `input` to `clipboard`, the contents of the clipboard are used as input to the workflow. For example, a URL to run a workflow named “Add to Instapaper” with the clipboard would look like this:

`workflow://run-workflow?name=Add20%to20%Instapaper&input=clipboard`

**Tip:** If you’d like to run one workflow from within another, we recommend using the Run Workflow action instead of opening this URL. You should only run workflows with a URL if you’re integrating from another app outside of Workflow.

[Previous](https://help.apple.com/workflow/#/apda283236d7) [Next](https://help.apple.com/workflow/#/apd77a47304b)

© 2018 Apple Inc. All rights reserved.
***

==**1734**== Words

- **[Run a workflow - Workflow Help](https://help.apple.com/workflow/#/apd624386f42)**