# 常见问题

## Q1: 插件变量值的获取及引用

右上角点击引用变量，然后点右边复制变量，然后粘贴到你需要的地方就可以

![](../../.gitbook/assets/wecom-temp-edfeb72810d972dae34d3f8d98232ec6.png)

自定义的变量如何定义及如何引用，可以参考文档：

[变量定义及引用](https://docs.bkci.net/overview/terminology/variables)

## Q2: 使用 shell 或 bat 执行任务python脚本时，如何将变量回写到蓝盾中？

问题一：可以通过获取环境变量的方式来获取蓝盾的变量

```
# 单行python例子，var为用户在本步骤或者其他步骤定义的变量名，BK_CI_START_USER_NAME是蓝盾的全局变量
python -c "import os; print(os.environ.get('var'))"
python -c "import os; print(os.environ.get('BK_CI_START_USER_NAME'))"

# 如果你知道自己定义的变量名字，也可以在自己的python文件里通过os.envion.get('var')来获取
cat << EOF > test.py
import os
print(os.environ.get('var'))
EOF
python test.py
```

问题二：如何将变量回写到蓝盾

```
# 如果是常量，shell可以使用setEnv，bat可以使用call:setEnv来将变量回写到蓝盾
setEnv "var_name" "var_value" # shell
call:setEnv "var_name" "var_value"  # bat

# 将python脚本输出结果写回蓝盾
var_value=`python script.py` # script.py里需要有print输出，如print("test")
setEnv "var_name" "${var_value}" # var_name="test"

# 把变量写到一个文件中，然后在shell中读取这个文件，然后setEnv
python script.py > env.sh # 假设env.sh里为file_name="test.txt"
source env.sh
setEnv "var_name" "${file_name}"
```

问题三：bat 脚本中调用 python ，将 python 输出回写到蓝盾

````
for /F %%i in('python3 D:\mytest.py') do (set res=%%i)
echo %res%
call:setEnv "var_name" %res%
````

---

## Q3：如何有条件的执行插件

每个插件都为一个 task，通过高级流程控制，可以定义插件的运行逻辑。

[task 说明](https://docs.bkci.net/overview/terminology/task)

## Q4：插件安装后无法使用

大致分为两种情况

①：插件安装后，选择插件时没有对应的插件：

插件还需要安装到对应项目，才可以在项目里选择插件。具体请参考：

[插件安装](https://docs.bkci.net/store/plugins/plugin_install_demo#liu-an-zhuang-cha-jian)

②：插件安装后，插件为灰色状态无法选择

![](../../.gitbook/assets/企业微信截图_16384260669700.png)

插件分为：有编译插件和无编译插件。编译插件又分三种环境：Linux、windows、macOS

新建 stage 时，要选择和插件对应环境的 stage，才能选择对应的插件。

job 插件为无编译环境插件，需要选择无编译环境的stage才可以。

## Q5: 请问流水线的变量能联动吗，比如我下拉选择了变量1的值为A，变量2的值自动变为A？

暂时还不支持联动，如果值没什么变化，可以设置默认值

## Q6: 如何执行 git push 的操作

可以试着用账密的方式push： git push [http://username:passwd@xxx](http://username:passwd@xxx)，username和passwd可以使用凭证管理起来，username和passwd不允许有特殊字符，蓝盾在渲染变量的时候，不会转义特殊字符

## Q7: 流水线构建失败，Agent心跳超时/Agent Dead，请检查构建机状态

常见于在公共构建机上运行耗费内存的编译任务，导致容器oom，在公共构建机上执行`grep oom /var/log/messages`通常能看到匹配记录，如果是因为多个任务同时跑在同一台构建机上导致oom，可以通过调整调度算法的内存阈值，避免单台构建机上运行过多任务；如果单个编译任务就触发oom，建议调高构建机的内存，或者使用内存更高的私有构建机

## Q8：插件执行失败download plugin execute file fail

通常是由于 mongodb 服务异常导致的问题。

在中控机中，执行 ```./bkcli restart mongodb``` 恢复服务即可

## Q9：构建任务中插件长时间卡住（超过超时时间仍未终止）

插件默认的超时时间为 900min，若超过超时时间仍未终止，通常是 process 或 project 服务出现了异常。

需进入蓝盾机器，重启服务 

```systemctl status bk-ci-project.service ```

```systemctl status bk-ci-process.service``` 

---

# gitlab 触发插件

## Q1: gitlab触发插件无法触发流水线

1. 检查分支是否匹配

2. 查看下devops\_ci\_process.T\_PIPELINE\_WEBHOOK表是否有注册这条流水线， SELECT \* FROM devops\_ci\_process.T\_PIPELINE\_WEBHOOK WHERE pipeline\_id = ${pipeline\_id}，${pipeline\_id}可以从url地址获取

3. 如果没有注册

   1. 查看repository服务到gitlba的网络是否能通，比如是否配置gitlab的域名解析

   2. 查看gitlab仓库的权限是否是master权限。生成accesstoken的用户需要是仓库的`maintainer`角色，且accesstoken 的 Scopes需要具有`api`权限

   3. 在repository服务部署的机器上，执行grep "Start to add the web hook of " $BK\_HOME/logs/ci/repository/repository-devops.log查找注册失败原因，$BK\_HOME默认是/data/bkce

4. 如果已注册，还是没有触发，

   1. 到gitlab的webhook页面，查看是否有注册成功，如图1

   2. 如果gitlab中有注册的url，url是 [http://域名/external/scm/codegit/commit](http://xn--eqrt2g/external/scm/codegit/commit) 然后点击编辑，查看View detail，如图2

   3. 查看发送的错误详情，如图3。检查gitlab到蓝盾机器的网络是否可达，如gitlab服务器是否能解析蓝盾域名。

5. 如果上面都没问题，在process服务部署的机器上，执行grep "Trigger gitlab build" $BK\_HOME/logs/ci/process/process-devops.log 搜索日志，查找触发的入口日志，查看gitlab push过来的请求体。

   注意查看gitlab push过来的请求体，对比请求体中的`http_url`字段和代码库里代码仓库的地址是否**完全**匹配，如果一个是域名形式的url，另一个是ip形式的url，则不匹配。如图4、图5

![](<../../.gitbook/assets/image (58) (1).png>)

![](<../../.gitbook/assets/image (59).png>)

![](<../../.gitbook/assets/image (57).png>)

<img src="../../.gitbook/assets/image-trigger-gitlab-webhook-post-body.png" alt="" data-size="original"><img src="../../.gitbook/assets/image-trigger-gitlab-repo-ip-view.png" alt="" data-size="original">

## Q2: 如何使用Merge-Request-Accept-Hook

![](../../.gitbook/assets/image-20220301101202-RtEPQ.png)

Merge Request Accept Hook会在源分支**成功merge到目标分支时触发**

比如，需要将feat\_1合并到dev分支时，分支名称写dev，监听源分支写feat\_1（也可以使用\*号的模糊匹配功能，如feat\_\*）

![](../../.gitbook/assets/image-20220301101202-pxOZb.png)

## Q3: gitlab触发器在哪里配置webhook地址，jenkins是需要手动配置一个url的

不需要配置这个hook，蓝蓝盾是会自己注册webhook，选择事件类型后保存，就会自动注册webhook

![](../../.gitbook/assets/wecom-temp-d5c48ee99a96d373426491d14d56e404.png)



## Q4: 有条流水线通过gitlab提交触发了，但查看代码变更记录为空。说明此次触发的构建，并没有新代码变更，却仍然触发了流水线

可能的原因是，触发器监听了整个代码库的commit事件，但代码拉取插件只拉取了某一个特定分支的代码，而此分支并没有代码变更，比如，插件监听了整个代码库commit事件，但代码拉取插件只拉取了master分支的代码，而提交commit的是dev分支，代码变更记录显示的是所拉取的分支相交上一次体检的变更，master分支没有变更，所以没有变更记录。

## Q5：gitlab webhook 报错 

URL '[**http://devops.bktencent.com/ms/process/api/external/scm/gitlab/commit**](http://devops.bktencent.com/ms/process/api/external/scm/gitlab/commit)' is blocked: Host cannot be resolved or invalid

gitlab 无法解析蓝盾的域名。

需要在gitlab的机器上配置devops.bktencent.com的hosts解析

## Q6: 提pr时想触发流水线应该如何配置

如果是使用gitlab托管代码，直接配置gitlab触发器，触发的事件类型有：

1. Commit Push Hook 代码提交时触发
2. Tag Push Hook 提交有tag的代码时触发
3. Merge Request Hook 当有代码合并时触发
4. Merge Request Accept Hook 当代码合并后触发

## Q7: 监听和排除有优先级吗？

监听 > 排除

假设 trigger 既配置了监听选项，又配置了排除选项，且事件中既包含监听又包含排除，那么将会触发该流水线。

## Q8:监听的路径可以进行通配吗？

不支持通配符功能。目前可以支持前缀匹配功能。

例如在监听目录中填写 source，而 sourceabc 目录进行了变更，也会监听到该事件。

---

# Upload artifacts

## Q1、upload后文件去哪了？

upload 后，文件上传到了蓝盾服务器当中。

## Q2、Artifacts 是什么？

Artifacts 是蓝盾服务器的路径。

 /data/bkce/public/ci/artifactory/bk-archive/${项目名称}

## Q3、制品 upload 的绝对路径是什么？

比如项目名称是vincotest，114514.txt实际存放路径就是蓝盾机器上：

/data/bkce/public/ci/artifactory/bk-archive/vincotest/${流水线id}/${构建id}/114514.txt

项目名称、流水线ID、构建ID都可以从流水线url里读取到

![](../../.gitbook/assets/image-20220607165825062.png)

## Q4：上传时报错

**①：没有匹配到任何待归档文件**

![](../../.gitbook/assets/uploadsrcfile.png)

原因：没有匹配到对应的文件

常见于文件路径问题导致的报错。upload时默认从蓝盾的 ${WORKSPACE} 开始以相对路径匹配制品。

因此如果对应的制品在${WORKSPACE}的更下一级目录时，需要填写 路径/文件

**②：报告任务完成失败**

通常原因有两个

1. 上传的包体过大，CI 服务器资源不足，负载过高，导致服务出现异常

2. 上传 时会使用到 /tmp 目录，/tmp 空间磁盘容量不足导致。因此 /tmp 也需要保持足够的空间。

# Download artifacts



# python 插件

## Q1: python的环境变量添加后，在job执行的时候未生效。（job报错“系统找不到指定的文件”）

因为蓝盾agent和蓝鲸agent使用的账户是system，所以加到administrator的环境变量不生效 需要把python.exe和pip3.exe pip.exe加入到系统环境变量里，再重启操作系统

## Q2: windows构建机 流水线执行用python去打开exe 失败

windows下，agent无法拉起有UI界面的exe

这个是windows session 0 限制

## Q3：windows构建机，python 打印工作空间失败

如果构建机指定了工作路径，例如 **D:\testworkspace\source** , 在python中直接 print 打印工作空间将会失败。

因为python会把 \ 作为转义符转义。需要以 r'' 的形式打印

```python
print(r'${workspace}')
```

# checkout 插件

## Q1: failed to connect to gitlib.xxx.com port 443:connection timed out 构建失败 提示连接443端口超时

![](../../.gitbook/assets/image-20220301101202-AaxCJ.png)

这里断网的原因是dockerhost启动后, 执行过sysctl -p等价的命令, 导致 net.ipv4.ip\_forward 被重置为0, 导致容器断网.

```
sysctl -p | grep -F net.ipv4.ip_forward
net.ipv4.ip_forward = 0
单独启动一个测试容器:
docker run -it --rm centos 
应该会看到
WARNING: IPv4 forwarding is disabled. Networking will not work.
容器内执行命令, 等待后会看到提示超时:
curl -m 3 -v paas.service.consul
然后执行 systemctl restart bk-ci-docker-dns-redirect
单独启动一个测试容器:
docker run -it --rm centos 
容器内执行命令, 可以看到网络恢复:
curl -v paas.service.consul
```

## Q2：卡死在 Fetching the repository

![](../../.gitbook/assets/check_ugit.png)

构建机使用的是Ugit

蓝盾需要使用原生的 git 拉取代码。如果构建机使用了 Ugit 则会导致蓝盾 checkout 失败。需要重新安装一次原生 git 。

## Q3: 获取凭证失败

![](../../.gitbook/assets/企业微信截图_16266633248073.png)

这是因为旧版git拉取代码插件不支持在windows构建机上使用，最新版插件已经支持

## Q4:拉取代码时，偶现报错

Such issues can arise if a bad key is used during decryption.

![](../../.gitbook/assets/checkout_error_sometimes.png)

①此为旧版checkout插件的问题，现已修复。

②如果仍有报错，一般是由于蓝盾服务器和构建机上 bcprov-jdk 版本不一致导致的问题。

请检查版本是否一致：

构建机：agent目录\jre\lib\ext

蓝盾服务器：/data/bkce/ci/ticket/lib/

如不一致，进行重装构建机agent重装即可解决。

---

# Upload artifacts

## Q1: Upload artifacts这个上传功能是上传到当前使用stage的构建的构建机里面还是有单独的仓库位置

归档构件，是把构建机上的产物归档到专用的产物仓库，产物仓库和构建机无关，由 Artifactory 服务决定。

CI 的归档，是将产物暂存到仓库，方便流水线下游操作使用，或者作为后续部署的来源，目前没有支持归档时根据当前构建机所在的云指定构件存储方式。

你描述的，看起来像是构件的分发，通过部署工具去操作可能更合理。

或者你也可以自定义插件自行实现归档

# executeJobScript

## Q1: private configuration of key JOB\_HOST is missing

![](../../.gitbook/assets/image-20220301101202-QtZoR.png)

job脚本执行插件链接：[https://github.com/TencentBlueKing/ci-executeJobScript](https://github.com/TencentBlueKing/ci-executeJobScript)

私有配置缺少JOB\_HOST字段，按照上图配置好即可

![](../../.gitbook/assets/脚本执行配置1.png)

# sendmail

## Q1: 发送邮件插件执行成功，但没收到邮件

1. 首先配置ESB的邮件信息，参考：[https://bk.tencent.com/s-mart/community/question/2532](https://bk.tencent.com/s-mart/community/question/2532)
2. 配置插件的私有配置，参考：[https://github.com/TencentBlueKing/ci-sendEmail](https://github.com/TencentBlueKing/ci-sendEmail)

## Q2: 发送邮件插件的sender配置不是我配置的sender

![](../../.gitbook/assets/image-20220301101202-gdDMH.png)

sender需要在插件的「私有配置」里设置，独立于ESB的mail\_sender

「研发商店」-「流水线插件」-「工作台」-「选择发送邮件插件」-「基本设置」-「私有配置」-「增加sender字段」

![](../../.gitbook/assets/wecom-temp-de1f999781431e708256b5e9a9ecc1d6.png)

![](../../.gitbook/assets/wecom-temp-79503b33558fb2f05c4579c99280f8e7.png)

![](../../.gitbook/assets/wecom-temp-ad2da5032b4af609e41012bd4113bf84.png)

![](../../.gitbook/assets/wecom-temp-888da4cdb34f2bbcdc3869f7f4ff6dda.png)

![](../../.gitbook/assets/wecom-temp-8f040f0a22d3e9b0ff75a6b3ff40410b.png)

![](../../.gitbook/assets/wecom-temp-db0217ab76483f286bfb63cd7047f353.png)

除了sender字段，还需要配置其他字段，请参考：[https://github.com/TencentBlueKing/ci-sendEmail](https://github.com/TencentBlueKing/ci-sendEmail)

# batchscript

## Q1: batchscript插件无法执行bat文件，bat文件里有从系统中读取的变量，是当前用户设置的

![](../../.gitbook/assets/企业微信截图/_16285831782937.png)

将对应的agent服务的启动用户改为当前用户，执行命令`services.msc`打开windows服务管理界面，找到服务`devops_agent_${agent_id}`(注意：每个agent\_id是不同的，agent\_id的值可以在配置文件.agent.properties中找到)

右键->属性，在登录页签下选择此账户

如果是如入域构建机，账户名填写`域名\用户名`，例如`tencent\zhangsan`;如果没有入域的构建机，账户名填入`.\用户名`,例如`.\admin、.\administrator、.\bkdevops`，输入密码后，点击确认按钮

![](../../.gitbook/assets/image-20220128181627246.png)

右键 -> 重新启动，重启服务

![](../../.gitbook/assets/image-20220128181720819.png)

打开任务管理器，查看进程devopsDaemon.exe和的vopsAgent.exe是否存在，查看两个进程的启动的用户名是否为当前登录用户

## Q2: batchscript中的命令路径有空格，执行失败

![](../../.gitbook/assets/企业微信截图_16285852671573.png)

可以将有空格的命令用引号""括起来

## Q3：构建机本地执行 Unity bat 脚本时成功，蓝盾执行报错

查看**脚本执行日志**后发现，本地执行时开启了88个线程的UnityShaderCompiler，但是蓝盾执行时，有些UnityShaderCompiler就吊起失败了。

报错：Failed to get ipc connection from UnityShaderCompiler.exe shader compiler!

原因：蓝盾需要为用到的exe开启进程，来收集错误和日志，创建的进程数超出了限制，会导致进程开启失败，导致流程失败。

解决办法：需增加系统可开启的进程数。

---

## Q4：无法执行带UI界面的程序

具体表现：同样的脚本在目标机器执行bat脚本没问题， 在蓝盾或者job平台不能执行

蓝盾开发团队给出的解释：

蓝盾第三方构建机windows agent默认以系统服务的方式启动，通过agent启动带界面UI的程序时会报错或者碰到界面被不可见的问题

原因：Windows Service启动的进程都运行在Session0内，Session0限制了不能向桌面用户弹出信息窗口、UI 窗口等信息。

 

碰到这种情况可以换一种方式启动agent，方式如下：

1. 如果agent已经安装成系统服务，执行 uninstall.bat 卸载agent服务

2. 双击 devopsDaemon.exe启动agent，注意**不要关掉弹出窗口**



**注1：这种方式启动的agent没有开机启动功能。**

**注2：蓝盾agent执行完构建任务后，会自动停止所有由agent启动的子进程，如果不需要结束子进程，可以在启动进程前设置环境变量：set DEVOPS_DONT_KILL_PROCESS_TREE=true**

**目前只有这种临时解决方式， 因为agent最开始设计就是如此**

---

# Shell script

## Q1 macos机器无法执行 shell 和 python 插件

问题如下：macOs的私有构建机使用shell插件执行命令报错， 什么命令都无法执行

![](../../.gitbook/assets/clip_image001.png)

使用python插件如下报错：

![](../../.gitbook/assets/clip_image002.png)

排查问题：

1. 确认macOs的默认shell环境是否正常cat /etc/shells、echo $SHELL，如下显示为正常

![](../../.gitbook/assets/clip_image003.png)

2. 查看构建机日志set up job日志，查看环境变量，查看环境变量是否都正常

![](../../.gitbook/assets/clip_image004.png)

 本次案例排查出环境变量LANG异常， 字符集LANG设置为zh_CN.eucCN 是错误的， 应该设置为zh_CN.UTF-8

![](../../.gitbook/assets/clip_image005.png)

原因：LANG字符集影响了中文值的变量export，导致整个sh脚本出错

解决方案：修改字符集为正确的字符集即可解决

 

## Q2 shell脚本执行异常

报错：java.io.IOException: No such file or directory

![](../../.gitbook/assets/clip_image006.png)

 排查问题：

1. 检查是否设置workspace，如设置先去掉再执行shell看是否成功， 如成功则是workspace设置问题

2. 检查workspace的目录创建的位置是否在用户目录下， 如果不是流水线无法访问到

 

原因：workspace权限问题

解决方法：正确创建workspace位置， 把权限设置对