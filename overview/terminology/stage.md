# Stage

In order to describe the CI process more clearly, we introduce the concept of Stage.
* Consists of multiple Jobs (jobs);
* The execution mode of a Job at the same Stage is parallel. Because jobs are independent from each other, when a Job fails, other jobs will be run to completion.
* If a Job fails, the Stage fails.
![](../../.gitbook/assets/image%20%2825%29%20%281%29%20%282%29.png)

## Generic option for Stage

### Fastkill

After Fastkill is enabled, the current Stage ends immediately when the Job fails.
### Process control options
Advanced flow control enables you to define the running logic of a Job.
![](../../.gitbook/assets/image%20%2843%29.png)

## Next you may need
* [Task](task.md)
* [Job](job.md)

