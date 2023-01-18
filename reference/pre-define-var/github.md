# GITHUB Constants Collection

## GITHUB pulls the code

| Variable                            | Description |
| :---------------------------------- | :---------- |
| git.${group}.${project}.new.commit  |             |
| git.${group}.${project}.last.commit |             |

## GITHUB triggers public constants

| Variable                               | Description                                            |
| :------------------------------------- | :----------------------------------------------------- |
| BK_CI_REPO_WEBHOOK_REPO_TYPE           | The type of code base triggered is GIT                 |
| BK_CI_REPO_WEBHOOK_REPO_URL            | The URL of the code base that is triggered             |
| BK_CI_REPO_WEBHOOK_NAME                | The name of the code base that is triggered            |
| BK_CI_REPO_WEBHOOK_ALIAS_NAME          | Triggered code base alias in BKCI               |
| BK_CI_REPO_WEBHOOK_HASH_ID             | The triggered code base has the HASH ID in BKCI |
| BK_CI_REPO_GIT_WEBHOOK_COMMITID        | The corresponding COMMIT ID is triggered               |
| BK_CI_REPO_GIT_WEBHOOK_EVENT_TYPE      | The type of event that is triggered                    |
| BK_CI_REPO_GIT_WEBHOOK_INCLUDE_BRANCHS | Triggers the listening branch of the plug-in           |
| BK_CI_REPO_GIT_WEBHOOK_EXCLUDE_BRANCHS | Triggers the excluded branch of the plugin             |
| BK_CI_REPO_GIT_WEBHOOK_EXCLUDE_USERS   | Triggers the eliminator of the plug-in                 |

## GITHUB creates a Branch Or Tag event. Procedure

| Variable                                  | Description                    |
| :---------------------------------------- | :----------------------------- |
| BK_CI_REPO_GITHUB_WEBHOOK_CREATE_REF_NAME | TAG or BRANCH name             |
| BK_CI_REPO_GITHUB_WEBHOOK_CREATE_REF_TYPE | REF type, TAG or BRANCH        |
| BK_CI_REPO_GITHUB_WEBHOOK_CREATE_USERNAME | The author who created the REF |

## The GITHUB Commit Push Hook event is triggered

| Variable                             | Description                      |
| :----------------------------------- | :------------------------------- |
| BK_CI_REPO_GIT_WEBHOOK_PUSH_USERNAME | User of PUSH                     |
| BK_CI_REPO_GIT_WEBHOOK_BRANCH        | The branch corresponding to PUSH |
|                                      |                                  |

## GITHUB Pull Request Hook event triggered

| Variable                                     | Description                                  |
| :------------------------------------------- | :------------------------------------------- |
| BK_CI_REPO_GIT_WEBHOOK_MR_AUTHOR             | The author or submitter of PR                |
| BK_CI_REPO_GIT_WEBHOOK_TARGET_URL            | The object code library URL of PR            |
| BK_CI_REPO_GIT_WEBHOOK_SOURCE_URL            | PR source code library URL                   |
| BK_CI_REPO_GIT_WEBHOOK_TARGET_BRANCH         | Target branch of PR                          |
| BK_CI_REPO_GIT_WEBHOOK_SOURCE_BRANCH         | The source branch of PR                      |
| BK_CI_REPO_GIT_WEBHOOK_MR_CREATE_TIME        | Creation time of PR                          |
| BK_CI_REPO_GIT_WEBHOOK_MR_UPDATE_TIME        | The creation timestamp of PR                 |
| BK_CI_REPO_GIT_WEBHOOK_MR_ID                 | ID of PR                                     |
| BK_CI_REPO_GIT_WEBHOOK_MR_NUMBER             | Update timestamp of PR                       |
| BK_CI_REPO_GIT_WEBHOOK_MR_DESC               | Description of PR                            |
| BK_CI_REPO_GIT_WEBHOOK_MR_TITLE              | PR title                                     |
| BK_CI_REPO_GIT_WEBHOOK_MR_ASSIGNEE           | PR director                                  |
| BK_CI_REPO_GIT_WEBHOOK_MR_URL                | URL of PR                                    |
| BK_CI_REPO_GIT_WEBHOOK_MR_REVIEWERS          | PR reviewers (including necessary reviewers) |
| BK_CI_REPO_GIT_WEBHOOK_MR_MILESTONE          | The milestone name of PR                     |
| BK_CI_REPO_GIT_WEBHOOK_MR_MILESTONE_DUE_DATE | PR milestone time                            |
| BK_CI_REPO_GIT_WEBHOOK_MR_LABELS             | PR label                                     |
