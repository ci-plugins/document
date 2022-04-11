# 使用变量来控制流水线

用户可以通过自定义变量来控制后续task的执行，从而达到控制流水线执行流的目的
**假设一种场景：** 当stage2的shell脚本执行成功的时候，stage3的shell脚本才执行

1. stage2 shell插件设置status变量

![shell脚本末尾设置status变量](../../../.gitbook/assets/image-variables-set-status-success.png)

2. stage3 shell插件选择「自定义变量全部满足时才运行」

![选择条件执行](../../../.gitbook/assets/image-variables-run-if-var-set.png)

3. shell插件新增执行条件变量为`status==success`

![设置执行条件](../../../.gitbook/assets/image-variables-status-condition.png)

4. 条件满足，执行成功

![条件满足执行成功](../../../.gitbook/assets/image-variables-run-success.png)

5. 模拟变量设置失败

![模拟条件不满足](../../../.gitbook/assets/image-variables-set-status-failed.png)

6. 条件不满足，插件不执行

![条件不满足脚本不运行](../../../.gitbook/assets/image-variables-skip-if-unsuccess.png)

类似地，还可以给插件反向设置执行条件：「自定义变量全部不满足时运行」

![自定义变量全部不满足时运行](../../../.gitbook/assets/image-variables-status-condition-not.png)