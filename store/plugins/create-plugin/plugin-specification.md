# Plug-in development specification

## Plug-in definition specification
* The basic information of the plug-in description class is defined through the online process

  * When you add a plug-in to the plug-in workbench, you can specify the identity, name, and development language
    * The identity and development language cannot be changed after initialization

  * The basic information of the plug-in can be updated when the plug-in is put on the shelf/upgraded, including the name, classification, description and other information

* Plug-in execution, input, and output definitions are defined in a file named task.json in the plug-in codease

  * task.json is stored in the root path of the plug-in codebase
  * See [Plug-in Configuration Specification](plugin-config.md) for details.
## Plug-in development specification
* Plug-ins are packaged as command-line executable commands:

    * The call-up command is specified by the `execution.target` field of task.json
      * execution.target is a string
      * ${var\_name} can be used to retrieve variables in the call up command

    * Installation demands are specified by the `execution.demands` field of task.json if a dependency needs to be installed before execution
      * execution.demands is a list. Multiple installation commands can be configured
      * The installation command can use ${var\_name} to get variables

* Plug-in input field value, obtained from the specified input file

    * Input information file name, specified by the environment variable `bk_data_input`
    * Path to the input information file, which is specified by the environment variable `bk_data_dir`
    * The input information file is json, as shown in the following example:

    ```text
    {
        "inputVar_1": "value1",
        "inputVar_2": "value2"
    }
    ```

    * When using the SDK for development, you do not need to pay attention to the location and name of the input file. You can use the methods provided by the SDK to obtain the input

* bkci agent is notified of plug-in output by writing files

    * File name of the output information, specified by the environment variable `bk_data_output`
    * Path for storing the output information file, specified by the environment variable `bk_data_dir`
    * Output information file format, See [plug-in output specification](vscode webview - resource: //c9 cf071b 83-05 d8-44-934 f - 26 f3182c6000 /file ///Users/zhaozhihui/Downloads/ci - plugins - w iki/specification/plugin_output.md)
    * When using the SDK for development, you do not need to pay attention to the location and name of the output file. You can use the methods provided by the SDK to set the output

* Plug-in execution results are determined by two policies:

    * If the 'status' field is specified in the output information file, the value of the field shall prevail
    * If no output information file is specified, the value returned by the plug-in command shall prevail
      * If the return value is 0, success is indicated
      * If the return value is not 0, it indicates failure

* Plug-in log output to the console

    * bkci agent displays the collection console logs (standard output stream, standard error stream) to the pipeline foreground

* Plug-in level sensitive information management

    * Sensitive data such as account password can be managed in the plug-in Settings → Private Settings interface
      * The platform will be encrypted and stored
      * When used in the plug-in, you can obtain it through the methods provided by the SDK

* Plug-in error codes and error categories

    * The plug-in developer needs to subdivide the scenarios that cause plug-in execution failures, use the errorCode to identify them, and provide detailed descriptions and solutions in the plug-in logs and user guides, so that users can quickly locate and solve the problems
    * The plug-in developer should classify the errors that cause the plug-in to fail and specify the error type errorType for measurement statistics
## Plug-in code base management specification
You are advised to manage plug-in codes in a unified manner to facilitate sharing, handover, and system-level management.
* Enterprise internal management in accordance with the enterprise code management, unified management under a group
* Open source general plug-ins can be submitted to the bkci open source plugins group [ci-plugins](https://github.com/ci-plugins) by contact with bkci customer service
## Plug-in Help Documentation (detailed description) specification
* Purpose
  * It is convenient for users to understand the working principle and application scope of the plug-in
  * Convenient for users to obtain solutions when they encounter problems
* Way of provision
  * When publishing a plug-in, enter the plug-in description field
  * The plugin details screen will be displayed in the R&D store, or the log view help will be performed.
* Use the document **Write in markdown language**. It is recommended to include the following contents:
### 1. Plug-in introduction
* A brief description of the plug-in's functions
### 2. Plug-in application scenarios
* Describes the plug-in application scenarios in detail
### 3. Plug-in usage restrictions and restricted solutions
* \[Optional \] Call frequency limit
* \[Optional \] Concurrency limit
* \[Optional \] Network restrictions, stating network requirements, or network policies to apply
* \[Optional \] If the plug-in has permission control (IP, user, etc.), describe the application method in detail
### 4. Common plug-in failure reasons and solutions
* Lists possible failure causes and error codes, and provides solutions based on the scenarios to help users quickly resolve the problem
## Plug-in addition/release process
### plug-in state flow diagram
![](vscode-webview-resource://83cf071b-05d8-44c9-934f-26f3182c6000/file///Users/zhaozhihui/Downloads/ci-plugins-wiki/assets/status.png)

### Process description
* Developers add plugins to the plugin workbench

  * The purpose of initialization is to get the unique plug-in ID in the system

* Developers develop debugging plug-ins locally

* Developers debug OK, add a new version in the plug-in workbench, start the release process

* After version submission:

  * Enter the testing phase
    * Developers can create a test pipeline under the debug project selected when adding a plug-in to determine whether the plug-in meets expectations
    * During the testing process, if you find problems, you can fix the code bug and re-pack it, and then re-transmit the package to continue the testing

  * After the test is OK, the developer will click "Continue" to confirm, and the version will be successfully released to the R&D store
