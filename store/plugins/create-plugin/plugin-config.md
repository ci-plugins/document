# Plugin configuration specification

## 1 Description

* Each plugin has a description file named task.json Input fields, output fields, and startup commands are described by the developer in task.json
* describing the input fields, the purpose of which is to allow the user to configure custom parameter values when programming the pipeline.
* description of the output field, which is intended to allow the user to understand the plugin output for use in downstream steps when programming the pipeline
* description of the start command, which is intended to let bkci know how to start the plugin execution
* The description file (task.json) is stored in the root of the plugin codebase
* The content of the description file (task.json) is formatted as json

## 2 task.json data structure details

### The overall structure is as follows

```text
{
    "atomCode": "", # plug-in unique identification, consisting of letters, and plug-in initialization of the specified logo consistent
    "execution": { # the entry point of the execution command

    },
    "inputGroups": [ # input field grouping, optional, after setting, input fields can be displayed by group, support expand and collapse by group

    ],
    "input": { # plugin input field definition

    },
    "output": { # plugin output field definition

    }
}
```

### Detailed explanation of each configuration item 

#### atomCode

* A unique identifier for the plugin, consisting of a letter of the alphabet, consistent with the identifier specified during plugin initialization
* The value format is a string

#### execution 

* Configuration related to the execution command entry
* The value format is an object.
* The value object includes the following attributes.

| Attribute Name | Attribute Description | Format | Remarks |
| :--- | :--- | :--- | :--- |
| packagePath | The relative path of the plugin execution package in the release package | string | required, including the execution package name, the execution package will be found according to this configuration when the release package is downloaded and unpacked |
| language | development language | string | required, such as python, java, etc., and the language specified when the plugin is initialized |
| demands | dependencies | array | optional
| target | execution portal | string | required, usually a command line executable |

#### inputGroups

* Input field grouping, optional, after setting, can display input fields by group, support expand by group put away
* The value format is array.
* Multiple groups can be set, each group uses an object to describe, including the following attributes.

| Property Name | Property Description | Format | Remarks |
| :--- | :--- | :--- | :--- |
| name | groupName | string | required, configured in the groupName of the input field, identifies the group to which the field belongs |
| label | groupName | String | Required, the name of the group that the user sees directly |


#### input

* Input field definition
* Value formatted as an object
* One or more input fields can be configured
* Each input field is identified as a key and the value as an object

**System supports the following UI components**

| Component type | Component name | Remarks | Description of the value obtained by the plugin backend during execution |
| :--- | :--- | :--- | :--- |
| vuex-input | single-line textbox | | string |
| vuex-textarea | multi-line textbox | | string |
| atom-ace-editor | code edit box | | string |
| selector | drop-down box | selectable, not input | string |
| select-input | The input value can be a value that is not in the drop-down list (including variables), and the id that is seen in the box when selected | string ||
| devops-select | select-input | The input value can only be a variable, after checking the box you will see the name | string |
| atom-checkbox-list | checkbox list | | strings, e.g. \["id1", "id2" \] |
| atom-checkbox | checkbox (boolean) | | string |
| enum-input | single-select | | string |
| cron-timer | time picker | | string |
| time-picker | date picker | | string |
| user-input | Person Name Selector | | string |
| tips | hints | support dynamic preview of user input parameters, support hyperlinks | string |
| parameter | Indefinite parameter list | Parameter list support from interface | string |
| dynamic-parameter | variable-parameter | support for getting from the interface, support for multiple columns per row, support for dynamic addition and deletion | string |

If the above components do not meet your needs, please contact bkci customer service.

**Each input field configuration supports the following public attributes**

| Property Name | Property Description | Configuration Format | Remarks |
| :--- | :--- | :--- | :--- |
| label | Chinese name | string | used for display, null allowed (in combination with other fields in the scenario) |
| type | component type | string | required, the platform provides common input components, according to different components have different display |
| default | default value | default value format varies by component | Not required |
| placeholder | placeholder | string | Not required |
| groupName | groupName | string | Not required, the name of the inputGroups defined in the |
| desc | fieldDescription | string | Not required, field description, support for \r\n line feeds |
| required | required | boolean | Not required |
| disabled | editable | boolean | Not required |
| isSensitive | isSensitive | boolean | Not required, sensitive information in the log will not be displayed in plain text |
| rely | Show/hide current fields based on conditions | object | Not required |
| rule | Value validity limit | 0                                        | Not required<br/>The following attributes are supported:<br/>alpha: English characters only, Boolean, true/false<br/>numeric: Only numeric, Boolean, true/false is allowed<br/>alpha_dash: The value can contain English, digits, underscores (_), hyphens (-), Boolean, true, or false<br/>alpha_num: Can contain English and numeric, Boolean, true/false<br/>max: indicates the maximum length of a string, int<br/>min: The minimum length of a string, int<br/>regex: a string of regular expressions |




**rule configuration example:**
```json
// Only letters are allowed, and the string length is 3-7
"rule": {
    "min": 3,
    "max": 7,
    "alpha": true
}

// Regular match for strings that start with a number
"rule": { "regex": "^[0-9]" }
```

**Has personalized properties for different types of components **

**1. Single line text box: type=vuex-input**

* Component properties.
  * inputType: used when the input string is desired to be displayed as\*\*\*\*\*\*\*, the value is password
* Example.
  * Configuration

    ```text
    "fieldName": {
        "label": "password input box",
        "type": "vuex-input",
        "inputType": "password",
        "desc": "XXX"
    }
    ```

**2. Checkbox (boolean): type = atom-checkbox**

* Component properties.
  * text: At this point the label can be set to empty, the corresponding value is true/false
  
* Example.
  * Configuration
  
  ```
  "fieldName": {
      "label": "",
      "default": true,
      "type": "atom-checkbox",
      "text": "required Rebuild",
      "desc": "XXX"
  }
  ```
  
  

**3、Dropdown box/enterable dropdown box：type = selector/select-input/devops-select**

* Component Properties：
  * optionsConf：drop-down box property configuration

    ```text
    "optionsConf": {          # type=selector/select-input/devops-select
        "searchable": false,  # Searchable or not
        "multiple": false,    # Whether it is multiple choice
        "url": "",            # Link to the bkci service, or link to the API for accessing the BK                             Gateway
                                Variables are supported in the link, referenced using {variable name},                               either fields in the current task.json or several built-in variables,                                 such as projectId, pipelineId, buildId
                                
        "dataPath": "",       # The path in the json of the API return body where the option list data is                             located, without this field it defaults to data, example:                                             data.detail.list. use with url
        "paramId": "",        # url returns the field name used for the drop-down list option key in the                             specification, used with url
        "paramName": "",      # url returns the field name used in the specification for the drop-down                               list option label, used with url
        "hasAddItem": true,   # Whether there is an add button (only effective when type=selector)
        "itemText": "Copywriting",   # New button text description (only effective when type=selector)
        "itemTargetUrl": "to url"    # Click on the jump address of the add button (only effective when                                      type=selector)
    }
    ```
  
    * bkci-Service links, you can use the browser developer assistant to grab, commonly used links are as follows:
      * ticket： /ticket/api/user/credentials/{projectId}/hasPermissionList?permission=USE&page=1&pageSize=100&credentialTypes=USERNAME\_PASSWORD
        * credentialTypes  [CredentialType](https://github.com/Tencent/bk-ci/blob/master/src/backend/ci/core/ticket/api-ticket/src/main/kotlin/com/tencent/devops/ticket/pojo/enums/CredentialType.kt)
      * code-base：/repository/api/user/repositories/{projectId}/hasPermissionList?permission=USE&repositoryType=CODE\_GIT&page=1&pageSize=5000
        * repositoryType  [ScmType](https://github.com/Tencent/bk-ci/blob/master/src/backend/ci/core/common/common-api/src/main/kotlin/com/tencent/devops/common/api/enums/ScmType.kt)
      * node：/environment/api/user/envnode/{projectId}/listUsableServerNodes?page=1&pageSize=100
  
  * options：Drop-down list item definition
  
    ```text
    "options": [ # type=selector/select-input component options list
        {  
            "id": "", # option ID
            "name": "", # option name
            "desc": "", # option description
            "disabled": false # optional or not
        }
    ]
    ```

**4、Single choice： type = enum-input**

* Component Properties：

  * list

  ```text
  "list": [                 # type=enum-input组件选项列表
        {
            "label": "",
            "value": ""
        }
    ]
  ```

**5. Date picker: type=time-picker**

* Component properties.
  * startDate: timestamp, milliseconds, start date
  * endDate: timestamp, milliseconds, end date
  * showTime: boolean, whether to show the time

**6. hint-message: tips**

* Component properties.
  * tipStr: tip message content template
  * Support {} reference to other variables of the current plugin
  * Support inserting hyperlinks
* Example.
  * Example configuration.

    ```text
    "tipTest": {
         "label": "",
         "type": "tips",
         "tipStr": "This is a XXX system, welcome to experience it. [click to view](http://www.baidu.com)"
    }
    ```

**7. Indefinite parameter list: parameter**

* Component properties.
  * paramType: data dynamically obtained from the link or from the definition of the list, optional values are: url, list
  * url: paramType=url when configuring the link
  * urlQuery: value for the object, url parameter settings such as: {"param1": "", "param2": ""} param1, param2 can be other parameters of the current plug-in, the implementation will automatically replace the value
  * parameters: a list of parameters, you can define one or more parameters Each parameter contains the following properties

   | Property Name | Property Description | Format | Remarks |
    | :--- | :--- | :--- | :--- |
    | id | the unique identifier of the row | string | the unique identifier of the row |
    | key | the value of key | string | the key of the row's parameter |
    | keyType | the type of key | string | optional values for input, select |
    | keyListType | type of key data source | string | valid when keyType=select, optional values are url, list |
    | keyUrl | | string | valid when keyListType=url |
    | keyList | | list | keyListType=list, example: \[ { id: 'id', name: 'name' } \ ], id is the specific value of the key |
    | keyDisable | whether to edit | boolean | true, false |
    | keyMultiple | whether multi-selectable | boolean | true, false |
    | value | the value of the value | string | the value of the line parameter |
    | valueType | the type of value | string | optional values for input, select |
    | valueListType | type of value data source | string | valid when valueType=select, optional values are url, list |
    | valueUrl | | string |valid if valueListType=url |
    | valueList | | list | valueListType=list, example: \[ { id: 'id', name: 'name' } \ ], id is the specific value of value |
    | valueDisable | whether to edit | boolean | true, false |
    | valueMultiple | whether multi-selectable | boolean | true, false |

**8、Checkbox list： type=atom-checkbox-list**

* 组件属性：
  * list

    ```text
    "list":[
    {
        "id":"php"
        "name":"php"
        "disabled":true
        "desc":"python is the best language in the world"
    }]
    ```

**9. Code edit box: atom-ace-editor**

* Component properties.
  * bashConf
  * lang

    ```text
    "bashConf": {
        "url": "XXX", # Third-party link that has access to the BK gateway
        "dataPath": "" # as data.name
    },
    "lang": "sh" # currently supports highlighting syntax json|python|sh|text|powershell|batchfile
    ```

**10. Person name selector: user-input**

* Component properties.
  * inputType: the type of data that can be entered, the optional values are email , rtx , all

    ```text
    "receiver2": {
        "label": "Recipient, support mail group",
        "type": "company-staff-input",
        "inputType": "all",
        "desc": "Can fill in any user of the company, including mail groups"
    }
    ```

11, **dynamic-parameter component: dynamic-parameter**

* Component properties

```text
"params":{
  "label": "dynamic-parameter",
  "type": "dynamic-parameter",
  "required": false,
  "desc": "dynamic-parameter component",
  "param": {
    "paramType": "url", // parameters are obtained from the url or directly from the value of the list, either url or list
    "url": "XXXX",      // paramType is the url when the value is taken from the interface, the {test} in the url can be replaced with the value in the current plugin or the parameters in the browser url
    "dataPath": "",     // Interface return value, path to fetch number, default is data.records
    "parameters": [     // When paramType is a list, the value is taken from here
        {
            "id": "parameterId", //Unique identifier for the row, required
            "paramModels": [
                {
                    "id": "233",     // Unique identifier for the model, required
                    "label": "testLabel",
                    "type": "input", // Can be input or select
                    "listType": "url", // Get the list method, either url or list
                    "isMultiple": false, // select whether to multi-select
                    "list": [ { "id": "id", "name": "name" } ], // type is select works, need to have id and name fields
                    "url": '', // type is select and listType is url works
                    "dataPath": "",     // Interface return value, path to fetch number, default is data.records
                    "disabled": false, // Controls are editable or not
                    "value": "abc=" // value, which can be used as the default value for initialization
                }
            ]
        }
    ]
  }
}
```

Example of data passed to the plugin backend during execution.

\[{"id":"parameterId","values":\[{"id":123,"value":"3d029fbe08c011e99792fa163e50f2b5,${abc}"},{"id":1233,"value":"ab"},{"id":1235,"value":"id"}\]}\]

12、**Simplified version of dynamic-parameter component: dynamic-parameter-simple**

* Component Properties

| Property Name | Property Description | Required | Format | Remarks | 
| :--- | :--- | :--- | :--- | :--- |
| rowAttributes[N].id | The unique ID of the attribute, | Required | Yes | String | 
| type | optional: ["input", "select"] | yes| String| When using "select", the rowAttributes[N].options item is required | 
| rowAttributes[N].options| Dropdown box options on the page| Yes| Array Of Instance Option | when rowAttributes[N].type is "select". 
| rowAttributes[N].options[M].name| The value to display on the page| When rowAttributes[N].type is "select", then yes | String | 
| id | the actual selected value | when rowAttributes[N].types is "select", then yes | String | 

* demo
```
{
  "input": {
    "input_dynamic_parameter_simple": {
      "label": "dynamic-parameter (simple version)",
      "type": "dynamic-parameter-simple",
      "parameters": [
        {
          "rowAttributes": [
            {
              "id": "ip", # Unique ID for this attribute, required
              "label": "IP",
              "type": "input", # optional values: ["input", "select"], if "input" is used, then "options" is not filled
              "placeholder": "IP",
              "desc": "IP information",
              "default": "8.8.8.8"
            },
            {
              "id": "protocol_port",
              "label": "protocol\\port",
              "type": "select", # Optional: ["input", "select"], if "select" is used, it must have "options"
              "options": [ # When type is "select", then must be filled
                {
                  "id": "80", # the actual value selected
                  "name": "HTTP\\80" # The value to be displayed on the page
                },
                {
                  "id": "443", # The actual value selected
                  "name": "HTTPS\\443" # The value displayed on the page
                }
              ],
              "desc": "protocol\\port"
            }
          ]
        }
      ],
      "desc": "Dynamic Parameters (Easy Version) Input Example"
    }
  }
}

```

Features supported by ####

* Show/hide the current field based on conditions
* Example configuration.

```text
"rely": { # Show/hide current field configuration based on conditions
    "operation": "AND", # multi-conditional with/or, optional: AND/OR
    "expression": [ # condition list
        {
            "key": "", # Conditional field name
            "value": Any # Conditional field value
        }
    ]
}
```

### output
#### Output field definition

* Value formatted as an object
* One or more output fields can be configured
* Each output field has an English identifier of key and a value of object
* Each output field definition contains the following attributes.

| Property Name | Property Description | Format | Remarks |
| :--- | :--- | :--- | :--- |
| type | The type of the output field | string | Required. The following three types are supported: string: String artifact: Output file, which will be automatically archived to the repository report: Custom report html, which will be automatically stored and rendered in the output report screen |
| description | description | string | not required, description |
| isSensitive | isSensitive | isBoolean | non-required, whether is sensitive information |

## 3. Input component configuration example

* vuex-input

```text
"fieldName": {
    "label": "version number",
    "type": "vuex-input",
    "desc": "tertiary version number, ex: 1.0.1",
    "required": true
}
```

* Person Name Selector

```text
"fieldName": {
    "label": "reciver",
    "type": "user-input",
    "desc": "Only current project members can be filled in"
}
```

* atom-checkbox

```text
"fieldName": {
    "label": "",
    "type": "atom-checkbox",
    "text": "Is Rebuild required",
    "desc": "XXX"
}
```
* selector/select-input/devops-select
  * The list of options is configured in task.json

    ```text
    "fieldName":{
        "label": "input-field-name",
        "type": "selector",
        "options":[
            {
                "id": "video",
                "name": "video"
            },
            {
                "id": "website",
                "name": "website"
            }
        ]
    }
    ```

  * The list of options is obtained from the interface
    * Configuration specification: specified by optionsConf's url, paramId, paramName, dataPath

      ```text
      "optionsConf": {
            "url": "", # API link to get the options list data
            "dataPath": "", # the path to the API json where the options list data is located, without this field it defaults to data, example: data.detail.list
            "paramId": "", # the id field name of each option data
            "paramName": "" # the name field of each option data
        }
      ```

      * The url supports two types.
        * bkci built-in services
        * Third-party API for accessing the BK Gateway
      * url return specification: return json format data

        * status: whether the operation is successful, 0 success, non-0 failure
        * data: option list data. Support specifying the path, such as data.detail.list
        * optionId and optionName fields in data are not mandatory, they correspond to the paramId and paramName in the configuration.
        * message: error message when status is not 0

        ```text
        {
            "status": 0,
            "data": [
                {
                    "optionId": "",
                    "optionName": ""
                }
            ]
        }
        ```

      * demo

      ```text
      "fieldName":{
            "label": "enter filed name",
            "type": "selector",
            "optionsConf": {
                "url": "http://xxx-test.com/prod/testnet",
                "paramId": "optionId",
                "paramName": "optionName"
            }
        }
      ```
* atom-checkbox-list Checkbox list

```text
"fieldName":{
    "label": "checkbox-list",
    "type": "atom-checkbox-list",
    "list": [
        {
            "id": "php",
            "name": "php",
            "disabled": true,
            "desc": "php is the best language in the world"
        },
        {
            "id": "python",
            "name": "python",
            "disabled": false,
            "desc": "python is the best language in the world"
        }
    ]
}
```

* time-picker date picker

```text
"fieldName":{
    "label": "date picker",
    "type": "time-picker",
    "startDate": 1559555765,
    "endDate": 1577894399000,
    "showTime": false
}
```

* tips tips message

```text
"tipTest": {
      "label": "",
      "type": "tips",
      "tipStr": "This is a XXX system, welcome to experience it. [click to view](http://www.baidu.com)"
}
```

* parameter indefinite parameter list

```text
"params":{
  "label": "Sub pipeline parameters",
  "type": "parameter",
  "required": false,
  "desc": "Run parameters to bring into the sub-pipeline",
  "param": {
    "paramType": "url", // whether the parameters are obtained from a url or directly from a list, either url or list
    "url": "XXXX", // paramType is url when fetching values from the interface
    "urlQuery":{
      "projectId": "", "subPip": ""
    },
    "parameters": [ // take value from here if paramType is list
      {
        "id": "parameterId", // unique identifier for the line
        "key": "abc",
        "keyDisable": false, // controls whether it is editable
        "keyType": "input", // can be input or select
        "keyListType": "url", // the way to get the list, can be url or list
        "keyUrl": "", // type is select to work
        "keyList": [ { "id": "id", "name": "name" } ], // type is select role, need to have id and name fields
        "keyMultiple": false, // whether select is multi-select
        "value": "ddd",
        "valueDisable": false,
        "valueType": "input", // can be input or select
        "valueListType": "url", // the way to get the list, can be url or list
        "valueUrl": "", // type is select to work
        "valueList": [ { "id": "id", "name": "name" } ], // type is select
        "valueMultiple: false // whether select is multi-select
      }
    ]
  }
}
```

* enum-input single-select radio

```text
"fieldName_1":{
    "label": "radio",
    "type": "enum-input",
    "list": [
        {
            "value": "php",
            "label": "php"
        },
        {
            "value": "python",
            "label": "python"
        }
    ]
}
```

## 4. Field show/hide configuration based on conditions

* Specified by the rely attribute in the input field definition. rely has two attributes.
  * operation: the relationship between multiple conditions, with, or, or not
  * expression: conditional expression
* The operation field supports three values.
  * AND
  * OR
  * NOT
* Exact match is supported, when the expression attribute is
  * key: the English name of the field
  * value: field value
* Supports regularity, where the expression attribute is
  * key: English name of the field
  * regex: regular expression
* Example.

Show the current field when the value of inputField\_1 is true and the value of inputField\_2 ends with .apk, otherwise hide the current field

```text
"fieldName":{
    ...
    "rely": {
        "operation": "AND",
        "expression": [
            {
                "key": "inputField_1",
                "value": true
            },
            {
                "key": "inputField_2",
                "regex": ".*\\.apk$"
            }
        ]
    }
    ...
}