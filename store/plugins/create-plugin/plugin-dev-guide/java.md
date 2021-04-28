# Java 插件开发指引

### 一、工程的整体结构如下 <a id="%E4%B8%80%E5%B7%A5%E7%A8%8B%E7%9A%84%E6%95%B4%E4%BD%93%E7%BB%93%E6%9E%84%E5%A6%82%E4%B8%8B"></a>

```text
|- pipeline-plugin
    |- bksdk   插件sdk
    |- demo    插件样例，你可以把工程项目名和内部逻辑修改成你自定义的
```

### 二、如何开发插件 <a id="%E4%BA%8C%E5%A6%82%E4%BD%95%E5%BC%80%E5%8F%91%E6%8F%92%E4%BB%B6"></a>

插件代码建议统一管理。通用的开源插件可以放到 [ci-plugins](https://github.com/ci-plugins) 下

请参考 [plugin-demo-java](https://github.com/ci-plugins/plugin-demo-java)

### 三、如何打成研发商店要求的zip包： <a id="%E4%B8%89%E5%A6%82%E4%BD%95%E6%89%93%E6%88%90%E7%A0%94%E5%8F%91%E5%95%86%E5%BA%97%E8%A6%81%E6%B1%82%E7%9A%84zip%E5%8C%85"></a>

1、进入pipeline-plugin目录下执行"mvn clean package"命令进行打包。

2、进入demo（插件逻辑所在的工程目录）目录下的target文件夹下就可以获取我们需要的zip包。

