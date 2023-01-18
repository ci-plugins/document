# Common builder

## Q1: What is the pipelining scheduling strategy when there are multiple common builders?

The algorithm preferentially selects the last built machine (affinity). If a resource of the last built machine exceeds the following threshold, the algorithm finds another build machine to perform the build task

```
 Memory threshold: 80% Disk I/O: 85% Disk space: 90%
```

## Q2: Can I change the threshold of the scheduling policy?

Currently, only the memory threshold can be adjusted, and the default value is 80%. That is, when the memory usage of a common builder reaches 80% and other builders have free resources, tasks will be scheduled to other builders. The threshold can be modified by logging in to the BKCI dispatch-docker server and performing the following operations:

```
 The value of # threshold indicates the threshold percentage. The following uses setting the memory threshold to 70% as an example. curl -H 'Accept:application/json; charset="utf-8"' -H 'Content-Type:application/json; charset="utf-8"' -H "X-DEVOPS-UID: Admin - X "POST -- data '{" threshold" : "70"}' http://127.0.0.1:21938/api/op/dispatchDocker/docker/threshold/update
```

## Q3: How does common build mount work?

![img](../../../../.gitbook/assets/image-20220301101202-sxXbU.png)

This service requires the maintenance of an NFS shared storage service. Therefore, it is not recommended and may be removed later

The best way to do this is to package the dependency tool into the image, which has two phases

The job in stage A has a task-A: clone git code and build the package jar

The job in phase B has a task-B: It is to distribute the jar scp built in task-A to the deployment server.

The result is that the workspace of these two phases is not common. The current practice is to put them all into the same Job, so that the production jar files can be built in the same workspace.

By design, if a CI artifact is to be deployed, it has to go to the artifact repository, and using maven for private service is a good idea

## Q4: Common build machine, which systems are supported?

![img](../../../../.gitbook/assets/image-1646103610029.png)

The common builder relies on docker and can only run linux. Currently, it can only run build images based on our bkci/ci:alpine (debian system).

------

## Q5: Can the public builder use its own image?

You can refer to https://docs.bkci.net/store/ci-images

------

## Q6: How do I remove the common builder

Log in to the machine for the BKCI dispatch-docker service and execute`/data/src/ci/scripts/bkci-op.sh list`Get all the public builders and execute`/data/src/ci/scripts/bkci-op.sh del`operation

------

# Private builder

## Q1: What is the scheduling strategy for private build clusters?

If there are multiple private construction machines, a private construction cluster can be formed. After selecting this cluster, the BKCI pipeline selects one of them to build according to a certain algorithm:

**The algorithm is as follows:**

**The highest priority agent:**

1. This builder was used in a recent build task
2. There are currently no build tasks

**agent of the second highest priority:**

1. This builder was used in a recent build task
2. There are currently build tasks, but the number of build tasks does not reach the maximum concurrency of the current builder

**agent of the third priority:**

1. There are currently no build tasks

**agent of the fourth priority:**

1. There are currently build tasks, but the number of build tasks does not reach the maximum concurrency of the current builder

**Lowest priority:**

1. None of them meet the above criteria

------

## Q2: BKCI script starts gradle daemon process and closes it after each build. Is this controlled by devops agent?

![img](../../../../.gitbook/assets/wecom-temp-d4178631b527e498ee7d8a0778c1fb09.png)

Yes. After the BKCI agent completes the build task, all sub-processes started by the agent are automatically stopped. If you do not need to end the sub-processes, set the environment variable set in the bash script before starting the process: set DEVOPS_DONT_KILL_PROCESS_TREE=true`setEnv "DEVOPS_DONT_KILL_PROCESS_TREE" "true"`

------

## Q3: Can the same private builder be used by multiple projects?

Yes. Install the agent in different directories on the private build machine and import the Agent to the corresponding projects.

## Q4: Is it only possible to use private build machines to generate images using docker build?

You are advised to use a private builder. The public builder DinD solution has security risks. Therefore, a private builder is required for mirroring.

If BKCI users are trusted, they can use our delivery team's DinD **solution**
