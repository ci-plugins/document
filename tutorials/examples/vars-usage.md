# Example 3 (Pipelining variable use)
* Variable usage type:

  * Global variable references, shell/python/windows variable reference methods

  * Plug-in variable setting methods and cross-plug-in variable references

* Click Trigger to add the variable message
![](../../.gitbook/assets/image-20220301101202-sbynv.png)

* Add stage, select the Python script execution plugin under Job, and use variables via ${message}
![](../../.gitbook/assets/image-20211210111540640.png)

Add shell plug-ins that use variables with ${message}
![](../../.gitbook/assets/image-20211212170436642.png)

Add stage and select windows for the Job type
![](../../.gitbook/assets/image-20211212170545118.png)

Click windows and select the windows Private Builder node
![](../../.gitbook/assets/image-20211212170801357.png)

Add Batch Script plug-in, using %message% to reference variables
![](../../.gitbook/assets/image-20211212171003864.png)

* Plugin method for setting global variables
On the python script execution plugin, use print("setEnv demo test1") to set an environment variable: demo (note: demo variable cannot be used in the current plugin).
![](../../.gitbook/assets/image-20211212171417261.png)

The variable demo is referenced in shell script and batch script plug-ins in the same way that trigger configured variables are referenced
![](../../.gitbook/assets/image-20211212171708729.png)

![](../../.gitbook/assets/image-20220301101202-InSYO.png)

The way windows sets global variables, call:setEnv "test" "testmessage", references the test variable as above
![](../../.gitbook/assets/image-20211212172006260.png)

* Pipeline default global variable
Click any plug-in, and there is a reference variable in the upper right corner. The pipeline defines some variables by default, which can be used directly on the plug-in. The variable reference method is as above
![](../../.gitbook/assets/image-20211212172109877.png)