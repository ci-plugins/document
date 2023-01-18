# Plugins customize UI

## Custom plug-in front-end framework
> As more and more users use the R&D store to develop pipelining plug-ins, users have higher and higher requirements for components and interaction scenarios.
> Because most of the components and interaction scenarios proposed by individual users are not universal, the platform cannot be encapsulated one by one, so a set of user-defined framework for the development of the front-end part of the plug-in is designed and developed.
The > framework opens the front end of the plug-in to user-defined development and is suitable for implementing the front end of the plug-in in complex interaction scenarios.
## Principle introduction
* Divide the pipeline editing plugin panel into an area to load as an iframe, and the content of the iframe is implemented by user-defined.
* When the plugin is clicked, the upper layer of the platform will load the plugin's [atomValue](vscode-webview-resource://3f6fc6ee-8541-4ba2-969a-1a7624756a26/file///Users/zhaozhihui/Downloads/ci- plugins-wiki/specification/plugin_custom_ui.md#atomvalue) and [atomModel](vscode-webview-resource://3f6fc6ee-8541-4ba2-969a- 1a7624756a26/file///Users/zhaozhihui/Downloads/ci-plugins-wiki/specification/plugin_custom_ui.md#atommodel) is passed by postMessage to The iframe will get the atomModel and atomValue internally and then customize the plugin part.
* When the user enters the corresponding parameters, the value is updated to atomValue and the plugin panel will automatically pass the value of atomValue back to the upper layer of the platform when it is closed.

For vue developers, we encapsulate a vue-based scaffolding that integrates the BK magixbox component library, bkci business components, and bkci plug-in capabilities, and encapsulates the api for communication with the upper layer of the platform, so that developers can focus only on the business logic part of the process.

## Framework directory structure introduction
The bk-frontend directory in the root directory of the plug-in code base is the front-end code root directory.
Its code structure is as follows:![](vscode-webview-resource://3f6fc6ee-8541-4ba2-969a-1a7624756a26/file///Users/zhaozhihui/Downloads/ci-plugins-wiki/asse ts/atom-custom-ui.png)
## Development steps
* 1. Select "Yes" for the front end of the custom plug-in when adding new parts to the R&D store.

* 2. Operation:

  * Create the bk-frontend directory in the code root directory
  * Go to the bk-frontend directory
  * Copy the framework code [bkci-customAtom-frontend](https://github.com/ci-plugins/bkci-customAtom-frontend) to the current directory
  * Run npm install
  * run npm run dev and open a browser to [http://localhost:8001](http://localhost:8001/) to see the effects of our simple built-in demo project

* 3. Development:

  * Configure task.json in the bk-frontend/data directory
  * Develop plug-in business logic in Atom.vue (see the plug-in business logic development introduction below for specific development considerations)

* 4. After local debugging is ok:

  * Copy the contents of task.json in the bk-frontend/data directory to task.json in the root directory
## Atom.vue \(User plug-in logical part development considerations \)
* When developing plug-ins in Atom.vue, users need to reference atomMixin, which has built-in communication capabilities and interaction apis on the upper level of the platform
```text
import { atomMixin }from 'bkci-atom-components'
mixins: [atomMixin],
```

* After referencing atomMixin.js, data already has two built-in atomValue and atomModel variables (as explained below) :

  * atomModel: namely, input part of task.json. Under the framework of custom plug-in, the input part of task.json can be understood as the data variable in the vue file. When you put some configurations in task.json, you can get them directly in the atomModel variable, which makes the vue file simpler and easier to maintain.
  * atomValue: The value that needs to be submitted to the upper level of the platform and saved to the back-end plug-in execution, such as:

  ```text
  {
      "item1": "111",
      "item2": "222"
  }
  ```

After the user has modified the corresponding parameter, the value can be updated to atomValue. When the plug-in panel is closed, the atomValue value is automatically returned to the upper layer for saving
## Local debugging
> Framework provides local debugging module, users can debug the front-end part locally before submitting
package.json provides two packaging commands

* npm run dev: run this command locally to debug the project. When running this command, the program execution path is roughly main.js -&gt; data/LocalAtom.vue -&gt; Atom.vue

* npm run public: When the local development is complete and the package is ready to be published, run this command, main.js -&gt; data/PublicAtom.vue -&gt; Atom.vue

* During local development, the user puts the contents of task.json into data/task.json. After running npm run dev, the framework will read input in data/task.json as atomModel. Extract the default value of each field as the corresponding default value in atomValue

* When running online, the atomModel and atomValue values are passed inside the iframe from the platform layer

  

  Debugging is normal when the user runs locally, and the effect is the same when the user opens the platform plug-in panel after going online
## Publish
After debugging the plug-in, release it through the R&D store workbench. The preparation process of the release package is as follows:
1. run npm run public package
2. Create a frontend directory in the release package root directory (relea.md).
3. Copy the package result file \(all files \in the dist directory) to the frontend directory
4. zip all files in the root directory of the release package and upload them to the store on the workbench
## Frequently Asked Questions
1. How to use the built-in bkci component library and magixbox component library?
* bkci component library: Any component that can be configured with task.json can also be used directly as a component. The properties of a component are configurable properties of task.json ([click to view](plugin-config.md)). The value change event of the bkci component library is encapsulated as handle-change="functionxxx", where functionxxx has two parameters: the component name and the new value of the component
* The BK magixbox component library has a variety of components, which can basically cover the types of components needed for daily development. Within the framework, you can directly use the magixbox component library for development. The specific use please see [official documentation](https://bk.tencent.com/docs/document/6.0/130/5946)
2. When debugging locally, I need to combine some specific project, such as using selector component to pull the code base list and credential list of certain project, how to bring the project information?
* projectId=${projectId} in query mode at the end of the accessed url. Such as [http://local.XX.com:8001?projectId=abc](http://local.xx.com:8001/?projectId=abc), The built-in selector/select-input component in bkci will automatically parse the projectId parameters in the url as request parameters
3. Is task.json still useful after using the custom plug-in framework? What is the relationship between the two?
* To some extent, the custom framework will work even if the input content in task.json is empty, but we recommend that you configure the input part of task.json. The content in the input part will be transmitted to iframe through atomModel variable, which can make the code more concise, define the fields required by the plug-in in advance, and facilitate the back-end to do some inspection and expansion. On the other hand, users who are used to the direct generation of task.json before can also refer to the writing method in demo. Fields are rendered directly in the form of traversal of higher-order components. The interaction capabilities configured in task.json, such as rely, can also be directly used after referring to atomMixin
4. There is a task.json in the root directory of the code repository and a task.json in the bk-frontend/data directory. What is the relationship between the two?
* Two specifications of task.json are configured in the same way. task.json in bk-frontend/data is the data source for local debugging, and atomModel value is the input part in local debugging. json in the root directory is the data source of atomModel when running online. At the same time, if there is output part in the plug-in, it can be added in the root directory of task.json, that is, the development and debugging phase. Write and configure task.json in bk-frontend/data. Then copy the contents of task.json in bk-frontend/data to task.json in the root directory before submitting the data. (If the output part is included, add it separately.)
5. In the process of plug-in development, if there is field verification, how to interact with the upper platform?
* After referring to atomMixin, the built-in framework encapsulates the api for communicating with the upper-layer plug-in state. When the parameter entered by the user is invalid, this.setAtomIsError\(true\) is called, and the plug-in box can be marked red. Call this.setAtomIsError\(false\) to reset the state back to normal
