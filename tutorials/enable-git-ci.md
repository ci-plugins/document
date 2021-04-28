# 为你的Git工程开启CI

### 准备事项 <a id="&#x51C6;&#x5907;&#x4E8B;&#x9879;"></a>

* 一个 gitlab 工程

如没有，请参考[关联你的第一个代码库](link-first-repo.md)

* 一个 bk-ci 项目
* 了解[流水线的基本概念](../overview/learn-pipeline-in-5-min.md)

### 通过 BK-CI 监听代码库 push 事件 <a id="&#x901A;&#x8FC7; BK-CI &#x76D1;&#x542C;&#x4EE3;&#x7801;&#x5E93; push &#x4E8B;&#x4EF6;"></a>

1. 创建一条空白流水线
2. 在 Job1-1 中添加触发器：GitLab![gitlab](https://bkdocs-1252002024.file.myqcloud.com/ZH/6.0/%E6%8C%81%E7%BB%AD%E9%9B%86%E6%88%90%E5%B9%B3%E5%8F%B0/%E4%BA%A7%E5%93%81%E7%99%BD%E7%9A%AE%E4%B9%A6/assets/quickstart_4.png)
3. 添加 Job2-1，用来执行具体的编译任务

   ![gitlab](https://bkdocs-1252002024.file.myqcloud.com/ZH/6.0/%E6%8C%81%E7%BB%AD%E9%9B%86%E6%88%90%E5%B9%B3%E5%8F%B0/%E4%BA%A7%E5%93%81%E7%99%BD%E7%9A%AE%E4%B9%A6/assets/quickstart_5.png)

4. 依次添加如下 3 个插件：
   * Checkout GitLab

     ![gitlab](https://bkdocs-1252002024.file.myqcloud.com/ZH/6.0/%E6%8C%81%E7%BB%AD%E9%9B%86%E6%88%90%E5%B9%B3%E5%8F%B0/%E4%BA%A7%E5%93%81%E7%99%BD%E7%9A%AE%E4%B9%A6/assets/quickstart_7.png)

   * Shell Script

     ![shell](https://bkdocs-1252002024.file.myqcloud.com/ZH/6.0/%E6%8C%81%E7%BB%AD%E9%9B%86%E6%88%90%E5%B9%B3%E5%8F%B0/%E4%BA%A7%E5%93%81%E7%99%BD%E7%9A%AE%E4%B9%A6/assets/quickstart_8.png)

   * Upload artifacts

     ![shell](https://bkdocs-1252002024.file.myqcloud.com/ZH/6.0/%E6%8C%81%E7%BB%AD%E9%9B%86%E6%88%90%E5%B9%B3%E5%8F%B0/%E4%BA%A7%E5%93%81%E7%99%BD%E7%9A%AE%E4%B9%A6/assets/quickstart_9.png)

