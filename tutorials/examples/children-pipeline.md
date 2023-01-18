# Call sub-pipeline

children-pipeline: Other pipelines under the project can be called from the current pipeline
* New stage

  ![](../../.gitbook/assets/image-20211218153126542.png)

* Select call pipeline plug-in, here select the call pipeline as [children-pipeline demo], and also execute synchronous and asynchronous calls, and fill in the variable parameters of the children-pipeline

  ![](../../.gitbook/assets/image-20211218153213103.png)



![](../../.gitbook/assets/image-20211218161418247.png)

* Added shell script plugin, sleep 20s

  ![](../../.gitbook/assets/image-20211218161316700.png)

* children-pipeline demo, perform sleep 10 operations

  ![](../../.gitbook/assets/image-20211218161541806.png)

* Pipeline-execution, the call pipeline succeeds immediately after calling the children-pipeline, and then executes the next operation, while the children-pipeline demo asynchronously executes (if synchronous, waits for the children-pipeline to complete before executing the next operation).

  ![](../../.gitbook/assets/image-20211218161727205.png)



![](../../.gitbook/assets/image-20220301101202-Azved.png)