# Pipelined graphic layout

## Stage operation set
### Open access for Stage
In the full CI/CD life cycle, it is inevitable that there will be some steps that expect human intervention. The Stage access feature allows you to pause the process before the pipeline reaches a certain Stage and continue after human intervention.
#### Open method
When editing pipeline, click the lightning ICON in the upper left corner of an existing Stage to enter the Stage access property panel
![](../../../.gitbook/assets/image%20%2850%29.png)

![](../../../.gitbook/assets/image%20%2849%29.png)

#### The effect after being turned on
* If a build task is in the Stage entry audit, the build task will become a "STAGE\_SUCCESS" state. See [Pipeline Status Summary](../pipeline-build-detail/status.md#pipeline-zhuang-tai)
