# Plugin error code specification

## General requirements

* Plugin developers need to subdivide the various scenarios that lead to the failure of plug-in execution, use errorCode to identify, and give detailed descriptions and solutions in the plug-in logs and usage guidelines, so that users can quickly locate and solve problems
* Plugin developers need to categorize the errors that lead to the failure of plug-in execution, specify the error type errorType, used for metrics statistics

## Error type and error code specification

### 1 Plugin error type (errorType)

Reported through the errorType field in the plug-in results.

| errorType | value | meaning | details |
| :--- | :--- | :--- | :--- |
| USER | 1 | User Configuration Error | The user has configured the wrong plug-in parameters in the pipeline, or the user has made a business logic error.
| THIRD\_PARTY | 2 | Third-party system error | Error in calling interfaces of other platforms than bkci, such as: third-party mirroring platform interface error, job platform interface error, weaving cloud upload interface request failure, etc. |
| PLUGIN | 3 | Plugin execution error (default) | Plugin execution logic error, the developer needs to follow up and repair, the plug-in developers are obliged to subdivide PLUGIN error into other types |

Note: Plug-in SDK only provides 1-3 pass value enumeration, plug-in results are not specified within or specify a value other than 1-3, the error type takes the value of 3 (plug-in execution error)


### 2 plugin error code（errorCode）

Reported via the errorCode field in the plugin results.

| Value | Meaning | Details |
| :--- | :--- | :--- |
| 2199001 | Default Error Code | The default error code of the plugin will be used if the plugin developer does not specify an error code. |
| Custom | Plugin developer-defined error codes | Plugin developer-defined specifications used by the team/platform they work for, data metrics that can be used in later plugins/builds |

Note: Plugin error codes help developers define complete and systematic error information for easy problem location and report generation.

