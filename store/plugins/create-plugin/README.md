# Develop a pipeline plugin

> Before developing a plug-in, enter the plug-in Workbench to initialize a plug-in and determine the unique identity of the plug-in in the platform.
## Table
This is where you can add/publish/remove plug-ins to manage them
### Function area introduction
![](../../../.gitbook/assets/image%20%2844%29.png)

1. Change the resource type
2. Add plug-ins
3. Manage a single plug-in
4. Upgrade, remove, or delete the plug-in shortcut
5. Guide documents and plug-in UI debugging tool entry
### New plug-in
![](../../../.gitbook/assets/image%20%2830%29.png)

1. Sign
   * The unique identifier of the plug-in on the platform. It is recommended to use a readable English identifier related to the function of the plug-in

2. Debug the project
   * During the release of plug-ins, plug-ins can be added to the pipeline under the debugging project to test plug-ins and ensure that their functions meet expectations.
   * It is recommended to add special plug-in debugging projects to avoid service impact during testing.
3. Develop the language
   * Support for plug-in development in four languages:     
     * Java
     * Python
     * Golang
     * Nodejs
### Develop plug-ins
> Once the plug-in is initialized, you can start developing it
* Refer to the development guidelines for the development language
  * [Java Plug-in Development Guide](plugin-dev-guide/java.md)
  * [Python plug-in Development Guide](plugin-dev-guide/python.md)
  * [Golang plugin Development guide](plugin-dev-guide/golang.md)
  * [Nodejs plugin Development guide](plugin-dev-guide/nodejs.md)
### Plug-in private configuration
> Plug-in level sensitive information, such as token, username, password, IP address, and domain name, is not recommended to be directly submitted to the code base and can be managed on the workbench private configuration page

The entry is as follows. After creating the plug-in, you can use the method provided by the SDK to obtain it
![](../../../.gitbook/assets/image%20%282%29.png)

## Next you may need
* [Use store plugin in BKCI](../upload-plugin.md)
