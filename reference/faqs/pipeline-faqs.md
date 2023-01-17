# Pipeline FAQ

### Q: How can I make my pipeline log display with different colors

In the pipeline logging component, we define the following keywords for plug-in developers to use.

| Key word       | function                                          | remarks                                                      |
| -------------- | ------------------------------------------------- | ------------------------------------------------------------ |
| ##[section]    | The beginning of a Job or plugin                  | If it is the start of a plug-in, it must be included in the Starting of a Job |
| ##[endsection] | The end of a Job or plugin                        | If it is a plug-in ending, it must be included in the Finishing of a Job |
| ##[command]    | Highlight the following string as ShellScripts    | #0070BB                                                      |
| ##[info]       | Mark the following string as the info color       | #48BB31                                                      |
| ##[warning]    | Mark the following string as the color of warning | #BBBB23                                                      |
| ##[error]      | Mark the following string as the error color      | #DE0A1A                                                      |
| ##[debug]      | Mark the following string as the debug color      | #0D8F61                                                      |
| ##[group]      | The beginning of a fold                           |                                                              |
| ##[endgroup]   | The end of a fold                                 |                                                              |

**Take the Bash plug-in as an example:**

```
echo "##[command]whoami"
whoami
echo "##[command]pwd"
pwd
echo "##[command]uptime"
uptime
echo "##[command]python --version"
python --version

echo "##[info] this is a info log"
echo "##[warning] this is a warning log"
echo "##[error] this is a error log"
echo "##[debug] this is a debug log"

echo "##[group] Print SYSTEM ENV"
env
echo "##[endgroup]"
```

You should see something like the image below

![img](../../.gitbook/assets/image2020-1-9_21-59-12.png)

### Q: Does the gitlab event trigger plugin fail to trigger events?

1. Check whether the pipeline_devops_ci_process. T_PIPELINE_WEBHOOK table is registered. SELECT * FROM devops_ci_process.T_PIPELINE_WEBHOOK WHERE pipeline_id = pipeline_id, {pipeline_id} can be obtained from the url
2. If not registered
   1. Check whether the repository service is connected to gitlba
   2. Check whether the gitlab warehouse has master permissions
   3. In the repository service deployment on the machine, the implementation of the grep "Start to add the web hook of" BK_HOME/logs/ci/repository/repository - the conversation. *Registered* the log to *find* *reasons* for *failure*, BK_HOME The default value is /data/bkce
3. If it's registered and still not triggered,
   1. Go to gitlab's webhook page and see if any registrations have been successful, as shown in Figure 1
   2. If you have any registered gitlab url, the url is [http:// domain name/external/SCM/codegit/commit](http://xn--eqrt2g/external/scm/codegit/commit) and then click edit, send details view, as shown in figure 2
   3. See the details that gitlab did not send, as shown in Figure 3
4. If above all no problem, in the process of service deployment machine, perform the grep "Trigger gitlab build" $BK_HOME/logs/ci/process/process - the conversation. The log search logs, find out the entry log Trigger

![img](../../.gitbook/assets/image%20(58)%20(1).png)

![img](../../.gitbook/assets/image%20(59).png)

![img](../../.gitbook/assets/image%20(57).png)

### Q: What do the states of the assembly line represent?

The status of the pipeline is summarized as follows:

![img](../../.gitbook/assets/image-20220301101202-uphlD.png)

### Q: How is the bkci pipeline progress bar calculated?

The progress bar is an estimate made by the bkci front end based on pipeline-related data. This schedule is not the exact time, for reference only.

![img](../../.gitbook/assets/进度条.png)

### Q: How does the bkci pipeline build support server distribution rate-limiting configurations?

Adjust the rate limiting of the distribution source, as shown in the following figure. If the agent has been installed on a machine, you can remove the Agent and then install it. IP address of the source machine: 192.168.5.134

![img](../../.gitbook/assets/image-20220301101202-PluSB.png)

### Q: How do I obtain the pipeline id?

In the pipeline url, the parameters after the pipeline are the project id and pipeline id respectively. Such as: http://devops.bktencent.com/console/pipeline/iccentest/p-8f3d1b399897452e901796cf4048c9e2/history, iccentest for project id, p-xxx indicates the pipeline id.

### Q: Does the project name support modification?

The project name can be changed in Project Management, the project abbreviation (i.e., project id) cannot be changed.

![img](../../.gitbook/assets/image-20220301101202-qTzdw.png)

![img](../../.gitbook/assets/image-20220301101202-FyiDk.png)

### Q: Pipelining failed. Why doesn't the plugin have a retry button?

Only the latest build can be retried.

### Q: How do I automatically distribute builds to specific servers through bkci?

With the deployment machine, we can distribute the artifacts to the test machine. Start by adding a non-compile environment, Job 3-1, adding the plug-in job platform-component distribution and completing the configuration.

![img](../../.gitbook/assets/image-20220301101202-vGRcA.png)

### Q: What are the global variables of bkci?

[pre-define-var](../pre-define-var/)

### Q: How do I view the timestamp when viewing logs?

Go to the log page, Show/Hide Timestamp

![img](../../.gitbook/assets/image-20220301101202-QERjn.png)

### Q: What is the use of view management and tag management in bkci pipeline?

If there are a large number of pipelines, labels and views play a bigger role.

### Q: Why is it sometimes necessary to apply for pipelining permission, but F5 is restored after refreshing?

There is a permission conflict. In the user group permission, there are multiple pipeline permissions. But customization only has pipelining permissions. This will be fixed in subsequent updates. The solution is to delete the custom permission. This issue will be fixed with a future version update.

![img](../../.gitbook/assets/image-20220301101202-HIaKn.png)

### Q: python environment variables are added but do not take effect when the job is executed. (job error "System cannot find the specified file")

Since bkci agent and BK agent use the system account, the environment variables added to the administrator account do not take effect. You need to add python.exe and pip3.exe to the system environment variables and restart the operating system

### Q: Can I upload builds to designated private GitLab warehouses via the bkci pipeline?

bkci git plug-in does not have push function. Users can put the ssh private key on the build machine and use the git command push product in the Batch Script plug-in or Bash plug-in to achieve a temporary solution.

### Q: How do I pass variables between bash plug-ins so that the previous bash plug-in outputs variables that the next bash plug-in can reference?

bkci provides the bash plugin with the setEnv command to set bkci's global variables, `setEnv 'variable name' 'variable value'` Such as:

```
setEnv 'cmdb' '3.2.16'
```

setEnv sets the output parameter of the current bash. This parameter takes effect only in the downstream. It cannot be printed in the current bash.

Used in windows batchscript plugin`call:setEnv "FILENAME" "package.zip"` This variable is then referenced in subsequent batchscript plug-ins using %FILENAME%

### Q: Node machine, the display is normal. Why is there no data on monitoring network io?

![img](../../.gitbook/assets/image-20220301101202-Lkelb.png)

Not enabled. This monitoring is meaningless and does not affect scheduling. Special monitoring systems such as BK monitoring are recommended.

If you want to enable:

```
1. configure bin/03-userdef/ci.env 
2. add BK_CI_ENVIRONMENT_AGENT_COLLECTOR_ON=true
3. Then add the influxdb-related configuration items. 4.
Reinstall the ci-environment. You can use . /bk_install ci to install it.
5. Modify the existing agent: edit .agent.properties , configure devops.agent.collectorOn=true, restart the agent.
```

### Q: Is there a way to call bkci from standard operations?

Pipeline-stage-1 trigger selects remote. Then standard operations invokes the job to quickly execute the script, invoking the url prompted in the remote plug-in.

### Q: How do I use dockerbuild to package the image and then push the image to harbor? My dockerbuild environment does not have docker commands

You can use a private build machine. There is no dockerd in the container, and for security reasons, the host dockerd cannot be operated in the container, or if the bkci user is trusted, the DinD **solution** from our delivery team can be used

### Q: Is it only possible to use private build machines to generate images using docker build?

You are advised to use a private builder. The public builder DinD solution has security risks. Therefore, a private builder is required for mirroring.

If bkci users are trusted, they can use our delivery team's DinD **solution**

### Q:ci does not display logs

![img](../../.gitbook/assets/image-20220301101202-xwkmo.png)

View microservice logs/ data/bkce/logs/ci/log/

![img](../../.gitbook/assets/image-20220301101202-bduGg.png)

One index accounts for 12 shards, exceeding the maximum set by es7, which is the limit for es7

Solution: Clean up some useless indexes

```
# View all current indexes
source /data/install/utils.fc
curl -s -u elastic:$BK_ES7_ADMIN_PASSWORD -X GET http://$BK_ES7_IP:9200/_cat/indices?v
# Delete index # index is the name of the index
curl -s -u elastic:$BK_ES7_ADMIN_PASSWORD -X DELETE http://$BK_ES7_IP:9200/index
# cant delete .security-7
```

![img](../../.gitbook/assets/image-20220301101202-RWPNo.png)

**Another possibility is that the user does not have es7 installed**

### Q: Common builder, are all of these supported?

![img](../../.gitbook/assets/image-1646103610029.png)

The common builder relies on docker and can only run linux. Currently, it can only run build images based on our bkci/ci:alpine (debian system).

### Q: Does a private build machine have to be a physical machine? Can it be a docker container?

The private builder is bound to the project, and the agent must be installed and registered. You are advised to use scenarios with few changes, such as physical machines or VMS. Containerization can be done using a common builder.

### Q: An error occurs when uploading an image. The program changes the http mode to https by default

![img](../../.gitbook/assets/image-20220301101202-UayBz.png)

docker is https by default, so docker on the server should be changed. You need to add insecure-registry to /etc/docker/daem. json on the dockerhost machine.

By default, all images pushed by BKCI use https. To use http, you need to configure the warehouse domain name into insecure

If https is used, if the warehouse domain name is not the corresponding certificate when docker client starts to install, the certificate corresponding to this domain name needs to be imported into the builder

### Q:no available Docker VM

![img](../../.gitbook/assets/image-20220301101202-ceNsG.png)

No ci-dockerhost is available.

\1. In the ci - dispatch nodes perform/data/SRC/ci/scripts/bkci - op. Sh list check whether there is a condition is true.

\2. If the dispatch still fails, check whether the ci-dispatch logs are abnormal. Or log involving dockerhost ip.

The reason was that when bkci was deployed, due to limited server resources, the construction machine microservice gateway was placed on one machine, resulting in high memory usage of the construction machine. When building the environment, the construction machine could not be found. Now those errors before the construction machine was deployed on another machine are gone.

### Q: Where can I view the jar packages uploaded to the artifact library? Use the default

The BK community reference: https://bk.tencent.com/s-mart/community/question/2380

### Q: The gitlab event trigger plug-in cannot trigger events

Refer to the https://docs.bkci.net/reference/faqs under the screen

### Q: Failed to pull a mirror with error message status 500

![img](../../.gitbook/assets/image-20220301101202-CVycR.png)

If the warehouse is configured by users, ensure that the network is reachable

### Q: Can only one agent be installed on a mac

You can start multiple agents in different directories. Each agent instance needs to be newly installed. The existing agent directory cannot be directly copied.

### Q: Failed in windos builder pipelining to open the exe using python

Symptom In windows, the agent cannot pull up the UI exe

This is the windows session 0 limit

### Q: failed to connect to gitlib.xxx.com port 443:connection timed out Q: Failed to connect to gitlib.xxx.com port 443: Connection timed out

![img](../../.gitbook/assets/image-20220301101202-AaxCJ.png)

The reason for the network disconnection is that after dockerhost is started, a sysctl -p equivalent command is executed. As a result, net.ipv4.ip_forward is reset to 0, resulting in network disconnection of the container.

```
sysctl -p | grep -F net.ipv4.ip_forward
net.ipv4.ip_forward = 0
Start a separate test container:
docker run -it --rm centos 
You should see:
WARNING: IPv4 forwarding is disabled. Networking will not work.
Execute the command inside the container, and you will see a timeout:
curl -m 3 -v paas.service.consul
then run: 
systemctl restart bk-ci-docker-dns-redirect
Start a separate test container:
docker run -it --rm centos 
Execute the command inside the container, and you should see the network resume:
curl -v paas.service.consul
```

### Q: docker needs to be connected to the network in the agent, but the server cannot connect to the network. How to deal with it?

Currently, any image can be used by the public builder. No build environment requires the Internet to download the image.

It is currently required that you deploy the non-compile environment to a network accessible area and grant access to the docker hub address.

The public builder fills in the image address for your private docker registry.

And manually transfer bkci/ci:latest on the docker hub to the private docker registry.

### Q: Not when selecting credentials after adding them

Check whether the browser reports an error after the creation, and check whether the ci-auth and ci-ticket logs are abnormal.

If it is created by a common user, you can switch to the administrator account to check whether it is created successfully.

### Q: How do I use mount? No data in the drop-down box

![img](../../.gitbook/assets/image-20220301101202-sxXbU.png)

This service requires the maintenance of an NFS shared storage service. Therefore, it is not recommended and may be removed later

The best way to do this is to package the dependency tool into the image, which has two phases

The job in stage A has a task-A: clone git code and build the package jar

The job in phase B has a task-B: It is to distribute the jar scp built in task-A to the deployment server.

The result is that the workspace of these two phases is not common. The current practice is to put them all into the same Job, so that the production jar files can be built in the same workspace.

By design, if a CI artifact is to be deployed, it has to go to the artifact repository, and using maven for private service is a good idea

### Q: R&D store: plug-in configuration file [task.json] The atomCode field is inconsistent with that entered by the workbench

![img](../../.gitbook/assets/image-20220301101202-WRucB.png)

The uploaded, probably not plug-in distribution, is source code. The release process looks at the plug-in's readme

If the correct distribution package is uploaded, you can temporarily edit task.json in the plug-in zip package, modify atomCode(consistent with the upload interface, without underscores), repackage and upload.

### Q: The plug-in package fails to be uploaded

![img](../../.gitbook/assets/image-20220301101202-iJWQt.png)

Can check artifactory blueking users whether normal, speaking, reading and writing data directory: / data/bkce/public/ci/artifactory /

Then check the artifactory log file for errors.

### Q: A bkiam v3 failed error is displayed when bkci is adding a node

![img](../../.gitbook/assets/image-20220301101202-MyIAk.png)

### Then check the log according to the given documentation

/data/bkce/ci/environment/logs/environment-devops.log

/data/bkce/ci/environment/logs/auth-devops.log

![img](../../.gitbook/assets/image-20220301101202-GyIic.png)

The T_AUTH_IAM_CALLBACK table in the ci auth library is empty

The initial cluster configuration failed, but the script did not terminate

```
ci init
reg ci-auth callback.
[1] 19:29:00 [SUCCESS] 172.16.1.49
{
  "timestamp" : 1626291190535,
  "status" : 500,
  "error" : "Internal Server Error",
  "message" : "",
  "path" : "/api/op/auth/iam/callback/"
}Stderr: * About to connect() to localhost port 21936 (#0)
Solution: You can try to manually register the ci-auth callback.
source /data/install/load_env.sh
iam_callback="support-files/ms-init/auth/iam-callback-resource-registere.conf"
./pcmd.sh -H "$BK_CI_AUTH_IP0" curl -vsX POST "http://localhost:$BK_CI_AUTH_API_PORT/api/op/auth/iam/callback/" -H "Content-Type:application/json" -d @${BK_PKG_SRC_PATH:-/data/src}/ci/support-files/ms-init/auth/iam-callback-resource-registere.conf
```

### Q: Upload artifacts Does the upload function upload artifacts to the build machine that is currently using the stage or does it have a separate repository location

Archiving component is to archive the products of the construction machine to a dedicated product warehouse, product warehouse and construction machine unrelated, determined by Artifactory service.

The archiving of CI is to temporarily store the product in the warehouse for the convenience of downstream operation of the pipeline, or as the source of subsequent deployment. Currently, there is no support for archiving the storage mode of components specified according to the cloud where the current builder resides.

What you describe looks like a distribution of components that might make more sense through deployment tools.

Or you can customize plugins to do the archiving themselves

### Q: Is there documentation on how to develop bkci plug-ins?

Plug-in development guidance: https://docs.bkci.net/store/plugins/create-plugin

### Q: JOOQ; uncategorized SQLException for SQL

![img](../../.gitbook/assets/image-20220301101202-rtxbB.png)

The old sql is not cleaned up

```
# Clean up the flag file, re-import all sql files
for sql_flag in $HOME/.migrate/*_ci_*.sql; do
chattr -i "$sql_flag" && rm "$sql_flag"
done
# Importing database SQL is executed only at the central console
cd ${CTRL_DIR:-/data/install}
./bin/sql_migrate.sh -n mysql-ci /data/src/ci/support-files/sql/*.sql
```

### Q: private configuration of key JOB_HOST is missing

![img](../../.gitbook/assets/image-20220301101202-QtZoR.png)

The job script execution plug-in link: https://github.com/TencentBlueKing/ci-executeJobScript

The JOB_HOST field is missing in the private configuration. Configure the job_host field as shown in the preceding figure

![img](../../.gitbook/assets/脚本执行配置1.png)

### Q: The email sending plug-in is unavailable

![img](../../.gitbook/assets/企业微信截图_16408694122894.png)

Plug-in execution environments are compiled and non-compiled. The execution environment of the email plug-in is non-compiled. When creating a Job, select a Job type that is non-compiled, that is, Agentless

![img](../../.gitbook/assets/image-20220301101202-SfGeA.png)

![img](../../.gitbook/assets/image-20220301101202-dhitX.png)

### Q: The email sending plug-in is successfully executed, but no email is received

1. First configure the ESB email information, refer to: https://bk.tencent.com/s-mart/community/question/2532
2. Configure the plug-in private configuration, refer to: https://github.com/TencentBlueKing/ci-sendEmail

### Q: The sender configuration of the email sending plug-in is not the sender configured by me

![img](../../.gitbook/assets/image-20220301101202-gdDMH.png)

sender needs to be set in the plug-in's "private configuration", independent of the ESB mail_sender

"R&d Store" - "Pipeline Plug-in" - "Workbench" - "Select Send Mail plug-in" - "Basic Settings" - "Private Configuration" - "Add sender Field"

![img](../../.gitbook/assets/wecom-temp-de1f999781431e708256b5e9a9ecc1d6.png)

![img](../../.gitbook/assets/wecom-temp-79503b33558fb2f05c4579c99280f8e7.png)

![img](../../.gitbook/assets/wecom-temp-ad2da5032b4af609e41012bd4113bf84.png)

![img](../../.gitbook/assets/wecom-temp-888da4cdb34f2bbcdc3869f7f4ff6dda.png)

![img](../../.gitbook/assets/wecom-temp-8f040f0a22d3e9b0ff75a6b3ff40410b.png)

![img](../../.gitbook/assets/wecom-temp-db0217ab76483f286bfb63cd7047f353.png)

In addition to the sender field, but also need to configure the other fields, please refer to: https://github.com/TencentBlueKing/ci-sendEmail

### Q: How do the services on the configuration platform relate to the container management platform?

![img](../../.gitbook/assets/企业微信截图_16412880662873.png)

![img](../../.gitbook/assets/企业微信截图_16412881057362.png)

1. In the rights center, check whether the user account has the local-k8s platform permission
2. On the configuration platform, check whether the account is configured in Resources, Services, and Operation and Maintenance Personnel

![img](../../.gitbook/assets/wecom-temp-ac68ebc38b2022819c8540b00100d2fb.png)

### Q: How do I use Merge-Request-Accept-Hook and why do I not trigger it? I want the pipeline to trigger when the branch feature_lzj_test123123213 is merged into feature_lzj_test0117

![img](../../.gitbook/assets/image-20220301101202-RtEPQ.png)

The Merge Request Accept Hook is **triggered when the source branch is successfully merged into the target branch**

For example, when you want to combine feat_1 into the dev branch, write dev for the branch name and listen for the source branch to write feat_1.

![img](../../.gitbook/assets/image-20220301101202-pxOZb.png)

### Q: Where does a gitlab trigger configure a webhook address when jenkins needs to manually configure a url

You do not need to configure this hook. Blueshield will register Webhooks by itself. After selecting the event type and saving it, Webhooks will be automatically registered

![img](../../.gitbook/assets/wecom-temp-d5c48ee99a96d373426491d14d56e404.png)

### Q: gitlab fails to trigger

1. Check whether the branches match

2. Check whether the pipeline_devops_ci_process. T_PIPELINE_WEBHOOK table is registered. SELECT * FROM devops_ci_process.T_PIPELINE_WEBHOOK WHERE pipeline_id = pipeline_id, {pipeline_id} can be obtained from the url

3. If the gitlab webhook page has no record of registering WebHooks, e.g

   ![img](../../.gitbook/assets/image-20220128124536187.png)

   1. Check whether the repository service is connected to gitlab, for example, if gitlab domain name resolution is configured

   2. Check whether the permissions of gitlab warehouse are master permissions, that is, the user who generated accesstoken needs to be from the warehouse`maintainer`Roles, and accesstoken required Scopes`api`

      ![img](../../.gitbook/assets/wecom-temp-fe0a7bc1e72a97ec39e0a4e51e3e1e58.png)

      ![需要选择maintainer](../../.gitbook/assets/image-trigger-gitlab-accesstoken-maintainer.png)maintainer needs to be selected

      ![需要是maintainer](../../.gitbook/assets/image-trigger-gitlab-accesstoken-view.png)maintainer is required

   3. On the machine where the repository service is deployed, execute`grep "add the web hook of " $BK_HOME/logs/ci/repository/repository-devops.log`The default value of $BK_HOME is /data/bkce

4. If there is a webhook registration record on gitlab, e.g

   ![img](../../.gitbook/assets/image-gitlab-webhook-edit.png)

   If it still doesn't trigger:

   1. Click Edit of the corresponding webhook to View the sending details of the webhook and view View detail

      ![img](../../.gitbook/assets/image-gitlab-webhook-viewdetail.png)

   2. Check whether the network between gitlab and bkci is reachable. For example, whether the gitlab server can resolve the bkci domain name

      ![img](../../.gitbook/assets/image-gitlab-webhook-request-detail.png)

5. If above all no problem, in the process of service deployment machine, perform the grep "Trigger gitlab build" $BK_HOME/logs/ci/process/process - the conversation. The log search logs, find out the entry log Trigger. Check the request body from gitlab push and compare the request body`http_url`Whether the field matches the address of the code repository in the code base. If one is a domain name url and the other is an ip url, the field does not match the address of the code repository in the code base, as shown below:

   ![img](../../.gitbook/assets/image-trigger-gitlab-webhook-post-body.png)

   ![img](../../.gitbook/assets/image-trigger-gitlab-repo-ip-view.png)

### Q: The batchscript plug-in cannot execute the bat file. The bat file contains variables that are read from the system and are set by the current user

![img](../../.gitbook/assets/企业微信截图_16285831782937.png)

To change the startup user of the agent service to the current user, run the following command`services.msc`Open the windows Service management page and locate the service`devops_agent_${agent_id}`(Note: each agent_id is different and the value of agent_id can be found in the configuration file.agent.properties)

Right-click -> Properties and select this account on the login TAB

In the case of the domain builder, enter the account name`Domain name \ User name`, for example`tencent\zhangsan`; If there is no in-domain builder, enter the account name`.\ User name`, for example`.\admin,.administrator,.bkdevops`After entering the password, click the Confirm button

![img](../../.gitbook/assets/image-20220128181627246.png)

Right-click -> Restart to restart the service

![img](../../.gitbook/assets/image-20220128181720819.png)

Open the task Manager, and check whether the devopsDaemon.exe and vopsAgent.exe processes exist, and check whether the startup user name of the two processes is the current login user

### Q: The command path in batchscript has Spaces, and execution fails

![img](../../.gitbook/assets/企业微信截图_16285852671573.png)

You can enclose commands with Spaces in quotation marks

### Q: How do I get items ** through the interface

The curl -x GET https://devops.bktencent.com/prod/v3/apigw-app/projects/ - H "content-type: application/json "-H" X-DEVOPS-UID: admin"

### Q: The "execute only if the previous plug-in failed" condition felt useless and was executed successfully

![img](../../.gitbook/assets/wecom-temp-c6aa0d74275116c38ff7f592563616c7.png)

What this condition really means is that any plug-in that runs before this plug-in fails to be triggered, not that the "previous" plug-in failed to run

### Q: Can the English name of the project be changed

Modification is not supported

### Q: How do I get the project name that I want to include in the enterprise's wechat notification message

Use global variables`${BK_CI_PROJECT_NAME}`

### Q: After logging in to bkci in the browser, you need to log in again if you access bkci in a different tab of the same browser

In this case, the login cookie has expired, which should now default to two hours with an adjustable expiration time

### Q: There is a pipeline triggered by gitlab, but the code change record is empty, indicating that there is no new code change in the construction triggered this time, so why is it triggered

The possible reason is that the trigger listens for commit events for the entire codebase, but the code pull plug-in only pulls code for a specific branch that has no code changes. For example, if the plug-in listens for commit events for the entire codebase, but the code pull plug-in only pulls code for the master branch, While the commit is for the dev branch, the code change log shows the changes from the pulled branch that intersected the last checkup, and the master branch has no changes, so there is no change log.

### Q: Can pipelining and pipelining be mutually exclusive? Or pipeline A starts, and when pipeline B starts, pipeline B waits for pipeline A to end

Only jobs in the pipeline can be configured with a mutex group. If the two pipelines have only one JOB, configure the same mutex group for this JOB. If the pipeline has more than one JOB, you need to set a pipeline on both pipelines, then configure a mutex group on the two main waterlines, and pull tasks through the main waterlines.

![img](../../.gitbook/assets/wecom-temp-0427b67401a386578f79c2495a2009f8.png)

### Q: bkci scripts start gradle daemon. Recently, it was discovered that build is closed. Wondering if it was the devops agent?

![img](../../.gitbook/assets/wecom-temp-d4178631b527e498ee7d8a0778c1fb09.png)

After the bkci agent completes the build task, all sub-processes started by the agent are automatically stopped. If you do not need to end the sub-processes, set the environment variable set in the bash script before starting the process: set DEVOPS_DONT_KILL_PROCESS_TREE=true`setEnv "DEVOPS_DONT_KILL_PROCESS_TREE" "true"`

### Q: Can I set a variable value to determine whether to run a plug-in

Under the plug-in, select Run only when all custom variables are met. The name and value of the variable that the custom variable write depends on are displayed

![img](../../.gitbook/assets/image-20220210120321712.png)

### Q: How do I obtain and write the correct value for the plugin variable? For example, if I want to obtain the flushDB value in the plugin, then I find out in the script that it is incorrect?

![img](../../.gitbook/assets/企业微信截图_16318512177997.png)

![img](../../.gitbook/assets/企业微信截图_16318512474377.png)

![img](../../.gitbook/assets/企业微信截图_16318513189348.png)

Click on the reference variable in the top right corner, then click on the right to copy the variable and paste it wherever you want

![img](../../.gitbook/assets/wecom-temp-edfeb72810d972dae34d3f8d98232ec6.png)

### Q: How do I put a time stamp before each line of a log

Occupied space, to be resolved

### Q: Run lock, whether a maximum of one build task is run at a time, and the later task is forced to cancel the earlier task

There is currently no such feature

### Q: We use a cat to display Log, this way can be used, but there is a problem, every time open the speed is very slow, it takes more than 3 seconds to display Log data, is there any other better way to display log

For the problem that the task is longer than 3 seconds, the main reason is that the log data corresponding to the task is large, and the log content is 3MB, so the time is spent on download

### Q: The unity build log is not displayed in real time during pipeline execution

The cause is that "the unity compilation and construction operation is performed in the script and logs are written to the file. However, the subsequent cat command is not executed before the operation is complete. As a result, logs cannot be displayed on the web page in real time. For this scenario, try the following solutions:

```
 nohup $UNITY_PATH -quit -batchmode -projectPath $UNITY_PROJECT_PATH -logFile $UNITY_LOG_PATH -executeMethod CNC.Editor.PackageBuilderMenu.BuildPC "${isMono} ${isDevelop} $UNITY_OUT_PATH" & echo $! > /tmp/unity_${BK_CI_BUILD_ID}.pid unity_main_pid=$(cat /tmp/unity_${BK_CI_BUILD_ID}.pid) tail -f --pid ${unity_main_pid} $UNITY_LOG_PATH
```

### Q: How do I conditionally execute the CallPipeline plug-in

Under the plug-in, there is a flow control, where you can add running conditions as needed to meet the requirements

![img](../../.gitbook/assets/wecom-temp-70083f622bd2a6c839f9eb1b9436aac2.png)

### Q: Does CallPipeline seem to be unable to pass parameters like this?

![img](../../.gitbook/assets/wecom-temp-3d80fac2503d5be8620e76b0d8175798.png)

The variable needs to be referenced in this way`${flushDB}`

### Q: How do I refer to global variables? I don't think I can refer to $BK_CI_BUILD_FAIL_TASKS

Variable references need curly braces`${BK_CI_BUILD_FAIL_TASKS}`

### Q: Can other parameters be hidden when the selected parameter is changed? For example, I select build for operator and hide tag parameter, just like the change event of option component in js

![img](../../.gitbook/assets/企业微信截图_1634710197325.png)

Not yet

### Q: When I click Execute, can the value in the parameter drop-down list be obtained through the custom interface?

Interface customization is not supported

### Q: The server disk is full. Can I delete files in these directories

![img](../../.gitbook/assets/企业微信截图_1635304491832.png)

These are build artifacts, and there is currently no expiration cleanup policy for build artifacts, which users can delete as appropriate

### Q: How do I change parameter values during pipelining?

If you are a shell plug-in, you can change the value of the parameter this way`setEnv "{KEY}" "{VALUE}"`

### Q: 1.5.4 CI, how do I call openapi

Version does not have OpenAPI enabled. You can upgrade to version 1.5.30 or later, which has OpenAPI enabled.

### Q: How do I view the information in the credentials

![img](../../.gitbook/assets/企业微信截图_16372883269771-4480877.png)

For security reasons, this content is encrypted and cannot be viewed

### Q: The code checks whether lua is supported

Code review does not support lua yet

### Q: Can I extend the code review rules myself

At present, the self-extension function is still under development, and users do not support self-extension code check rules

### Q: How do I make pipelining tasks optional

```
In the plugin, select "Skip some on manual trigger"
```

![img](../../.gitbook/assets/wecom-temp-ef4f873c64f962cc9582479c26442f2f.png)

### Q: Do you want bkci's log window to retain color? I want to make the failures more obvious

Refer to https://docs.bkci.net/reference/faqs/log-colors

### Q:job- Job execution plugin is grey, but I have installed it

![img](../../.gitbook/assets/企业微信截图_16384260669700.png)

This is a plug-in for non-compiler environments. You need to select a linux compiler when selecting the JOB type

![img](../../.gitbook/assets/image-20220210193855866.png)

### Q: What is the service ID

![img](../../.gitbook/assets/企业微信截图_1638426248456.png)

Service ID in the configuration platform is also displayed in the job platform

![img](../../.gitbook/assets/image-20220210194131021.png)

![img](../../.gitbook/assets/image-20220210194135210.png)

### Q: If I want to execute a python task through a shell or bat, can I only pass the bkci variable through the python command line and not write the variable back to bkci?

Problem 1: bkci variables can be obtained by obtaining environment variables

```
# Single line python example, var is the name of a variable defined by the user in this or other steps，
# BK_CI_START_USER_NAME is global var of bkci
python -c "import os; print(os.environ.get('var'))"
python -c "import os; print(os.environ.get('BK_CI_START_USER_NAME'))"

# If you know the name of the variable you defined, you can also get it in your own python file via os.envion.get('var') 
cat << EOF > test.py
import os
print(os.environ.get('var'))
EOF
python test.py
```

Question 2: How do I write variables back to bkci

```
# If it's a constant, the shell can use setEnv and bat can use call:setEnv to write the variable back to Randle
setEnv "var_name" "var_value" # shell
call:setEnv "var_name" "var_value"  # bat

# Write the python script output back to Randle
var_value=`python script.py` # The script.py needs to have print output，如print("test")
setEnv "var_name" "${var_value}" # var_name="test"

# Write the variables to a file, then read the file in the shell and setEnv
python script.py > env.sh # Assumptions file_name="test.txt" in env.sh
source env.sh
setEnv "var_name" "${file_name}"
```

### Q: gitlab webhook error URL "**[http://devops.bktencent.com/ms/process/api/external/scm/gitlab/commit](http://devops.bktencent.com/ms/process/api/external/scm/gitlab/commit)**" is blocked: Host cannot be resolved or invalid

hosts resolution for devops.bktencent.com needs to be configured on the gitlab machine

### Q: How do I enter the red box?

![img](../../.gitbook/assets/企业微信截图_16257162702433.png)

"R&d Shop" - "Workbench"

![img](../../.gitbook/assets/wecom-temp-f1631f05683e7125be01a6b4e79492dd.png)

### Q: I think each job has its own workspace. Do multiple jobs share a workspace?

If a single build machine (private build machine) is used, multiple jobs share a workspace

### Q: What is the reason for this error when using the "git pull code" plug-in? The ssh private key is used

![img](../../.gitbook/assets/企业微信截图_16266633248073.png)

This is because the old git pull code plug-in is not supported for use on the windows build machine. The latest version of the Git pull code plug-in is supported

### Q: Does bkiam v3 failed?

![img](../../.gitbook/assets/企业微信截图_16273862334714.png)

This problem is usually caused by the restart of the machine and the saas container in the permission center does not start. The problem can be solved by pulling the container back up

### Q: What if I want to force a code scan when I mention pr?

If you are using gitlab managed code, configure the gitlab trigger directly. The event types are as follows:

1. Commit Push Hook Triggered when the code is committed
2. Tag Push Hook Triggered when the tagged code is submitted
3. Merge Request Hook Merge request hook is triggered when code is merged
4. Merge Request Accept Hook The merge request accepts hook

### Q: Some rules in the code review do not apply to our company. How to modify the rules?

The content of a rule cannot be modified, but the rule set can be modified. The code check is based on the rule set. If some rules are not applicable, you can remove them from the rule set. If the rule set is the default rule set, you can create a custom rule set based on the rule set

### Q: The code check fails. Unknown Error: Unexpected char 0x5468 at 0 in X-DEVOPS-UID value: xxx

![img](../../.gitbook/assets/企业微信截图_1630326503372.png)

This step will read the fullname of gitlab, set to English can solve the problem, Chinese gitlab fullname is not supported for the time being, fullname above the display of personal information user name, such as vinco huang here, You can access the modification page by clicking Edit profile here

![img](../../.gitbook/assets/企业微信截图_16303286841990.png)

### Q: I want to send an artifacts file with a link from the current build in the company micromessage notification. How do I construct the download link for the attachment?

*[http://devops.bktencent.com/ms/artifactory/api/user/artifactories/file/download/local?filePath=/bk-archive/panda/BK_CI_P](http://devops.bktencent.com/ms/artifactory/api/user/artifactories/file/download/local?filePath=/bk-archive/panda/)* IPELINE_ID/{BK_CI_BUILD_ID}/{file name of your artifacts}

### Q: Does the docker public build support its own mirror?

Support, refer to https://docs.bkci.net/store/ci-images

### Q: Does bkci support pipelining on an idle machine in a private build cluster? For example, if we compile a packaging server, there may be multiple people working on the packaging of different branches at the same time?

If there are multiple private construction machines, a private construction cluster can be formed. After selecting this cluster, the bkci pipeline selects one of them to build according to a certain algorithm:

**The algorithm is as follows:**

**The highest priority agent:**

1. This builder was used in a recent build task
2. There are currently no build tasks

**agent of the second highest priority:**

1. This builder was used in a recent build task
2. There are currently build tasks, but the number of build tasks does not reach the maximum concurrency of the current builder

**agent of the third priority:**

1. There are currently no build tasks

**agent of the fourth priority:**

1. There are currently build tasks, but the number of build tasks does not reach the maximum concurrency of the current builder

**Lowest priority:**

1. None of them meet the above criteria

### Q: [**https://docs.bkci.net/**](https://docs.bkci.net) won't open

![img](../../.gitbook/assets/企业微信截图_16342628987332.png)

This document is hosted by gitbook and requires access to some of Google's resources, which can be a problem if the user doesn't have web access to Google

### Q: The machine restarted after power failure, but some services of BK did not work. Are these services not set to start from the boot?

There are dependencies between services. For example, some BK services depend on mysql. If these services are started before mysql, they will fail to start

### Q: I have pipeline A, which can be executed separately, and I have pipeline B, which will call A and wait for A result of A. How can I make this mutually exclusive

**Space occupied, to be filled**

### Q: You can set permissions for pipelines. For example, for ten pipelines under A project, A can see part of them, while B can only see the other part. I want to divide them according to functions

Permission centers can be managed on a single pipeline by first granting permissions to a specific user for a project and then to a single pipeline

![img](../../.gitbook/assets/wecom-temp-478bbf51b9813c4ec50828781038028b.png)

![img](../../.gitbook/assets/wecom-temp-d29b308520dfa33da51158b2d5c055a9.png)

![img](../../.gitbook/assets/wecom-temp-1e44f6048453bb9873ad1cc81c869a5e.png)

### Q: Can the variables of the pipeline be linked? For example, if I select the value of variable 1 as A, the value of variable 2 will automatically change to A?

Linkage is not supported yet. If the value does not change, can we set the default value

### Q: Are there any plugins that support git push? I want to push something to the repository

You can try to push it by keeping the account close: git push http://username:passwd@xxx, username, and passwd can be managed using credentials. username and passwd do not allow special characters. bkci does not escape special characters when rendering variables

### Q: How do I restart bkci agent on a private build

In the installation directory of the bkci agent, run the stop.sh script (stop.bat file on windows) and then start.sh (start.bat file on windows).

### Q: How do I reinstall bkci agent on a private builder

1. On linux/Mac, you can run the installation command again. If an installation error occurs, you are advised to uninstall, delete the installation directory, and run the installation command again
2. uninstall on windows, delete the installation directory, download the installation package, and repeat the installation process

### Q: How do I use the pipelined view function

The view can classify pipelinesby the creator of the pipelinesor by the pipelinesname. It supports and/or relationships between multiple conditions. The key value of a condition is the logic of include`vinco`Is matched to all pipeline names included in the project`vinco`Line of letters

![img](../../.gitbook/assets/image-20220125152014075.png)

![img](../../.gitbook/assets/image-20220125152350168.png)

### Q: The TGit plug-in cannot select the gitlab codebase

TGit is connected with Tencent's worker bee code base, and gitlab code base cannot be used

### Q: Timed trigger pipeline. The time display is incorrect, and the trigger time is incorrect

![img](../../.gitbook/assets/wecom-temp-26d5087b12647b6801f5d8471eeb3ee6.png)

Check whether the time of the bkci server is normal

### Q: Can the history page of pipeline display custom content? For example, the same pipeline is sometimes packaged for Android and sometimes for ios. By looking at the history page, the built content cannot be distinguished

![img](../../.gitbook/assets/企业微信截图_16364221097534.png)

You can add a shell **plug-in** to the pipeline by setting `BK_CI_BUILD_REMARK`The value of the global variable to implement the desired remarks. The field will not be displayed until the pipeline is finished

![img](../../.gitbook/assets/wecom-temp-a4453da39a470d74b7ed3d6da14120c0.png)

![img](../../.gitbook/assets/wecom-temp-9418a7960b89c65268c6947f46d95f72.png)

### Q: The bkci agent fails to be installed on the windows builder because the subdirectory or file already exists and access is denied

![img](../../.gitbook/assets/企业微信截图_16393825053890-3096967.png)

In this case, the agent is repeatedly installed. To uninstall the agent, run Uninstall script, delete the installation directory of the agent, download the agent package, and install the Agent again

### Q: bkci's execution history has a place to set the upper limit, my timing pipeline may be once a minute, data will waste disk

BK's platform is recommended for high frequency timing tasks

### Q: Ubuntu BK agent installation failed. There is no enough space left in /tmp, but there is disk space left

![img](../../.gitbook/assets/企业微信截图_16316948048063.png)

The awk command cannot be executed normally on the Ubuntu machine. The following error occurs when awk is executed:

```
awk: symbol lookup error: /usr/local/lib/libreadline.so.8: undefined symbol: UP
```

You can refer to this method to replace:

![img](../../.gitbook/assets/wecom-temp-62020c1b6e41f1f9e6e421bfe0a7dc70.png)

### Q: The image authentication fails when a mirror is associated

![img](../../.gitbook/assets/企业微信截图_16328099498489.png)

![img](../../.gitbook/assets/wecom-temp-96f388a0cface3bdddafa174084719a1.png)

By default, docker does not support non-HTTPS private repositories. Therefore, you need to modify /etc/docker/daem. json on the public builder`insecure-registries`Add the private repository address to the field and restart docker

![img](../../.gitbook/assets/image-20220301101202-lncwv.png)

### Q: Are there any images of bkci based on Ubuntu

No ready-made bkci image based on Ubuntu, users can according to the guide to package their own mirror image: https://bk.tencent.com/docs/document/6.0/129/7518

### Q: If I have more than one common builder, what is the scheduling algorithm for the common builder, and in what cases will tasks be scheduled to be executed on another builder?

The algorithm preferentially selects the last built machine (affinity). If a resource of the last built machine exceeds the following threshold, the algorithm finds another build machine to perform the build task

```
 Memory threshold: 80% Disk I/O: 85% Disk space: 90%
```

### Q: How do I adjust the resource threshold in the scheduling algorithm

Currently, only the memory threshold can be adjusted, and the default value is 80%. That is, when the memory usage of a common builder reaches 80% and other builders have free resources, tasks will be scheduled to other builders. The threshold can be modified by logging in to the bkci dispatch-docker server and performing the following operations:

```
 # The value of threshold is the threshold percentage, here the memory threshold is adjusted to 70% for example 
curl -H 'Accept:application/json;charset="utf-8"' -H 'Content-Type:application/json;charset="utf-8"' -H "X-DEVOPS-UID: admin" -X POST --data '{"threshold":"70"}' http://127.0.0.1:21938/api/op/dispatchDocker/docker/threshold/update
```

### Q: Occasionally, the startup build machine fails to start and Get credential failed

If the problem is known, delete dispatch-docker/lib/bcprov-jdk15on-1.64.jar. This is a soft chain. Just delete it and restart the dispatch-docker service`systemctl restart bk-ci-dispatch-docker.service`

### Q: How do I delete a common builder

Log in to the machine for the bkci dispatch-docker service and execute`/data/src/ci/scripts/bkci-op.sh list`Get all the public builders and execute`/data/src/ci/scripts/bkci-op.sh del`operation

### Q: The build step is stuck in preparing the build environment

![img](../../.gitbook/assets/企业微信截图_16419529383724.png)

If it is a public builder, check whether the service of the public builder bk-ci-dockerhost.service is normal

This is common on private build machines. It is usually caused by agent installation exceptions. Here are some known causes:

1. For example, the bkci domain name cannot be resolved or the bkci service is unreachable
2. The agent version is incorrectly installed. For example, if the linux agent package is installed on the mac, delete the bkci agent installation package and reinstall the agent of the corresponding version
3. It can be found in the agentDaemon.log file under logs in the bkci agent installation directory`too many open files`, execute on the machine`ulimit -n`The result shows that the number of files that can be opened is too small. The default value is 1024. You can increase the value and reinstall the bkci agent

![img](../../.gitbook/assets/wecom-temp-2cf366a83acf24ef09ae7dff30c47354.png)

![img](../../.gitbook/assets/wecom-temp-2eadbe319d03b3049c6b4cf300cda012.png)

### Q: Pipeline construction fails because the Agent heartbeat times out or the Agent is Dead. Check the status of the builder

This is common when a memory-consuming compilation task is executed on a public build machine, resulting in an oom container`grep oom /var/log/messages`The matching record is usually displayed. If oom is caused by multiple tasks running on the same builder, you can adjust the memory threshold of the scheduling algorithm to prevent multiple tasks from running on a single builder. If a single compilation task triggers oom, you are advised to increase the memory of the builder or use a private builder with a higher memory
