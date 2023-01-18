# gitlab code event triggers pipeline
**Usage scenario:**Pipelining is automatically triggered when code changes occur, such as code commit and code merge

![gitlba trigger plugin](../../../.gitbook/assets/image-trigger-gitlab-plugin.png)

![gitlab trigger](../../../.gitbook/assets/image-trigger-gitlab.png)

## Trigger mode
1. Commit Push Trigger when the Hook code is submitted
2. Tag Push Hook Trigger when the tagged code is submitted
Merge Request Hook 3. Merge Request Hook is triggered when code is merged
Merge Request Accept Hook 4. Merge Request Accept Hook is triggered when codes are merged
## parameter
Different triggering modes have different parameters
Code base: A public parameter that is a repository to listen for code events
### Commit Push Hook
1. Branch name: The branch where the code event occurred
2. Exclude the following target branches: Excluded branches do not trigger pipelined even if they have code events
3. Listen to the following path: If code changes occur in this path, the pipeline is triggered
4. Exclude the following paths: pipelining is not triggered if code changes occur under this path
5. Include the following people: Pipelined if the author of the code change is this person
6. Exclude the following people: Pipelining is not triggered if the author of the code change is this person
7. Contain the following Commit Message: If the commit message of the code change contains this message, the pipeline is triggered
8. Exclude the following Commit Message: If the commit message of the code change contains this message, the pipeline is not triggered   
### Tag Push Hook
1. Branch name: The branch where the code event occurred
2. Listen for the following tags: If the submitted code contains the following tags, the pipeline is triggered
3. Exclude the following tags: If the submitted code contains the following tags, the pipeline is not triggered
### Merge Request Hook
1. Branch name: The branch where the merge event occurs. If the pipeline is triggered when the dev branch is merged into the master branch, enter the branch name as master
2. Exclude the following target branches: If the target branches of the merge event are the following, the pipeline is not triggered
3. Monitor the following source branches: If the source branch of the merge event is the following branch, the pipeline is triggered
4. Exclude the following source branches: If the source branches of the merge event are the following, the pipeline is not triggered
5. Monitor the following paths: The pipeline is triggered when the target branch of the merge event contains code changes in the following paths
6. Exclude the following paths: If the merge event target branch contains code changes to the following paths, the pipeline is not triggered
7. Include the following personnel: The pipeline is triggered when code changes of the following personnel are included in the target branch of the merge event
8. Exclude the following: If the merge event target branch contains code changes for the following people, the pipeline will not be triggered
9. Contains the following Commit Message: If the target branch of the merge event contains the following commit information, the pipeline is triggered
10. Exclude the following Commit Message: If the target branch of the merge event contains the following commit information, the pipeline is not triggered
### Merge Request Accept Hook
1. Branch name: merge accept the branch where the event occurs. For example, if master receives the merge request from the dev branch, enter the branch name as master
2. Exclude the following target branches: If the target branches of the merge accept event are the following, the pipeline is not triggered
3. Listen to the following source branches: If the source branch of the merge accept event is the following branch, the pipeline is triggered
4. Exclude the following source branches: If the source branch of the merge accept event is the following, the pipeline is not triggered
5. Listen for the following paths: merge accept the target branch contains code changes in the following paths, and the pipeline is triggered
6. Exclude the following paths: If the merge accept event target branch contains code changes in the following paths, the pipeline is not triggered
7. The following personnel are included: The pipeline is triggered when the merge accept event target branch contains code changes of the following personnel
8. Exclude the following people: If the merge accept event target branch contains code changes of the following people, the pipeline is not triggered