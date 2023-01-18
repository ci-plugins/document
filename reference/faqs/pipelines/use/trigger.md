## Q1: Merge-Request-Accept-Hook



![](../../../../.gitbook/assets/image-20220301101202-RtEPQ.png)

The Merge Request Accept Hook is **triggered when the source branch is successfully merged into the target branch**

For example, when you want to combine feat_1 into the dev branch, write dev for the branch name and listen for the source branch to write feat_1.

![](../../../../.gitbook/assets/image-20220301101202-pxOZb.png)

## Q2: Where is the webhook address configured for the gitlab trigger

You do not need to configure this hook. BKCI will register the webhook itself. After selecting the event type and saving it, the webhook will be automatically registered



![](../../../../.gitbook/assets/wecom-temp-d5c48ee99a96d373426491d14d56e404.png)

## Q3: Pipeline was committed via gitlab, but the view code change log is empty. Indicating that this triggered build, with no new code changes, still triggers the pipeline

The possible reason is that the trigger listens for commit events for the entire codebase, but the code pull plug-in only pulls code for a specific branch that has no code changes. For example, if the plug-in listens for commit events for the entire codebase, but the code pull plug-in only pulls code for the master branch, While the commit is for the dev branch, the code change log shows the changes from the pulled branch that intersected the last checkup, and the master branch has no changes, so there is no change log.

## Q4: How to configure pipeline when you want to trigger pr

If you are using gitlab managed code, configure the gitlab trigger directly. The event types are as follows:

1. Commit Push Hook Triggered when the code is committed
2. Tag Push Hook Triggered when the tagged code is submitted
3. Merge Request Hook Merge request hook is triggered when code is merged
4. Merge Request Accept Hook The merge request accepts hook

## Q5: Is there a priority for listening and exclusion?

Listen > Exclude

If trigger is configured with both listener and exclusion options, and the event contains both listener and exclusion, the pipeline will fire.

## Q6: Can the monitored path be wildmatched?

The wildcard function is not supported. The prefix matching function is supported.

For example, if you enter source in the listening directory and the sourceabc directory changes, the event is also monitored.

## Q7: The listening path is configured, but the generated trigger is the listening root directory

In line with expectations. The server will listen to the root directory, but BKCI will filter based on this path.

This trigger is targeted at BKCI, and BKCI will also filter the configured listening path to decide whether to trigger the pipeline.

If you only want to limit it to a certain path, you need to change it manually.
