## Q1: How to do queuing/mutual exclusion operation between pipelines

Refer to this document for configuration

[pipeline mutual exclusion](../../../tutorials/scene/pipeline-exclusion-queue)



## Q2: Pipeline waiting for execution results of other pipelines

Question background: I have pipeline A, which can be executed separately, and I have pipeline B, which will call A and wait for a result of A. How can I do this kind of mutual exclusion?

You can use the sub-pipeline function.

Use call pipeline to call the sub-pipeline. Select **synchronous execution**, and continue to wait for the result of execution after triggering, and then decide whether to continue after the result is available.



## Q3: How to display custom information in the pipeline build history page

You can add a shell **plugin** in the pipeline to achieve the desired note by setting the value of the global variable `BK_CI_BUILD_REMARK`. The field will be displayed only when the pipeline is finished.

And add the note field in the pipeline history page. For details, please refer to.

[Using the note variable](../../../services/pipelines/pipeline-variables/pipeline-variables-remark)



## Q4: Can the variables in a pipeline be linked, e.g. the value of variable B follows variable A?

For now, linkage is not supported. If the value does not change much, you can set the default value.



## Q5: Can I get the value of the parameter drop-down list through a custom interface when the pipeline is executed?

Interface customization is not supported.



## Q6: Do multiple jobs share a workspace?

If you use a single builder (private builder), multiple jobs will share a workspace directory.

If it is a public build machine, then each job will have a separate directory under workspace.

For both private and public build machines, by default, each pipeline creates a separate workspace directory.



## Q7: How to get the URL of the build product

http://devops.bktencent.com/ms/artifactory/api/user/artifactories/file/download/local?filePath=/bk-archive/${project_name}/${BK\_CI\_ PIPELINE\_ID}/${BK\_CI\_BUILD\_ID}/{your artifacts file name}



---

