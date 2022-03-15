# Node Demo

本篇文章将指导你如何在 bk-ci 编译**NodeJS**工程。

## 准备材料 <a id="&#x51C6;&#x5907;&#x6750;&#x6599;"></a>

* 一个 NodeJS 工程：[https://gitlab.com/bk-ci/gs-maven.git](https://gitlab.com/bk-ci/gs-maven.git)
* 一个包含 npm 命令的 CI 镜像：[https://hub.docker.com/r/bkci/ci](https://hub.docker.com/r/bkci/ci)

## 详细步骤 <a id="&#x8BE6;&#x7EC6;&#x6B65;&#x9AA4;"></a>

1. 将准备好的 gitlab 代码库关联至 bk-ci，[请参考](../link-first-repo.md)
2. 创建一条空白流水线
3. 将 Linux 构建环境添加到 Job2-1，镜像地址填写：bkci/ci:latest 
   
   ![pic](https://bkdocs-1252002024.file.myqcloud.com/ZH/6.0/%E6%8C%81%E7%BB%AD%E9%9B%86%E6%88%90%E5%B9%B3%E5%8F%B0/%E4%BA%A7%E5%93%81%E7%99%BD%E7%9A%AE%E4%B9%A6/assets/examples_java_1.png)

4. 依次添加如下 3 个插件： 
   1. Checkout Gitlab 
   
   ![pic](https://bkdocs-1252002024.file.myqcloud.com/ZH/6.0/%E6%8C%81%E7%BB%AD%E9%9B%86%E6%88%90%E5%B9%B3%E5%8F%B0/%E4%BA%A7%E5%93%81%E7%99%BD%E7%9A%AE%E4%B9%A6/assets/quickstart_4.png) 

   2. Shell Scripts

      ```text
         #!/usr/bin/env bash
         npm run test
      ```

   3. Upload artifacts 
   
      ![pic](https://bkdocs-1252002024.file.myqcloud.com/ZH/6.0/%E6%8C%81%E7%BB%AD%E9%9B%86%E6%88%90%E5%B9%B3%E5%8F%B0/%E4%BA%A7%E5%93%81%E7%99%BD%E7%9A%AE%E4%B9%A6/assets/examples_node_1.png)

5. 运行流水线，观察结果 
   
   ![pic](https://bkdocs-1252002024.file.myqcloud.com/ZH/6.0/%E6%8C%81%E7%BB%AD%E9%9B%86%E6%88%90%E5%B9%B3%E5%8F%B0/%E4%BA%A7%E5%93%81%E7%99%BD%E7%9A%AE%E4%B9%A6/assets/examples_node_2.png)

