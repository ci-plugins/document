# Pipeline condition judgment

* Create multiple stages

  ![](../../.gitbook/assets/image-20211215150951360.png)

To add a shell script plug-in, enter any script: echo 1

![](../../.gitbook/assets/image-20211226153407230.png)

Add a parallel stage

&#x20;
![](../../.gitbook/assets/image-20211226153240321.png)



![](../../.gitbook/assets/image-20220301101202-tfPup.png)



add  a new stage

![](../../.gitbook/assets/image-20211226153714984.png)



![](../../.gitbook/assets/image-20211226153730961.png)

Add a finally stage
Finally stage: The last step in the pipeline execution. The steps defined in the finally stage are executed whether the pipeline execution fails or succeeds

![](../../.gitbook/assets/image-20211226153811917.png)



![](../../.gitbook/assets/image-20211226153848275.png)

* Scenario: After the preceding pipeline is configured, if a service requirement exists, only 2-1 jobs are executed and 2-2 and 3-1 are skipped if certain conditions are met
  Achieved by configuring variables
  
  * To define pipeline variables, click trigger and define test1 and test2
    
    ![](../../.gitbook/assets/image-20220301101202-yFjnM.png)
  
* Configure Job 2-1, select 【Run only when all user-defined variables are met】, and enter two user-defined variables, test1 and test2, whose values are the same as those defined by trigger

  ![](../../.gitbook/assets/image-20220301101202-aLqEe.png)

* Configure Job 2-2, click 2-2 Linux, select 【Run only when all user-defined variables are satisfied】, enter the two variables test1 and test2 that have just been customized, and write the values as you like, which are different from those defined by the trigger just now

  ![](../../.gitbook/assets/image-20211226154729382.png)

* Configure the 3-1 stage, select 【Run only when all user-defined variables are satisfied】, input the two variables test1 and test2 that have just been customized, and write the values arbitrarily, which are different from those defined by the trigger just now
  Note: Pipelining can be configured for stage/Job/ plug-in execution conditions

  ![](../../.gitbook/assets/image-20211226154952271.png)

* start pipeline, test1 and test2 variables with default values

  ![](../../.gitbook/assets/image-20211226155258274.png)

View the execution result. You can see that 2-2Job and stage3 are skipped because variable conditions are not met

![](../../.gitbook/assets/image-20211226155240606.png)