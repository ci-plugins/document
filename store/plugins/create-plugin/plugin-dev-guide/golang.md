# Golang Plugin Development Guide
## Plug-in development framework description
> The plug-in can be packaged into a command line executable command. There is no requirement on the development framework. The following uses the demo plug-in as an example
** I. The overall structure of the sample plug-in code project is as follows:**

```text
| - ${your plugin id}    |- cmd
        |- application
            |- main.go

    |- hello
        |- hello.go
```

**II. How to develop plug-ins:**

> See [plugin-demo-golang](https://github.com/ci-plugins/plugin-demo-golang)
Create plug-in code projects
You are advised to manage plug-in codes in a unified manner. Generic open source plug-ins can be placed under [ci-plugins](https://github.com/ci-plugins)
* Implement plug-in functions

  Specification:

  * [Plug-in Development Specification](../plugin-specification.md)
  * [Plug-in output specification](../plugin-output.md)

**III. How to package and publish:**

1. Go to the plug-in code project directory
2. Pack

```text
cd cmd/application
go build -o bin/${executable}
```

1. Create a new folder anywhere and name it as follows: release\_pkg = ${your plugin id}\_release
2. Copy the execution package produced in Step 2 to ${release\_pkg}
3. Add the task.json file to the task.json file under ${release\_pkg}. See the example.
   * [Plug-in Configuration Specification](../plugin-config.md)
   * task.json Example:
```text
{
    "atomCode": "demo",
    "execution": {
        "language": "golang",
        "packagePath": "app",             # Relative path to the plugin installation package in the release package
        "demands": [
            ""                            # The installation commands to be executed before the plugin is launched, in order
        ],
        "target": "./app"
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

4. In the ${release\_pkg} directory, type all files into a `zip` package
Example `zip` package structure:
```text
| - demo_release.zip # distribution package
	| - app # plug-in package execution
	| - task.json  # plug-in configuration file
```

After packaging is complete, the plug-in workbench bill of lading is published, and the plug-in can be tested or released
