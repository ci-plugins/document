# Credential variable
After setting the credential of **password type **in the credential management, you can reference the password variable in the pipeline. The password variable is project-level and can be referenced in different pipelines under the same project. It is applicable to the scene where variables need to be defined for the whole project, such as game platform, game version, branch name, etc.
Reference:  ${credential name}
![Set password variable](../../../.gitbook/assets/image-variables-ticket-myvar.png)
![Reference password variable](../../../.gitbook/assets/image-variables-ticket-var-used.png)