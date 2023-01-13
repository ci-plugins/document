# Use the store plugin in BKCI
> After the plug-in is developed, the plug-in is published to the R&D Store through the R&D store workbench for users to add to the pipeline.
## entry
In the workbench list, click the following entry to initiate the publication process:
![](../../.gitbook/assets/image%20%2821%29.png)

1. When it was first released, the entry was called "On Shelves"
2. When upgrading the version, the entry name is Upgrade.
    Or in plugin release management -&gt; Release process initiated by the version management interface:
    ![](../../.gitbook/assets/image.png)
    1. If the current version is not in the end state, possible operations are as follows:
       * Launch: The first version enters the launch process
       * Progress: The release process page is displayed
    2. You can add a new version only when the latest version is in the terminal state
## Fill in plug-in related information / upload plug-in release package

   You can modify the basic information of the plug-in when you install or upgrade the plug-in, as shown below:
   ![](../../.gitbook/assets/image%20%2836%29.png)

![](../../.gitbook/assets/image%20%2828%29.png)

1. Applicable Job Type:
   * This parameter corresponds to the pipeline Job type. Select this parameter based on the plug-in's actual application
   * If incorrect, you need to add a new version
2. Release Package:
   * The atomCode in task.json must be the same as the identifier entered when adding a plug-in in [create-plugin/]; otherwise, the upload will fail

When upgrading plug-ins, there are three upgrade modes:
     ![](../../.gitbook/assets/image%20%289%29.png)
1. Incompatible upgrade:
   * Used when the plug-in input and output are different or the same input and output but the functional logic has changed significantly and is incompatible with the older version
   * After this version is released, the pipeline that has used this plug-in will not automatically upgrade the version. You need to manually change the version number
   * Major version number +1
2. Compatible function update:
   * The input and output of the plug-in are compatible with older versions, and can only be used when the function is updated or newly added \(does not affect existing users \)
   * After this version is released, the pipeline that uses the plug-in and version number is \[major version.latest] automatically uses the new version of the plug-in without manually editing the pipeline
   * Minor version number +1
3. Compatible problem correction:
   * Plug-in I/O compatible with older versions, only do problem fixing
   * After this version is released, the pipeline that uses the plug-in and version number is \[major version.latest] automatically uses the new version of the plug-in without manually editing the pipeline
   * Correction sign +1
## Test/release plugin
> Fill in the information, submit, enter the release process, you can test -&gt; Repacket -&gt; Test until the plug-in meets expectations, then manually continue the process of releasing the plug-in to the development store
![](../../.gitbook/assets/image%20%2829%29.png)

1. Test: Click and jump to the pipeline service of plug-in debugging project. You can add the current plug-in to the pipeline to verify whether UI and functions meet expectations
2. Retransmit packets: If a problem is found in the test, upload the released package again and perform the test again
3. Continue: After the test is OK and the expectation is met, confirm the submission and release
4. Cancel the release: You can terminate the release at any time during the release process
> Note: When the plug-in development language is Python or Nodejs, the plug-in execution environment has certain requirements. For details, see [Preparations for the Third-Party Builder Environment](../../services/pools/self-hosted-agents/prepara-agent.md)
