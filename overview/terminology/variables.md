# Variables

## Define variables in the pipeline

### Customize variables when orchestrating the pipeline
Click Job1-1 on the Edit Pipeline page to add pipeline variables.
![](../../.gitbook/assets/image%20%2813%29.png)

### Sets variables in the pipeline plug-in
If you develop your pipeline plug-in in bk-ci, you can define the output field in the plug-in's task.json file, which also allows you to declare these variables when you run the plug-in.
### Set variables through the Bash plugin
You can set the parameters passed between plug-ins using the setEnv function in the Shell Script plug-in as follows:
```bash
#!/usr/bin/env bash
# setEnv "FILENAME" "package.zip"
# Then reference this variable with ${FILENAME} in the form of subsequent plug-ins```
```

## References variables in the pipeline

You can use the variables defined above in any plugin form by referring to them as ${KEY}
## Set the variable value when the pipeline is manually triggered
1. When the pipeline variable is defined during the editing process and the "Display during execution" option is enabled, the pipeline preview page will be displayed after the pipeline is run.
2. Go to the preview page where you can edit your variable value again and run the pipeline.
![](../../.gitbook/assets/image%20%2838%29%20%281%29%20%281%29.png)

![Var](https://bkdocs-1252002024.file.myqcloud.com/ZH/6.0/%E6%8C%81%E7%BB%AD%E9%9B%86%E6%88%90%E5%B9%B3%E5%8F%B0/%E4%BA%A7%E5%93%81%E7%99%BD%E7%9A%AE%E4%B9%A6/assets/variables_5.png)

> The Key variable cannot be modified during execution, only the value variable can be modified.
## Next you may need
* [List of predefined variables](../../reference/pre-define-var/)
