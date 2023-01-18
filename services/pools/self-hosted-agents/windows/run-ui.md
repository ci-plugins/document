# windows agent startup interface program solution
BKCI The third-party builder windows agent starts as a system service by default. When programs with UI are started through the agent, errors are reported or the interface is not visible
Cause: All processes started by the Windows Service run in Session0. Session0 cannot display information or UI Windows to desktop users.
In this case, you can start the agent in another way as follows:
1. If the agent has been installed as the system service, run uninstall.bat to uninstall the agent service

2. Double-click devopsDaemon.exe to start the agent. Do not close the pop-up window
  {% hint style="info" %}
  The agent started in this mode does not have the startup function.
  After the agent finishes the build task, all child processes started by the agent are automatically stopped. If you dont need to end the child processes, set the environment variable before starting the process: set DEVOPS\_DONT\_KILL\_PROCESS\_TREE=true

  {% endhint %}

