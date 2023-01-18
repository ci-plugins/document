# Import Windows builder
{% hint style="danger" %}

1. Before hosting, prepare the execution environment: [third-party builder environment preparation](../prepara-agent.md)\*\*\*\*

2. **If your windows build requires you to start the UI program in the pipeline**(e.g. open a browser for automated testing), see [windows agent Startup Solution](run-ui.md)).

3. agent resources are isolated by project. If multiple projects are imported to a third-party builder, import the agent in different projects and install the agent in different directories. (The installation package/installation script for each agent is different)

   {% endhint %}

## Get the Agent package in BKCI
According to [Host your build to BKCI](../) Guide, select Windows, download the Agent package
## Create the agent installation directory on the Windows builder
```text
new-item C:\data\landun -itemtype directory
```

## Decompress and install agent

Decompress the downloaded Agent package to the folder created in the previous step

![](../../../../.gitbook/assets/image%20%2854%29.png)

Run install.bat as an administrator
![](../../../../.gitbook/assets/image%20%2855%29.png)

The above operation installs the agent as a system service, and the startup user of the service is the built-in windows user `system`. In order to read the user environment variables and user directory information during the pipeline process, `need to change the system service startup user to the login user`.

Execute the command `services.msc` to open the windows service management interface, find the service `devops_agent_{agent_id}` (each agent\_id is different, the value of agent\_id can be found in the configuration file `.agent.properties`)

Right-click-&gt; Properties and select `this account` under the login tab

If it's a builder that's in the domain, the account name should be `domain\username`, e.g. `tencent\xxx`; if it's a builder that's not in the domain, the account name should be `.\username`, e.g. `.\admin`, `.\administrator`, `.\bkci`

After entering the password, click the `Confirm` button
![](../../../../.gitbook/assets/image%20%2853%29.png)

Right click -&gt; Restart to restart the service
![](../../../../.gitbook/assets/image%20%2852%29.png)

## Check the status
Open the task Manager, and check whether the devopsDaemon.exe and devopsAgent.exe processes exist, and check whether the startup user name of the two processes is the current login user
## Page import
Click the 'Refresh' button on the build import page and you can see that the agent status changes to 'normal'
