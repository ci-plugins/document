# Known problem

#### Q: User groups and user-defined permissions overlap. As a result, user permissions on the pipeline do not meet expectations. ci <1.7

#### **Version: ci<1.7**

Occasional/obligatory: Obligatory

Description: The user group to which the user belongs has all permission for the test project, and the user-defined permission has some pipeline permission for the test project. When the pipeline page is displayed, the pipeline may fail to **be** viewed

![可以查看流水线](../../.gitbook/assets/image-20220301101202-Tnoda.png)You can look at the pipeline

![无法查看流水线](../../.gitbook/assets/image-20220301101202-SOWdg.png)Unable to view pipeline

**Q: gitlab occasionally fails to obtain credentials**

![img](../../.gitbook/assets/wecom-temp-941115d684647ac6fe940676a7854656.png)

A known problem **affects version <=1.5.23**

Delete the ticket/lib/bcprov-jdk15on-1.64.jar package and restart the ticket service`systemctl restart bk-ci-ticket.service`

**Q: I want to upload the unit test report as the output report successfully. However, when the report is opened, it cannot be displayed normally. Error "This request has beenblocked; the content must be served over https" is displayed.**

![img](../../.gitbook/assets/wecom-temp-76f4802ef5f78b0abfda917c2575106a.png)

Known problem, **affected Version: 1.5.x**

**Q: Three pipeline instances are created using the template, but three instances are displayed after one is deleted. The template cannot be deleted even after all instances are deleted**

![img](../../.gitbook/assets/企业微信截图_16389525588929.png)

![img](../../.gitbook/assets/企业微信截图_16389527024197.png)

Known problem, scope of impact: Version <**1.5.x**

It was fixed in v1.7

**Q: If a code analysis task created through the pipeline is stopped after the pipeline is deleted, an error message is displayed**

![img](../../.gitbook/assets/image-20220301101202-nkPoi.png)

![img](../../.gitbook/assets/企业微信截图_16395354744740.png)

Known problem, scope of impact: **Version 1.5.x**

**Q: Blue Shield logs are generated in a disorderly sequence**

![img](../../.gitbook/assets/企业微信截图_16316936739387.png)

Known problem, scope of impact: **Version 1.5.x**

**Q: When Blue Shield pipeline applies for permission, click "Apply", but the page does not go to the permission center. F12 displays an error message indicating bkiam v3 failed**

![img](../../.gitbook/assets/企业微信截图_16384143961812.png)

![img](../../.gitbook/assets/企业微信截图_16384146286005.png)

Known problem, scope of impact: **Version 1.5.x**

**Q: The TGit plug-in is not allowed in the project. Please check whether the plug-in is installed correctly**

![img](../../.gitbook/assets/image-20220125154003687.png)

Known problems, TGit docking is Tencent's worker bee, the use of community version is limited, **affected version <1.5.35**

------
