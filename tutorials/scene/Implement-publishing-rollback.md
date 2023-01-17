# Implement publishing and rollback

## Key words: Release, rollback

## Business challenge

For business operation and maintenance, business release and rollback processes are mechanically fixed. Some steps, such as pulling down code for source dependency packaging, can be complex and time-consuming.

## BKCI advantage

BKCI is used to assemble various processes of publishing and rolling back into different plug-ins, and one pipeline connects the whole process of CI/CD to realize business publishing and rolling back operations.

## solution

1. Configure the following pipeline

For reference only

![img](../../.gitbook/assets/scene-Implement-publishing-rollback-a.png)

2. Pipeline configuration

When starting the pipeline, you can select the parameters, such as publish or roll back. If it is rollback, the version number of rollback needs to be specified. We added pipeline parameters to control the version number, rollback version number and rollback operation. The interface has the following options when pipeline execution (here is just an example).

![img](../../.gitbook/assets/scene-Implement-publishing-rollback-b.png)

The plug-in configuration is as follows:

![img](../../.gitbook/assets/scene-Implement-publishing-rollback-c.png)

3. Compile, package and archive

Compile packaging should only be performed at release build time, not at rollback time; We use the BKCI execution condition option to control whether to perform this step. In the red box, we determine whether the pipeline parameter rollback is true. If false, we skip the compile packing step

![img](../../.gitbook/assets/scene-Implement-publishing-rollback-d.png)

4. Publish and roll back

Pipelining custom variables to control which branch executes

![img](../../.gitbook/assets/scene-Implement-publishing-rollback-e.png)

This is just a simple scenario demo, the actual release and rollback steps are much more complicated than this, and the execution process varies from company to company or project to project; Case, for reference only.
