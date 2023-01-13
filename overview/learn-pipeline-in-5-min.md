# 5 minutes to read BKCI pipeline
bk-ci can help you quickly implement a continuous delivery pipeline to compile, test, and deploy your application. The following tutorial and documentation guide will show you how to configure and manage a continuous integration, continuous delivery (CI/CD) pipeline in bk-ci.
The following is the complete logic diagram of the pipeline:
![](../.gitbook/assets/image%20%283%29.png)

## Task
That's a single task, like pulling up the GitHub repository code.
## Job
It can run in a built environment, such as macOS; It can also be scheduled as a normal task that does not require a build environment. It has the following features:
* Consists of multiple Tasks\(plugins \)
* If a Task fails, the Job fails and other tasks will not run
![](../.gitbook/assets/image%20%2817%29%20%281%29%20%281%29%20%281%29.png)

## Stage
* Consists of multiple jobs
* Jobs in the same Stage are executed in parallel, and jobs are independent of each other
* When a Job fails, the Stage fails
![](../.gitbook/assets/image%20%2825%29%20%281%29%20%281%29.png)

## Pipeline

* Consists of multiple stages
* Stages under the same Pipeline are executed in serial. If one Stage fails, subsequent stages will not be executed
* When a Stage fails, the Pipeline fails

## Materials and Triggers
Assembly line execution is like cooking, need materials (meters), with materials, can make delicious meals. When you add the plugins (Git, SVN) associated with the pull code library to the pipeline, the pipeline has the material.

It is the trigger mode of pipeline construction, including: manual trigger, timing trigger, code base event trigger and remote trigger.

# other

### output 
When a pipeline build is performed, there will be many outputs, which are classified according to the following dimensions:
* Artifact, as the name implies, is a binary file that is produced after compilation or packaging. It includes an image, a version compression package, an IPA package, an APK package, and so on. Using plug-ins, you can archive artifacts into a specified repository.

* Code inspection report

If you include the CodeCC code review task plug-in in your pipeline, your pipeline will have a code review report page whose data will be refreshed as your pipeline builds.

* Test report
* installer
* Version log
* Documentation

> If you want to share outputs between different jobs, use the Upload and Download plug-ins.
### WORKSPACE 

The working directory on the build machine is the relative directory for all build-machine-related plug-ins to execute. In the following required path plug-ins, the required path is also the relative path in the WORKSPACE.



### node 
Also known as a build machine, in order to compile, test, or deploy your code, you will need to import at least one Agent node into bk-ci, and this number will increase as the team size grows. Depending on the node type, our tasks fall into two categories:

* Runs directly on the node
  When adding a Job, you can import a third-party builder (including macOS, Windows, and Linux) to bk-ci. The pipeline allocates tasks to this builder when the Job is running.

* Runs inside the node's docker

If the operating system of your node is Linux, the ** build resource type ** in the Job Details page has an additional option: Linux build image. If this option is selected, the pipeline will make full use of your node's CPU, MEM, and other dynamic resources after running the Job in the following ways:

* run the docker run command on the node assigned to the Job to start the image

* Mount WORKSPACE to docker for compilation and build

* After the Job is finished, destroy the container and keep the WORKSPACE
  # Next you may need
  Knowing more basic concepts can help you quickly configure pipelinesthat suit your business scenarios:

* [Task](terminology/task.md)

* [Job](terminology/job.md)

* [Stage](terminology/stage.md)

* [Variables](terminology/variables.md)

* [Trigger](terminology/trigger/)

