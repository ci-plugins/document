# python_atom_sdk interface guidelines

## sdk Code Structure
```text
python_atom_sdk
├── __init__.py # interface exposed by sdk
├── bklog.py # logging related
├── const.py # constants
├── input.py # Parsing user input
├── openapi.py # Calling the openapi interface
├── output.py # Set the output
├── setting.py # configure
```
The main focus is on `__init__.py`, the functions needed to develop the plugin are defined in this file

## \_\_init\_\_.py
```python
# -*- coding: utf-8 -*-

from .bklog import BKLogger, getLogger
from .input import ParseParams
from .output import SetOutput
from .const import Status, OutputTemplateType, OutputFieldType, OutputReportType, OutputErrorType

log = BKLogger()
parseParamsObj = ParseParams()
params = parseParamsObj.get_input()
status = Status()
output_template_type = OutputTemplateType()
output_field_type = OutputFieldType()
output_report_type = OutputReportType()
output_error_type = OutputErrorType()


def get_input():
    """
    @summary: get Plugin input parameters
    @return dict
    """
    return params


def get_project_name():
    """
    @summary: get project.name
    """
    return params.get("project.name", None)


def get_project_name_cn():
    """
    @summary: get project chinese name
    """
    return params.get("project.name.chinese", None)


def get_pipeline_id():
    """
    @summary: get pipeline id
    """
    return params.get("pipeline.id", None)


def get_pipeline_name():
    """
    @summary: get pipeline name
    """
    return params.get("pipeline.name", None)


def get_pipeline_build_id():
    """
    @summary: get build Id
    """
    return params.get("pipeline.build.id", None)


def get_pipeline_build_num():
    """
    @summary: getbuildno
    """
    return params.get("pipeline.build.num", None)


def get_pipeline_start_type():
    """
    @summary: get pipeline start type
    """
    return params.get("pipeline.start.type", None)


def get_pipeline_start_user_id():
    """
    @summary: get start userid
    """
    return params.get("pipeline.start.user.id", None)


def get_pipeline_start_user_name():
    """
    @summary: get start user.name
    """
    return params.get("pipeline.start.user.name", None)


def get_pipeline_creator():
    """
    @summary: get create user
    """
    return params.get("BK_CI_PIPELINE_CREATE_USER", None)


def get_pipeline_modifier():
    """
    @summary: get change user 
    """
    return params.get("BK_CI_PIPELINE_UPDATE_USER", None)


def get_pipeline_time_start_mills():
    """
    @summary: get pipeline start time
    """
    return params.get("pipeline.time.start", None)


def get_pipeline_version():
    """
    @summary: get pipeline version
    """
    return params.get("pipeline.version", None)


def get_workspace():
    """
    @summary: get workspace
    """
    return params.get("bkWorkspace", None)


def get_test_version_flag():
    """
    @summary: Whether the current plugin is a test version logo
    """
    return params.get("testVersionFlag", None)


def get_sensitive_conf(key):
    """
    @summary: get Configuration Data
    """
    conf_json = params.get("bkSensitiveConfInfo", None)
    if conf_json:
        return conf_json.get(key, None)
    else:
        return None


def set_output(output):
    """
    @summary: Set output
    """
    setOutput = SetOutput()
    setOutput.set_output(output)


def get_credential(credential_id):
    from .openapi import OpenApi
    client = OpenApi()
    return client.get_credential(credential_id)


if __name__ == "__main__":
    pass
```

1. The interfaces can be broadly classified into the following categories.

   1. get user input, `get_input` returns a dictionary consisting of `{"input_component_name": "user_input_content"}`, call method: `sdk.get_input().get("key")`
   2. set user input, `set_output` set user output, in command_line.py, has been wrapped into `exit_with_error` and `exit_with_succ`
   3. get_private_configuration, the private configuration usually configures the global variables of the plugin or the account secret information which is not visible to normal users, such as the address of the BK esb gateway, the address of the requesting third-party service, etc. Call method: `sdk.get_sensitive_conf(key)`, the key indicates the configuration name, such as `sdk.get_sensitive_ conf("BK_PAAS_URL")`
   4. get_credential`, the user's private configuration, you can manage the configuration by credentials, the plugin can get this part of information by `get_credential`, call method: `sdk.get_credential("credential_id")`, credential_id is the English name of the credential
   5. get built-in variables, in addition to the above four categories, the remaining interfaces are all interfaces to get built-in variables
   6. there are also interfaces for log printing `sdk.log.info("info"), sdk.log.error("error")`
