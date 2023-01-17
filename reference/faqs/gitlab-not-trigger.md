# Can the gitlab event trigger plugin fail to trigger events?

1. Check whether the pipeline_devops_ci_process. T_PIPELINE_WEBHOOK table is registered. SELECT * FROM devops_ci_process.T_PIPELINE_WEBHOOK WHERE pipeline_id = pipeline_id, {pipeline_id} can be obtained from the url
2. If not registered
   1. Check whether the repository service is connected to gitlba
   2. Check whether the gitlab warehouse has master permissions
   3. In the repository service deployment on the machine, The implementation of the grep "Start to add the web hook of" BK_HOME/logs/ci/repository/repository - the conversation. *Registered* the log to *find* *reasons* for *failure*, BK_HOME The default value is /data/bkce
3. If it's registered and still not triggered,
   1. Go to gitlab's webhook page and see if any registrations have been successful, as shown in Figure 1
   2. If you have any registered gitlab url, the url is [http://domain name/external/SCM/codegit/commit](http://域名/external/scm/codegit/commit) and then click edit, send details view, as shown in figure 2
   3. See the details that gitlab did not send, as shown in Figure 3
4. If above all no problem, in the process of service deployment machine, Perform the grep "Trigger gitlab build" $BK_HOME/logs/ci/process/process - the conversation. The log search logs, find out the entry log Trigger

![img](../../.gitbook/assets/image%20%2858%29%20%281%29.png)

![img](../../.gitbook/assets/image%20%2859%29.png)

![img](../../.gitbook/assets/image%20%2857%29.png)
