# Python Plugin Development Guidelines

## Plugin development framework description

* Developers can use their favorite framework for development, there are no hard and fast requirements
* Examples of plugins organized in source distribution packages
  * Pros: cross-platform, simple and small package
  * Disadvantages: need to use pip installation before implementation, when there are other third-party package dependencies, need to be able to access the mirror source to install the dependency package

**I. The overall structure of the plug-in code project example is as follows:**

```text
|- ${your plugin identifier} # Plugin package name
    |- ${your plugin identifier} # Plugin package name
        |- __init__.py py # py package identifier
        |- command_line.py # command entry file
    |- python_atom_sdk # plugin development SDK package
    |- MANIFEST.in # Package file type declaration
    |- requirements.txt # dependency declaration
    |- setup.py # Execute package packaging configuration
```

**II. How to develop plugins:**

> Reference [plugin-demo-python](https://github.com/ci-plugins/plugin-demo-python)

* Create plugin code project

  Plugin code is recommended to be managed in a unified way. Generic open source plugins can be put under [ci-plugins](https://github.com/ci-plugins)

* Modify the package name to have a recognizable name, it is recommended to be consistent with the plugin logo
* Implementing plug-in functionality
* Specification.
  * [plug-in development specification](../plugin-specification.md)
  * [plugin-output-specification](../plugin-output.md)

**III. How to package and release:**

1. enter the root directory of the plug-in code project
2. Execute the package command package

   ```text
   # This example uses the setuptools sdist command as an example
   
   python setup.py sdist
   
3. Create a new folder in any location, name it: release\_pkg = ${your plugin identifier}\_release
4. Copy the package produced in step 2 to ${release\_pkg}
5. Add the task.json file to ${release\_pkg} under task.json See the example to configure it according to the plugin functionality.

   * [Plugin configuration specification](../plugin-config.md)
   * task.json example.

   ```text
   {
       "atomCode": "demo",
       "execution": {
           "language": "python",
           "packagePath": "demo-1.1.0.tar.gz",             # Relative path to the plugin installation package in the release package
           "demands": [
               "pip install demo-1.1.0.tar.gz --upgrade"   # actions to be performed before executing the target command, such as installing dependencies, etc.
           ],
           "target": "demo"
       },
       "input": {
           "inputDemo":{
               "label": "inputdemo",  
               "type": "vuex-input",
               "placeholder": "inputdemo",
               "desc": "inputdemo"
           }
       },
       "output": {
           "outputDemo": {
               "description": "outputdemo",
               "type": "string",
               "isSensitive": false
           }
       }
   }
   ```

6. In the ${release\_pkg} directory, just make a `zip` package of all the files

Example of `zip` package structure.

```text
|- demo_release.zip # Release package
   |- demo-1.1.0.tar.gz # Plugin execution package
   |- task.json # Plugin configuration file
```

After the package is finished, raise a release order in the plugin workbench to test or release the plugin

