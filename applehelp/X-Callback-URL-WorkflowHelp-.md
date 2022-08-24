# "X-Callback-URL - Workflow Help"

*23-08-2022 22:31* 

> Use URL schemes with Workflow
Use URL schemes with Workflow

![](https://help.apple.com/workflow/en.lproj/GlobalArt/AppIconDefault_Workflow.png)

## X-Callback-URL

Workflow supports x-callback-url, allowing the calling app to receive a response (a callback) when a particular interaction has completed. You can import and run workflows from an x-callback-url using the same parameters as discussed in [Run a workflow](https://help.apple.com/workflow/#/apd624386f42) and [Import a workflow](https://help.apple.com/workflow/#/apd77a47304b). Here’s an example:

`workflow://x-callback-url/run-workflow?name=Calculate%20Tip&input=text&text=24.99&x-success=...&x-cancel=...`

Per the x-callback-url standard, the following additional parameters can be provided:

-   *x-success (optional):* A URL that opens when the interaction is successful—for example, after a workflow is imported or finished running. If a workflow is run, a parameter named `result` is appended to the URL and contains the textual output of the workflow.
    
-   *x-cancel (optional):* A URL that opens when the interaction is canceled by the user.
    
-   *x-error (optional)*: A URL that opens when the interaction fails because an error occurred. A parameter named `errorMessage` is appended to the URL and contains a description of the error.
    

With `x-success`, you can provide a URL that opens after the workflow successfully finishes running. This could be used in conjunction with a multistep checklist of tasks in OmniFocus, wherein you open the x-callback-url to run a workflow, return to the list, and move on to the next task via URL.

With `x-cancel`, you can provide a contingency URL to launch if the workflow stops before it finishes running. Because the workflow did not complete, no output from the workflow is provided.

With `x-error`, you can provide a contingency URL to launch if the workflow encounters an error while running and fails to finish. In this case, you can kick off a different URL to handle the issue.

[Previous](https://help.apple.com/workflow/#/apd9c112ca23) [Next](https://help.apple.com/workflow/#/apd68802640c)

© 2018 Apple Inc. All rights reserved.
***

==**1835**== Words

- **[X-Callback-URL - Workflow Help](https://help.apple.com/workflow/#/apdcd7f20a6f)**