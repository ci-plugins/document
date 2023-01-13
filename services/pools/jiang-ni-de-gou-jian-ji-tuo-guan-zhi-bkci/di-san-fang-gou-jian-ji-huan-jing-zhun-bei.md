# Third party builder environment preparation
bk-ci pipelining plug-ins are provided by official or third party developers. Plug-in development languages support Java, Python, NodeJs, or Golang, and execution is environment dependent. Before importing bk-ci to a private builder as a pipeline executor, prepare an environment to prevent pipeline execution failures.
{% tabs %}
{% tab title=" Prepare Python plugin execution environment "%}
The Developer Store supports python plugins. If you want to run python plugins on your build machine, you need to do the following:

* Install python
  * python3.6 is recommended since Python 2 will not be serviced soon
  * The plug-in must be compatible with python2 and python3, so the version of python installed in the execution environment has little effect 

* Install the latest version of the pip tool

* If the enterprise has a dedicated pip source, set the pip source
  ```text
  index-url = <internal pip source >
  extra-index-url = < alternate pip source >  
  timeout = 600
  
  [install]
  trusted-host = <pip source host>  ```
  ```

  * Configuration Procedure (Using Linux as an example)

    > The user for configuring pip must be the same as the user for enabling bk-ci Agent. Otherwise, the configuration does not take effect. Perform ps - ef \| grep enterprise command to confirm start bk - ci Agent user

    * Log in to the machine as the user who installed bk-ci Agent
    * vi ~/.pip/pip.conf to add the above configuration, note that the newline cannot be \r\n
    * Save configuration
    * Restart the bk-ci Agent{% endtab %}

{% tab title=" Prepare Nodejs plugin execution environment "%}
The Developer store supports the development of NodeJS plugins. If you want to run NodeJS on your build machine, you need to do the following:

* Install NodeJS
> suggest installation [node LTS versions](https://nodejs.org/en/download/), which support more es features
* If the enterprise has a dedicated npm source, configure the npm repository as the Intranet version
  ```text
  npm config set registry < Intranet npm repository address> 

{% endtab %}
{% endtabs %}
