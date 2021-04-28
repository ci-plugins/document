# Variables



### 在流水线中定义变量 <a id="&#x5728;&#x6D41;&#x6C34;&#x7EBF;&#x4E2D;&#x5B9A;&#x4E49;&#x53D8;&#x91CF;"></a>

#### 在编排流水线时自定义变量 <a id="&#x5728;&#x7F16;&#x6392;&#x6D41;&#x6C34;&#x7EBF;&#x65F6;&#x81EA;&#x5B9A;&#x4E49;&#x53D8;&#x91CF;"></a>

在编辑流水线页面点击 Job1-1，可以添加流水线变量。 

![](../../.gitbook/assets/image%20%286%29.png)

#### 在流水线插件中设置变量 <a id="&#x5728;&#x6D41;&#x6C34;&#x7EBF;&#x63D2;&#x4EF6;&#x4E2D;&#x8BBE;&#x7F6E;&#x53D8;&#x91CF;"></a>

如果你在 bk-ci 中开发了自己的流水线插件，可以在插件的 task.json 中定义 output 字段，这样也可以在运行该插件时声明这些变量。

#### 通过 Bash 插件设置变量 <a id="&#x901A;&#x8FC7; Bash &#x63D2;&#x4EF6;&#x8BBE;&#x7F6E;&#x53D8;&#x91CF;"></a>

您可以通过 Shell Script 插件中的 setEnv 函数设置插件间传递的参数，用法如下：

```bash
#!/usr/bin/env bash
# setEnv "FILENAME" "package.zip"
# 然后在后续的插件的表单中使用${FILENAME}引用这个变量
```



### 在流水线中引用变量 <a id="&#x5728;&#x6D41;&#x6C34;&#x7EBF;&#x4E2D;&#x5F15;&#x7528;&#x53D8;&#x91CF;"></a>

你可以在任意的插件表单中使用通过上面介绍的方式定义的变量，引用方式为${KEY}

### 在手动触发流水线时设置变量值 <a id="&#x5728;&#x624B;&#x52A8;&#x89E6;&#x53D1;&#x6D41;&#x6C34;&#x7EBF;&#x65F6;&#x8BBE;&#x7F6E;&#x53D8;&#x91CF;&#x503C;"></a>

1. 在编辑流水线时定义了流水线变量，并开启了“执行时显示”选项时，则会在运行流水线后进入**流水线预览页**；
2. 进入预览页，你可以再次编辑你的变量 value 并运行流水线。

![](../../.gitbook/assets/image%20%2819%29.png)

![Var](https://bkdocs-1252002024.file.myqcloud.com/ZH/6.0/%E6%8C%81%E7%BB%AD%E9%9B%86%E6%88%90%E5%B9%B3%E5%8F%B0/%E4%BA%A7%E5%93%81%E7%99%BD%E7%9A%AE%E4%B9%A6/assets/variables_5.png)

> 变量 Key 在执行时不可修改，只能修改 value。

### 接下来你可能需要 <a id="&#x63A5;&#x4E0B;&#x6765;&#x4F60;&#x53EF;&#x80FD;&#x9700;&#x8981;"></a>

* [预定义变量列表](../../reference/pre-define-var.md)

