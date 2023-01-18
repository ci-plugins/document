## Q1: How to do queuing/exclusive operations between pipelines

Refer to this document for configuration

[Pipeline exclusion](../../../../tutorials/scene/pipeline-exclusion-queue)

## Q2: Pipeline waits for execution results of other pipelines

Background: I have pipeline A, which can be executed separately, and I have pipeline B, which will call A and wait for A result of A. How to make this mutually exclusive?

You can use the subpipeline feature.

Invoke the subpipeline using the call pipeline. Select **synchronous execution.** Wait for the execution result after it is triggered. Decide whether to continue after the execution result is available.

## Q3: How do I display custom information on the pipeline Build history page

You can add a shell **plug-in** to the pipeline by setting `BK_CI_BUILD_REMARK`The value of the global variable to implement the desired remarks. This field is not displayed until the pipeline ends.

And add a comment field to the pipeline history page. For details, please refer to:

[Use remark variables](../../../../services/pipelines/pipeline-variables/pipeline-variables-remark)

## Q4: Can the variables of the pipeline be linked? For example, the value of variable B changes with variable A

Linkage is not supported yet. If the value does not change, you can set the default value.

## Q5: Can parameter drop-down list values be obtained through a custom interface when pipeline-executed?

Interface customization is not supported

## Q6: Do multiple jobs share a workspace?

If a single build machine (private build machine) is used, multiple jobs share a workspace directory.

If it is a common build machine, each job will have a separate directory under the workspace.

By default, a separate workspace directory is created for each pipeline for both private and public builders.

## Q7: How do I get the URL of the build product

The http://devops.bktencent.com/ms/artifactory/api/user/artifactories/file/download/local?filePath=/bk-archive/ *project* *name* / {BK_CI_P IPELINE_ID}/${BK_CI_BUILD_ID}/{file name of your artifacts}

------
