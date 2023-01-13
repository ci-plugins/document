# Pipelined trigger mode - manual/scheduled task/remote trigger 
The Trigger mode is used by selecting different types of plug-ins under the trigger

* Manual execution
The default way to create a pipeline is manually executed, so simply add a stage\
Manual plug-in: manual execution pipeline. After the pipeline is established, click Save in the upper right corner and manually click the button of execution pipeline
![](../../.gitbook/assets/image-20211209205014251.png)

* Scheduled task
Add the Timer plug-in and define crontab expressions
![](../../.gitbook/assets/image-20211209211036492.png)

Because the Manual triggering mode is not selected, the "Execute" button cannot be clicked manually to execute the pipeline
![](../../.gitbook/assets/image-20211209211118734.png)

Viewing the execution history, you can see that the pipeline automatically executes once per minute
![](../../.gitbook/assets/image-20211209211239418.png)

* Remote trigger
Add a Remote plug-in -- This can be triggered remotely by executing commands
Copy the example command. If the trigger has defined variables, the command line automatically generates an example with variable parameters
![](../../.gitbook/assets/image-20211209211650003.png)

Run the curl command on the CLI
![](../../.gitbook/assets/image-20220301101202-tNslA.png)

You can view the execution history of the pipeline
![](../../.gitbook/assets/image-20211209211547148.png)