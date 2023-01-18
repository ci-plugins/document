# Task

A Task, also known as an pipelined plug-in, is usually a single task, such as pulling Git repository code.
Tasks must be included in [Job](javascript:void%280%29). Tasks in the same Job are executed from the top down (except for tasks with advanced process control enabled).

## Custom plug-in
With the development Store, you can develop your own plugins, which currently support Java/Python/NodeJS/Go in four major languages, so start developing your first pipeline plug-in.
## Plug-in version
Each plug-in has version control, and you must specify a version when using the plug-in.
![](../../.gitbook/assets/image%20%2833%29.png)

> Version specifications for plug-ins:>
> * Each time a plugin is added, the default is the latest version of the current plug-in
> * Added plugins, version numbers that include N.latest, The new version will be used automatically
## Common options for plugins
### Advanced process control
With advanced flow control, you can define the running logic of your plug-in.
![](../../.gitbook/assets/image%20%284%29.png)

### plugin output
After each plug-in is run, it produces a series of output variables that, through an effective combination of variables and advanced process control, enable a variety of application scenarios.
![](../../.gitbook/assets/image%20%2816%29.png)

The output field namespace is used to resolve the problem that output field usage conflicts when multiple instances of the same plug-in exist in the pipeline.>
> * There is no need to add a namespace when there are no conflicts
> * After the namespace is changed, the corresponding field must be changed in the subsequent use
## Next you may need
* [Job](job.md)
* [Stage](stage.md)

