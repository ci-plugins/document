# Job

Job, which can run in a build environment, such as macOS; It can also be scheduled as a normal task that does not require a build environment. It has the following features:

* Consists of multiple Tasks\(plugins\);
* If a Task fails, the Job fails and other tasks will not run.

  ![](../../.gitbook/assets/image%20%2817%29%20%281%29%20%281%29.png)

## WORKSPACE

Each Job has its own WORKSPACE, which is the root directory of all plug-ins in the Job.
> If a Job contains the "pipeline call" plug-in, the WORKSPACE of the Job in this pipeline is independent and does not conflict with the WORKSPACE of the parent pipeline.
## General Options for Jobs

### Flow control options 

Advanced flow control enables you to define the running logic of a Job.
![](../../.gitbook/assets/image%20%285%29.png)

### exclusive group
The exclusive group is designed to solve the resource conflict problem of concurrent construction using the same builder. The same exclusive group is set for different jobs of different pipelines.
![](../../.gitbook/assets/image%20%2812%29.png)

Next you may need
* [Task](task.md)
* [Stage](stage.md)

