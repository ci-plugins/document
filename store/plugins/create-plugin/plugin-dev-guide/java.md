## Java plug-in development guidelines

## I. The overall structure of the project is as follows

```text
|- pipeline-plugin
    |- bksdk plugin sdk
    |- demo plugin sample, you can change the project name and internal logic to your custom
```

## II. How to develop plug-ins

Plugin code is recommended to unify management. Generic open source plug-ins can be placed under [ci-plugins](https://github.com/ci-plugins)

Please refer to [plugin-demo-java](https://github.com/ci-plugins/plugin-demo-java)

## III. How to type into the zip package requested by the R&D store.

1、Enter the pipeline-plugin directory and execute the command "mvn clean package" to package.

2, enter the demo (the project directory where the plug-in logic is located) directory under the target folder can get the zip package we need.

