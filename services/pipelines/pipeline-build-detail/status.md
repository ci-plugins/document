# Summary of flow line status information

## Pipeline status

| KEY | Description | Display Name |
| :--- | :--- | :--- |
| QUEUE\_CACHE | Initial state: waiting for scheduling in the queue, will switch to QUEUE\_CACHE | in the queue before ready for execution
| QUEUE\_CACHE | Intermediate state: In the execution queue, can be started | Pending
| RUNNING | intermediate state: running | running |
| CANCELED | Final state: cancelled | CANCEL
| STAGE\_SUCCESS | Final State: A successful state when Stage manual audit cancels a run | STAGE COMPLETE (success) |
| SUCCEED | Final state: Success | SUCCESS |
| FAILED | Final State: Failed | Failed |
| TERMINATE | Final state: Pipeline in RUNNING state is forced to terminate due to environment exceptions | TERMINATED (failure) |
| QUEUE\_TIMEOUT | Final state: Timeout caused by waiting for scheduling in the queue | Queue timeout |

## Stage status

| KEY | Description | Display Name |
| :--- | :--- | :--- |
| QUEUE\_CACHE | Initial state: waiting for scheduling in the queue, will switch to QUEUE\_CACHE | in the queue before ready for execution
| QUEUE\_CACHE | Intermediate state: In the execution queue, can be started | Pending
| RUNNING | intermediate state: running | running |
| REVIEWING | Intermediate state: stage is under human review | REVIEWING |
| PAUSE | Intermediate state: When the stage is being manually reviewed and waiting for review | Pause
| CANCELED | Final state: Cancel | CANCELED
| SUCCEED | Final state: Success | SUCCEED
| FAILED | Final State: Failed | Failed |
| TERMINATE | Final state: Stage in RUNNING state is forced to terminate due to environment exception | TERMINATED (FAILED)
| SKIP | Final state: skip no execution | SKIP |
| UNEXEC | Final state: never executed, end due to possible build failure, not executed later | never executed (not involved in final success/failure state operation) |
| QUEUE\_TIMEOUT | Final state: timeout caused by waiting for scheduling in the queue | Queue timeout |
| STAGE\_SUCCESS | Final state: A successful state when Stage manual audit is canceled to run | Stage completion (success) |

## Job status

| KEY | Description | Display Name |
| :--- | :--- | :--- |
| QUEUE\_CACHE | Initial state: waiting for scheduling in the queue, will switch to QUEUE\_CACHE | in the queue before ready for execution
| QUEUE\_CACHE | Intermediate state: In the execution queue, can be started | Pending
| LOOP\_WAITING | Intermediate state: waiting in rotation Mutual exclusion group robbing lock rotation | Mutual exclusion lock rotation waiting |
| DEPENDENT\_WAITING | Intermediate state: waiting for dependent jobs to complete before entering the ready environment | DEPENDENT\_WAITING |
| PREPARE\_ENV | Intermediate state: the builder is starting in the preparation environment | PREPARE\_ENV | RUNNING | Intermediate state: the builder is starting in the preparation environment
| RUNNING | Intermediate state: running | running |
| PAUSE | Intermediate state: When the plug-in pauses execution, it will set the state of Job to paused as well | PAUSE |
| CANCELED | Final state: Cancel | Cancel
| SUCCEED | Final state: success | success |
| FAILED | Final state: Fail | Failed
| TERMINATE | Final state: JOB in RUNNING state is forced to terminate due to environment exception | TERMINATED (FAILED)
| SKIP | Final state: skip no execution | skip |
| UNEXEC | Final state: never executed, end due to possible build failure, not executed later | never executed (not involved in final success/failure state operation) |
| QUEUE\_TIMEOUT | Final state: timeout caused by waiting for scheduling in queue | Queue timeout |
| HEARTBEAT\_TIMEOUT | Final state: Agent lost connection with the server for more than 2 minutes during the build process | Heartbeat timeout (failure)

## Task status

| KEY | Description | Display Name |
| :--- | :--- | :--- |
| QUEUE\_CACHE | Initial state: waiting for scheduling in the queue, will switch to QUEUE\_CACHE | in the queue before ready for execution
| QUEUE\_CACHE | Intermediate state: In the execution queue, can be started | Pending
| RETRY | intermediate state: set to fail retry, enter execution queue | pending retry
| RUNNING | Intermediate state: running | running
| CALL\_WAITING | Intermediate state: used to start the build environment plug-in waiting for the builder to call back the start result | Waiting for the builder to call back (running) |
| REVIEWING | intermediate state: manual review plugin or quality redline is configured for manual review and is pending review | PENDING REVIEW (RUNNING) |
| PAUSE | Intermediate state: The plugin is set to pause execution | Pause execution |
| REVIEW\_ABORT | Final state: The manual review plug-in or quality redline is configured for manual review and clicked Reject / Terminate | Manual review rejected (failed) |
| REVIEW\_PROCESSED | Final state: The manual review plug-in or quality redline was configured for manual review and clicked PASS | Manual review passed (success)
| CANCELED | Final state: cancelled | CANCELED |
| SUCCEED | Final state: Success | Success |
| FAILED | Final state: Fail | Failed |
| TERMINATE | Final state: Plug-in in RUNNING state is forced to terminate due to environment exception | TERMINATED (failed) |
| SKIP | Final state: skip not executed | SKIP |
| EXEC\_TIMEOUT | Final state: execution time exceeds the configured timeout | Execution timeout (failure) |
| UNEXEC | Final state: never executed, end of possible build failure, not executed later | never executed (not involved in the final success/failure state operation) |
| QUEUE\_TIMEOUT | Final state: timeout due to waiting for scheduling in queue | Queue timeout |
| QUALITY\_CHECK\_FAIL | Final state: direct failure after being intercepted by the quality red line (no manual review set) | intercepted by the quality red line (failure) |

