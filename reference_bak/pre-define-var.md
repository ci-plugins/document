# List of predefined variables

Reasonable use of variables can facilitate the maintenance pipeline. bk-ci provides a lot of system variables.

> Note: Variable means variable, which can be overwritten by users and plug-ins. Therefore, in the process of use, you should be careful to overwrite so as not to affect your own business logic. bk-ci has no system constant, and everything is left to the user to decide

Usage: In plug-in configuration, enter ${variable name} to get the value of the corresponding variable. Example: ${BK_CI_PIPELINE_NAME}  

| Variable                     | Description                                                  | sample                                                       |
| :--------------------------- | :----------------------------------------------------------- | :----------------------------------------------------------- |
| BK_CI_PIPELINE_ID            | The pipeline ID is 34 bits long and globally unique          | p-2fc5a05b25024d5586742b8e88d3c853                           |
| BK_CI_START_TYPE             | Build a startup mode, MANUAL/TIME_TRIGGER WEB_HOOK/SERVICE/PIPELINE/value in the REMOTE | WEB_HOOK                                                     |
| BK_CI_PROJECT_NAME           | English name of project                                      | alltest                                                      |
| BK_CI_PIPELINE_NAME          | Pipeline name                                                | Continuous delivery pipeline                                 |
| BK_CI_BUILD_ID               | Pipeline current build ID, 34 bits long, globally unique     | b-d82918fc4f5c44c790d538785685f36b                           |
| BK_CI_BUILD_NUM              | Build sequence number, incrementing from 1                   |                                                              |
| BK_CI_BUILD_JOB_ID           | ID of the current Job created by the pipeline. The value is 34 characters in length and globally unique |                                                              |
| BK_CI_BUILD_TASK_ID          | Pipeline current plug-in Task ID, 34 bits long, globally unique |                                                              |
| BK_CI_BUILD_REMARK           | The pipeline builds the remarks information, which is set by setEnv "BK_CI_BUILD_REMARK" while the pipeline is running |                                                              |
| BK_CI_BUILD_START_TIME       | Pipeline startup time, milliseconds                          |                                                              |
| BK_CI_BUILD_END_TIME         | Pipeline end time, milliseconds                              |                                                              |
| BK_CI_BUILD_TOTAL_TIME       | Pipeline execution time                                      |                                                              |
| BK_CI_BUILD_FAIL_TASKS       | Format: [STAGE alias][JOB alias]TASK alias 2. If multiple concurrent jobs fail, use newlines to separate them | Can be used in build failure notifications, or in plug-ins during pipeline execution |
| BK_CI_BUILD_FAIL_TASKNAMES   | All tasks that failed to be executed in the pipeline are in the format of TASK alias,TASK alias,TASK alias | Can be used in build failure notifications, or in plug-ins during pipeline execution |
| BK_CI_TURBO_ID               | Compile acceleration task ID, which is available only if compile acceleration is enabled |                                                              |
| BK_CI_MAJOR_VERSION          | A unique, major version number in the pipeline, which is displayed after the recommended Version number function is enabled |                                                              |
| BK_CI_MINOR_VERSION          | A unique feature version in the pipeline. The feature version appears after the recommended Version function is enabled |                                                              |
| BK_CI_FIX_VERSION            | The only version in the pipeline, modified version, after the "recommended version number" function is enabled |                                                              |
| BK_CI_BUILD_NO               | A unique build number in the pipeline, which appears after the "recommended version number" function is enabled. You can set different autoincrement rules |                                                              |
| BK_CI_PIPELINE_UPDATE_USER   | Pipeline update user                                         |                                                              |
| BK_CI_PIPELINE_VERSION       | Pipeline version number                                      |                                                              |
| BK_CI_PROJECT_NAME_CN        | Name of the project corresponding to the pipeline            |                                                              |
| BK_CI_START_CHANNEL          | Pipeline-started CHANNEL CODE                                |                                                              |
| BK_CI_START_USER_ID          | The user ID of the pipeline build, the current user ID of the general manual startup, and the user ID of the pipeline person for the retry. If it is a timed /webhook/ subpipeline call, it is the last modifier of the pipeline |                                                              |
| BK_CI_START_USER_NAME        | User ID for pipelined-build startup. The value is usually the same as BK_CI_START_USER_ID except in the following two cases: 1. If the boot mode is WEBHOOK, the value is the user ID of Git/SVN. 2. When called by a child pipeline, this value is the ID of the builder of the parent pipeline | For example, the last change of parent1 and Sub2 is User0. user1 Manually run the parent pipeline of parent1. parent1 starts Sub2, and the BK_CI_START_USER_ID of Sub2 is User0. BK_CI_START_USER_NAME is User1 |
| BK_CI_PARENT_PIPELINE_ID     | Gets the ID of the parent pipeline that started the current pipeline, valid only if it is a child pipeline and is triggered by the parent pipeline |                                                              |
| BK_CI_PARENT_BUILD_ID        | Gets the build ID of the parent pipeline that started the current pipeline, valid only if it is a child pipeline and is triggered by the parent pipeline |                                                              |
| BK_CI_START_PIPELINE_USER_ID | Gets the parent pipeline starter that starts the current pipeline. This is only valid if it is a child pipeline and is triggered by the parent pipeline |                                                              |
| BK_CI_START_WEBHOOK_USER_ID  | Get the trigger Webhook account that started the current pipeline. This is only valid if it was triggered by the webhook. This value will be displayed in the execution history, but the actual executor is not him, but the last pipeliner |                                                              |
| BK_CI_RETRY_COUNT            | The number of retries, which does not exist by default. This variable appears only when failed retry /rebuild occurs, and +1 |                                                              |

 
