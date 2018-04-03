## <a name="initialize-code-for-docker-and-kubernetes-development"></a>初始化用于 Docker 和 Kubernetes 开发的代码
到目前为止，我们已经有了可以在本地运行的基本 Web 应用。 现在将通过创建定义应用容器的资产来容器化应用，并了解如何将其部署到 Kubernetes。 在通连环境中，可以轻松完成这一操作： 

1. 启动 VS Code 并打开 `webfrontend` 文件夹。 （在添加调试资产或还原项目时可以忽略任何默认提示。）
1. 在 VS Code 中打开集成终端（使用“视图”|“集成终端”菜单）。
1. 运行此命令（请确保当前文件夹为 webfrontend）：

```cmd
vsce init --public
```

通连环境 CLI 的 ```init``` 命令使用默认设置生成 Docker 和 Kubernetes 资产：
* `./Dockerfile` 描述了应用的容器映像，以及如何生成并在容器中运行源代码。
* `./charts/webfrontend` 下的 [Helm 图表](https://docs.helm.sh)描述了如何将容器部署到 Kubernetes。

目前没有必要了解这些文件的全部内容。 但不得不说的是，相同的 Kubernetes 和 Docker 配置即代码资产可用于从开发到生产的整个阶段，在不同环境中提供更出色的一致性。
 
`init` 命令还生成一个名为 `./vsce.yaml` 的文件，它是通连环境的配置文件。 它通过额外的配置在 Azure 中实现了迭代开发体验，补充了 Docker 和 Kubernetes 项目。 例如，默认 Helm 图表不公开任何公共终结点。 但有时在开发过程中临时打开一个公用终结点是有所帮助的，例如，可以从移动设备或 webhook URL 测试代码。 使用 `init --public` 创建的 vsce.yaml 文件将覆盖 Helm 默认参数，仅针对开发时间公开公共终结点。
