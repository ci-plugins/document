# NodeJS Plugin Development Guidelines

## Plugin development framework description

**I. The overall structure of the plugin code project is as follows:**

**II. How to develop plugins:**

> Reference

* Create plugin code project

  Plug-in code is recommended to be managed in a unified manner. Generic open source plug-ins can be placed under [ci-plugins](https://github.com/ci-plugins)

* modify the package name with a recognizable name, it is recommended that can be consistent with the plug-in logo
* Implement the plugin functionality
* Specification.
  * [plug-in development specification](../plugin-specification.md)
  * [plugin-output-specification](../plugin-output.md)

**III. How to package and release:**

1. enter the root directory of the plug-in code project
2. execute the package command package
3. create a new folder in any location, name example: release\_pkg = ${your plugin logo}\_release
4. Copy the package produced in step 2 to ${release\_pkg}
5. Add the task.json file to ${release\_pkg} under task.json See the example to configure it according to the plugin functionality.

   * [Plugin configuration specification](../plugin-config.md)
   * task.json example.

   ```text
   {
       "atomCode": "demo",
       "execution": {
           "language": "nodejs",
           "packagePath": "", # Relative path to the plugin installation package in the release package
           "demands": [
               "" # The installation commands to be executed before the plugin starts, in order
           ],
           "target": "demo"
       },
       "input": {
           "inputDemo":{
               "label": "inputDemo",  
               "type": "vuex-input",
               "placeholder": "inputDemo",
               "desc": "input-example"
           }
       },
       "output": {
           "outputDemo": {
               "description": "Output Demo",
               "type": "string",
               "isSensitive": false
           }
       }
   }
6. In the ${release\_pkg} directory, just make a `zip` package of all the files
Example of `zip` package structure.

```text
|- demo_release.zip # Release package
   |- # Plugin execution package
   |- task.json # Plugin configuration file
```

After the package is finished, raise a release order in the plugin workbench to test or release the plugin

