# Plug-in output specification

* After the plug-in is executed, it supports passing output variables to the downstream steps of the pipeline, or archiving files to warehouses, and archiving reports to output reports
* The output information is specified by how the file was written, and the file path and name are specified by system-defined environment variables
* The format of the output information is described as follows:
```text
{
    "status": "", # the result of the plugin execution, the value can be success, failure
    "message": "", # Description of the plugin execution result, support markdown format
    "errorType": 3, # plug-in error type, int, 1 means user usage (parameters are not legal, etc.), 2 means dependency on third-party platform problems, 3 means plug-in logic problems
    "errorCode": 0, # plugin error code, int, used for subsequent analysis of the quality of the plugin based on the error code
    "type": "default", # output data template type, used to specify the output data parsed into the library. Currently supports default
    "data": { # default template data format as shown below, each output field should be defined in task.json first
        "outVar_1": {
            "type": "string",
            "value": "testaaaaa"
        },
        "outVar_2": {
            "type": "artifact",
            "value": ["file_path_1", "file_path_2"] # absolute paths to files, when specified, the agent automatically archives these files to the repository
        },
        "outVar_3": {
            "type": "report",
            "reportType": "", # report type INTERNAL built-in report, THIRDPARTY third-party link, default is INTERNAL
            "label": "", # Report alias, used to identify the current report in the output reporting interface
            "path": "", # The absolute path where the report directory is located when reportType=INTERNAL. Note that when planning the report path, all contents of the directory will be considered as report associated files to be archived together
            "target": "", # If reportType=INTERNAL, the name of the report entry file
            "url": "" # When reportType=THIRDPARTY, the report link, used when the report can be accessed via url
        }
    }
}
```

* Three types of data are supported in the output data:

  * string: indicates a character string
    * The length cannot exceed 4k characters

  * artifact: A component
    * Multiple components are supported
    * Each artifact specifies the local absolute path

  

  * report: report
    * There are two types of reports: built-in reports and third-party links
    * It is not recommended that report files be directly placed in the root directory. If other files in the root directory, such as code libraries, will upload all files as related to the report. It is recommended to create a directory to save the file, for example, path=${WORKSPACE}/report, target=result\_report.html
