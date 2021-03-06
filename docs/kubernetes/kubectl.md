---
description: Kubernetes Command Line Tool
---

# kubectl

## [安装并配置 kubectl](https://kubernetes.io/zh/docs/tasks/tools/install-kubectl/) <a id="install-kubectl"></a>

使用 Kubernetes 命令行工具 [kubectl](https://kubernetes.io/zh/docs/reference/kubectl/kubectl/)， 您可以在 Kubernetes 上运行命令。 使用 kubectl，您可以部署应用、检查和管理集群资源、查看日志。 要了解 kubectl 操作的完整列表，请参阅 [kubectl 概览](https://kubernetes.io/zh/docs/reference/kubectl/overview/)。

{% tabs %}
{% tab title="Homebrew" %}
```bash
brew install kubectl
```
{% endtab %}

{% tab title="Snap" %}
```
snap install kubectl --classic
```
{% endtab %}

{% tab title="Chocolatey" %}
```
choco install kubernetes-cli
```
{% endtab %}

{% tab title="Scoop" %}
```
scoop install kubectl
```
{% endtab %}
{% endtabs %}

### Krew: kubectl 插件包管理器

[Krew](https://krew.dev/) 提供了一种对插件进行打包和分发的跨平台方式。 基于这种方式，你会在所有的目标平台（Linux、Windows、macOS 等）使用同一 种打包形式，包括为用户提供更新。 Krew 也维护一个 [插件索引（plugin index）](https://krew.sigs.k8s.io/plugins/) 以便其他人能够发现你的插件并安装之。

## [kubectl 备忘单](https://kubernetes.io/zh/docs/reference/kubectl/cheatsheet/) <a id="kubectl-cheatsheet"></a>

### [kubectl 常用命令整理](https://docs.ethanshen.cn/kubernetes/kubectl_common.html) <a id="kubectl-useful-cmds"></a>

> 来源：[沈旭](https://github.com/a-ethan) @ [伊桑老师的产品社](https://www.ethanshen.cn/) &gt; [伊桑老师的文档](https://docs.ethanshen.cn/)

Kubernetes 运维工程师日常常用的 kubectl 工具，以及一些特殊用法示例。

## kubectl 生态圈小工具

### [kubecm: 管理你的 kubeconfig](https://mp.weixin.qq.com/s?__biz=MzI4MzcwMTA5Nw==&mid=2247483762&idx=1&sn=d03cacaa90db9cc12dc3a7c01928790c) <a id="kubecm"></a>

> 来源：[郭旭东](https://github.com/sunny0826) @ 云原生之路 &gt; [云原生工具箱](https://mp.weixin.qq.com/mp/appmsgalbum?__biz=MzI4MzcwMTA5Nw==&action=getalbum&album_id=1416096301506314242)

该项目脱胎于 [mergeKubeConfig](https://github.com/sunny0826/mergeKubeConfig) 项目，最早写该项目的目的是在一堆杂乱无章的 `kubeconfig` 中自由的切换。随着需要操作的 Kubernetes 集群越来越多，在不同的集群之间切换也越来越麻烦，而操作 Kubernetes 集群的本质不过是通过 `kubeconfig` 访问 Kubernetes 集群的 API Server，以操作 Kubernetes 的各种资源，而 `kubeconfig` 不过是一个 YAML 文件，用来保存访问集群的密钥，最早的 mergeKubeConfig 不过是一个操作 YAML 文件的 Python 脚本。而随着 Go 学习的深入，也就动了重写这个项目的念头，就这样 [kubecm](https://github.com/sunny0826/kubecm) 诞生了。

![kubecm - Manage your kubeconfig more easily](../.gitbook/assets/image%20%2811%29.png)

### [kubectl 周边的一些实用命令行小工具](https://www.yuque.com/serviceup/k8s-hands-on/cli-tools) <a id="krew-plugins"></a>

> 来源：海立 @ [ServiceUP](https://www.yuque.com/serviceup) &gt; [快速上手 Kubernetes ](https://www.yuque.com/serviceup/k8s-hands-on)

本文收集了一些 kubectl 的替代品（例如 [tubectl](https://github.com/reconquest/tubekit)），以及一些比较实用的 kubectl 官方插件（Krew 体系插件），可以用于简化 kubectl 纷繁复杂的操作，提升命令行环境下运维的效率。

### [K8s 资源可视化利器：kubectl-graph](https://mp.weixin.qq.com/s/cEjr0W7mkiANenm95IddSA) <a id="kubectl-graph"></a>

> 来源：[郭旭东](https://github.com/sunny0826) @ 云原生之路 &gt; [云原生工具箱](https://mp.weixin.qq.com/mp/appmsgalbum?__biz=MzI4MzcwMTA5Nw==&action=getalbum&album_id=1416096301506314242)

最近接手了一个规模比较大的集群，光是整理集群中的资源就使人头昏眼花，虽然我自认 `kubectl` 使用的已经十分熟练，但是上千个 Kubernetes Resource 看下来还是不堪重负。在不能为集群安装任何其他工具的情况下，可以改造的就只有我自己的 Client 端，也就是 `kubectl` 了。本文就介绍一个有趣的 kubectl 插件：[`kubectl-graph`](https://github.com/steveteuber/kubectl-graph)。

### [使用 kubectl-rabbitmq 部署和运维 K8s 上的 RabbitMQ 集群](https://mp.weixin.qq.com/s/YLYpYrolCZttrdMx0n3qiQ) <a id="kubectl-rabbitmq"></a>

> 来源：[郭旭东](https://github.com/sunny0826) @ 云原生之路 &gt; [云原生工具箱](https://mp.weixin.qq.com/mp/appmsgalbum?__biz=MzI4MzcwMTA5Nw==&action=getalbum&album_id=1416096301506314242)

最近接到一个在 K8s 中部署一个 RabbitMQ 集群的任务，既然是部署在 K8s 集群中，首选的当然是 RabbitMQ Operator 了。不过在浏览官方文档时，意外的官方也有开发一个 kubectl-rabbitmq 的插件来帮助部署和运维 RabbitMQ Operator，在试用后发现体验意外的不错。那么本文我们就使用 kubectl-rabbitmq 来部署一个 RabbitMQ 集群吧！

