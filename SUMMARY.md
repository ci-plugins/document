# Table of contents

* [首页](README.md)

## 🐤 了解基本概念 <a id="overview"></a>

* [BKCI 是什么？](overview/what-is-bkci.md)
* [BKCI 组件](overview/components.md)
* [5分钟读懂 BKCI 流水线](overview/learn-pipeline-in-5-min.md)
* [术语解释](overview/terminology/README.md)
  * [Pipelines](overview/terminology/pipelines.md)
  * [Stage](overview/terminology/stage.md)
  * [Job](overview/terminology/job.md)
  * [Task](overview/terminology/task.md)
  * [Trigger](overview/terminology/trigger.md)
  * [Variables](overview/terminology/variables.md)

## 👉 使用 BKCI <a id="tutorials"></a>

* [创建你的第一条流水线](tutorials/create-first-pipeline.md)
* [关联你的第一个代码库](tutorials/link-first-repo.md)
* [为你的Git工程开启CI](tutorials/enable-git-ci.md)
* [示例](tutorials/examples/README.md)
  * [Java Maven Demo](tutorials/examples/java-maven-demo.md)
  * [Node Demo](tutorials/examples/node-demo.md)

## 🚀 部署 BKCI <a id="setup"></a>

* [BKCI 系统要求](setup/system-requirements/README.md)
  * [BKCI 硬件规格指南](setup/system-requirements/hardware-specifications.md)
* [使用 One-Docker 运行 BKCI 的学习环境](setup/run-bkci-in-one-docker.md)
* [在生产环境中运行 BKCI](setup/run-bkci-in-prod/README.md)
  * [将 BKCI 一键部署至腾讯云](setup/run-bkci-in-prod/on-tencentcloud.md)
  * [在蓝鲸社区版中部署 BKCI](setup/run-bkci-in-prod/on-bkce.md)

## 📔 产品功能 <a id="services"></a>

* [控制台](services/console.md)
* [流水线](services/pipelines/README.md)
  * [流水线列表页](services/pipelines/pipeline-list.md)
  * [流水线执行历史](services/pipelines/pipeline-build-history.md)
  * [创建/编辑流水线](services/pipelines/pipeline-edit/README.md)
    * [流水线图形化编排](services/pipelines/pipeline-edit/gui.md)
    * [为流水线开启自定义构建号](services/pipelines/pipeline-edit/alias-buildno.md)
    * [锁定流水线](services/pipelines/pipeline-edit/disable-pipeline.md)
  * [流水线任务详情页](services/pipelines/pipeline-build-detail/README.md)
    * [流水线状态信息汇总](services/pipelines/pipeline-build-detail/status.md)
* [构建资源](services/pools/README.md)
  * [将你的构建机托管至 BKCI](services/pools/self-hosted-agents/README.md)
    * [第三方构建机环境准备](services/pools/self-hosted-agents/prepara-agent.md)
  * [构建机详情页](services/pools/agent-detail.md)
* [凭证管理](services/ticket.md)
* [代码库](services/repo.md)

## 🏪 研发商店 <a id="store"></a>

* [浏览研发商店](store/store-home.md)
* [流水线模板](store/pipeline-templates.md)
* [CI镜像](store/ci-images/README.md)
  * [构建并托管一个CI镜像](store/ci-images/image-build.md)
  * [发布一个CI镜像](store/ci-images/image-release.md)
* [流水线插件](store/plugins/README.md)
  * [开发一个流水线插件](store/plugins/create-plugin/README.md)
    * [插件开发指引](store/plugins/create-plugin/plugin-dev-guide/README.md)
      * [Java 插件开发指引](store/plugins/create-plugin/plugin-dev-guide/java.md)
      * [Python 插件开发指引](store/plugins/create-plugin/plugin-dev-guide/python.md)
      * [Golang 插件开发指引](store/plugins/create-plugin/plugin-dev-guide/golang.md)
      * [NodeJS 插件开发指引](store/plugins/create-plugin/plugin-dev-guide/nodejs.md)
    * [插件开发规范](store/plugins/create-plugin/plugin-specification.md)
    * [插件配置规范](store/plugins/create-plugin/plugin-config.md)
    * [插件输出规范](store/plugins/create-plugin/plugin-output.md)
    * [插件错误码规范](store/plugins/create-plugin/plugin-error-code.md)
    * [插件发布规范](store/plugins/create-plugin/release.md)
    * [插件自定义UI](store/plugins/create-plugin/plugin-custom-ui.md)
  * [在 BKCI 里使用商店插件](store/plugins/upload-plugin.md)

## 🤝 一起共建 BKCI <a id="contribute"></a>

* [BKCI 架构](contribute/architecture.md)
* [BKCI 代码结构](contribute/code-framework.md)
* [设计理念](contribute/design.md)

## ℹ️ 参考信息 <a id="reference"></a>

* [REST API](reference/rest-api.md)
* [预定义变量列表](reference/pre-define-var.md)
* [FAQS](reference/faqs.md)
* [系统限制](reference/limit/README.md)
  * [流水线复杂度限制](reference/limit/pipeline-limit.md)

---

* [返回 BKCI 官网](https://bkci.net)

