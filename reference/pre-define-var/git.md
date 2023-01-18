# GIT Constants Collection

## GIT pulls constants

| Variable                             | Description                                             |
| :----------------------------------- | :------------------------------------------------------ |
| BK_CI_GIT_REPO_URL                   | Pull the code library URL                               |
| BK_CI_GIT_REPO_NAME                  | Pull the code library name                              |
| BK_CI_GIT_REPO_ALIAS_NAME            | Pull code library alias in BKCI                  |
| BK_CI_GIT_REPO_BRANCH                | Pull the branch of the code base                        |
| BK_CI_GIT_REPO_TAG                   | Pull the TAG of the code base                           |
| BK_CI_GIT_REPO_CODE_PATH             | Pull the local relative directory path of the code base |
| BK_CI_GIT_REPO_LAST_COMMIT_ID        | The commit id of the last build                         |
| BK_CI_GIT_REPO_HEAD_COMMIT_ID        | commit id of this build                                 |
| BK_CI_GIT_REPO_HEAD_COMMIT_COMMENT   | Commit comments for this build                          |
| BK_CI_GIT_REPO_HEAD_COMMIT_AUTHOR    | The author of this build                                |
| BK_CI_GIT_REPO_HEAD_COMMIT_COMMITTER | committer of this construction                          |

## GIT event triggers constants

| Variable                               | Description                                                  |
| :------------------------------------- | :----------------------------------------------------------- |
| BK_CI_REPO_WEBHOOK_REPO_TYPE           | The type of code base triggered is GIT                       |
| BK_CI_REPO_WEBHOOK_REPO_URL            | The URL of the code base that is triggered                   |
| BK_CI_REPO_WEBHOOK_NAME                | The name of the code base that is triggered                  |
| BK_CI_REPO_WEBHOOK_ALIAS_NAME          | Triggered code base alias in BKCI                     |
| BK_CI_REPO_WEBHOOK_HASH_ID             | The triggered code base has the HASH ID in BKCI       |
| BK_CI_REPO_GIT_WEBHOOK_COMMITID        | The corresponding COMMIT ID is triggered                     |
| BK_CI_REPO_GIT_WEBHOOK_EVENT_TYPE      | The type of event that is triggered                          |
| BK_CI_REPO_GIT_WEBHOOK_INCLUDE_BRANCH  | Triggers the listening branch of the plug-in                 |
| BK_CI_REPO_GIT_WEBHOOK_EXCLUDE_BRANCH  | Triggers the excluded branch of the plugin                   |
| BK_CI_REPO_GIT_WEBHOOK_INCLUDE_PATHS   | The listening path that triggers the plug-in                 |
| BK_CI_REPO_GIT_WEBHOOK_EXCLUDE_PATHS   | The path that triggers the plugin's exclusion                |
| BK_CI_REPO_GIT_WEBHOOK_EXCLUDE_USERS   | The person who triggers the plug-in's exclusion              |
| BK_CI_GIT_WEBHOOK_FINAL_INCLUDE_BRANCH | The plug-in configures the final matched branch in Listen for the following target branch, if no configured value is null |
| BK_CI_GIT_WEBHOOK_FINAL_INCLUDE_PATH   | The list of paths that are eventually matched in Listen for the following paths in plug-in configuration is empty if not configured |
| BK_REPO_GIT_WEBHOOK_PUSH_COMMIT_MSG_n  | The Commit log that is triggered. n is only equal to 1 for push events; For mr Events n ranges from 1 to 32 |
| BK_CI_HOOK_MESSAGE                     | The commit message when triggered                            |

## GIT Commit Push Hook events trigger constants

| Variable                                   | Description                                                  |
| :----------------------------------------- | :----------------------------------------------------------- |
| BK_CI_REPO_GIT_WEBHOOK_PUSH_USERNAME       | User of PUSH                                                 |
| BK_CI_REPO_GIT_WEBHOOK_BRANCH              | PUSH corresponding branch                                    |
| BK_REPO_GIT_WEBHOOK_PUSH_BEFORE_COMMIT     | commit id before the PUSH                                    |
| BK_REPO_GIT_WEBHOOK_PUSH_AFTER_COMMIT      | commit id of the PUSH                                        |
| BK_REPO_GIT_WEBHOOK_PUSH_ADD_FILE_n1_n2    | The file added in this PUSH. n1 indicates the number of submissions. n2 indicates the number of files in the submission. n ranges from 1 to 32 |
| BK_REPO_GIT_WEBHOOK_PUSH_MODIFY_FILE_n1_n2 | Files changed in this PUSH. n1 indicates the number of submissions. n2 indicates the number of files in the submission. n ranges from 1 to 32 |
| BK_REPO_GIT_WEBHOOK_PUSH_DELETE_FILE_n1_n2 | Files deleted in this PUSH. n1 indicates the number of submissions. n2 indicates the number of files in the submission. n ranges from 1 to 32 |
| BK_REPO_GIT_WEBHOOK_PUSH_ADD_FILE_COUNT    | Number of files added in this PUSH                           |
| BK_REPO_GIT_WEBHOOK_PUSH_MODIFY_FILE_COUNT | Number of files changed in this PUSH                         |
| BK_REPO_GIT_WEBHOOK_PUSH_DELETE_FILE_COUNT | Number of files deleted in this PUSH                         |

## GIT Merge Request Hook or Merge Request Hook Accept event trigger constant

| Variable                                     | Description                                                  |
| :------------------------------------------- | :----------------------------------------------------------- |
| BK_CI_REPO_GIT_WEBHOOK_MR_AUTHOR             | Merge the author or submitter of the Request                 |
| BK_CI_REPO_GIT_WEBHOOK_TARGET_URL            | The URL of the Merge Request object code base                |
| BK_CI_REPO_GIT_WEBHOOK_SOURCE_URL            | The source code library URL of the Merge Request             |
| BK_CI_REPO_GIT_WEBHOOK_TARGET_BRANCH         | Merge the target branch of the Request                       |
| BK_CI_REPO_GIT_WEBHOOK_SOURCE_BRANCH         | Merge the source branch of the Request                       |
| BK_CI_REPO_GIT_WEBHOOK_MR_CREATE_TIME        | Specifies the creation time of the Merge Request             |
| BK_CI_REPO_GIT_WEBHOOK_MR_UPDATE_TIME        | Update time of the Merge Request                             |
| BK_CI_REPO_GIT_WEBHOOK_MR_CREATE_TIMESTAMP   | The creation timestamp of the Merge Request                  |
| BK_CI_REPO_GIT_WEBHOOK_MR_UPDATE_TIMESTAMP   | The update timestamp of the Merge Request                    |
| BK_CI_REPO_GIT_WEBHOOK_MR_ID                 | Id of the Merge Request that is triggered                    |
| BK_CI_REPO_GIT_WEBHOOK_MR_NUMBER             | Number of Merge requests that are triggered                  |
| BK_CI_REPO_GIT_WEBHOOK_MR_DESC               | This section describes the Merge Request                     |
| BK_CI_REPO_GIT_WEBHOOK_MR_TITLE              | Title of the Merge Request                                   |
| BK_CI_REPO_GIT_WEBHOOK_MR_ASSIGNEE           | Merge Request manager                                        |
| BK_CI_REPO_GIT_WEBHOOK_MR_URL                | URL of the Merge Request                                     |
| BK_CI_REPO_GIT_WEBHOOK_MR_REVIEWERS          | Merge Request reviewers (including necessary reviewers)      |
| BK_CI_REPO_GIT_WEBHOOK_MR_MILESTONE          | Milestone name of the Merge Request                          |
| BK_CI_REPO_GIT_WEBHOOK_MR_MILESTONE_DUE_DATE | Milestone time of the Merge Request                          |
| Milestone time of the Merge Request          | Label of the Merge Request                                   |
| BK_CI_REPO_GIT_WEBHOOK_COMMITID              | Indicates the ID of the Merge Request                        |
| BK_REPO_GIT_WEBHOOK_MR_LAST_COMMIT           | Merge Request last commitId to submit                        |
| BK_REPO_GIT_WEBHOOK_MR_LAST_COMMIT_MSG       | Merge Request Indicates the submission information of the last submission |

## The GIT Tag Push Hook event is triggered

| Variable                             | Description                                                  |
| :----------------------------------- | :----------------------------------------------------------- |
| BK_CI_REPO_GIT_WEBHOOK_TAG_NAME      | TAG name to submit                                           |
| BK_CI_REPO_GIT_WEBHOOK_TAG_OPERATION | TAG action: create or delete (create/delete)                 |
| BK_CI_REPO_GIT_WEBHOOK_TAG_USERNAME  | The author of the submitted TAG                              |
| BK_REPO_GIT_WEBHOOK_TAG_CREATE_FROM  | Which branch or commit point is the tag created from? If the tag is created from the client, the value is null |

## The GIT Code Review Hook event is triggered. Procedure

| Variable                                          | Description                                            |
| :------------------------------------------------ | :----------------------------------------------------- |
| BK_CI_REPO_GIT_WEBHOOK_REVIEW_REVIEWABLE_TYPE     | If the CR is created by MR, the value is merge_request |
| BK_CI_REPO_GIT_WEBHOOK_REVIEW_REVIEWABLE_ID       | If the CR is created by MR, the value is mr id         |
| BK_CI_REPO_GIT_WEBHOOK_REVIEW_RESTRICT_TYPE       | Review rules                                           |
| BK_CI_REPO_GIT_WEBHOOK_REVIEW_APPROVING_REVIEWERS | List of persons not reviewed, divided by               |
| BK_CI_REPO_GIT_WEBHOOK_REVIEW_APPROVED_REVIEWERS  | List of reviewers, divided by                          |

## A GIT ISSUE event is triggered. Procedure

| Variable                                  | Description        |
| :---------------------------------------- | :----------------- |
| BK_CI_REPO_GIT_WEBHOOK_ISSUE_TITLE        | issue title        |
| BK_CI_REPO_GIT_WEBHOOK_ISSUE_ID           | issue id           |
| BK_CI_REPO_GIT_WEBHOOK_ISSUE_IID          | issue iid          |
| BK_CI_REPO_GIT_WEBHOOK_ISSUE_DESCRIPTION  | issue description  |
| BK_CI_REPO_GIT_WEBHOOK_ISSUE_STATE        | issue status       |
| BK_CI_REPO_GIT_WEBHOOK_ISSUE_OWNER        | issue creator      |
| BK_CI_REPO_GIT_WEBHOOK_ISSUE_URL          | issue url          |
| BK_CI_REPO_GIT_WEBHOOK_ISSUE_MILESTONE_ID | issue milestone id |
| BK_CI_REPO_GIT_WEBHOOK_ISSUE_ACTION       | issue operation    |

## The GIT Note event is triggered

| Variable                                  | Description                                      |
| :---------------------------------------- | :----------------------------------------------- |
| BK_CI_REPO_GIT_WEBHOOK_NOTE_COMMENT       | Comment content                                  |
| BK_CI_REPO_GIT_WEBHOOK_NOTE_ID            | Comment ID                                       |
| BK_CI_REPO_GIT_WEBHOOK_NOTE_NOTEABLE_TYPE | The comment type can be Review, Commit, or Issue |
| BK_CI_REPO_GIT_WEBHOOK_NOTE_AUTHOR_ID     | Review writer                                    |
| BK_CI_REPO_GIT_WEBHOOK_NOTE_CREATED_AT    | Comment creation time                            |
| BK_CI_REPO_GIT_WEBHOOK_NOTE_UPDATED_AT    | Comment update time                              |
| BK_CI_REPO_GIT_WEBHOOK_NOTE_URL           | Comment url                                      |