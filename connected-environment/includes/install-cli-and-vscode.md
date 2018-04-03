## <a name="install-the-connected-environment-cli"></a>安装通连环境 CLI
通连环境需要最少的本地计算机设置。 大部分开发环境配置都存储在云中，并可与其他用户共享。

### <a name="install-on-mac"></a>在 Mac 上安装
下载并安装通连环境 CLI：
```cmd
curl -L https://aka.ms/get-vsce-mac | bash
```

### <a name="install-on-windows"></a>在 Windows 上安装
1. 安装[适用于 Windows 的 Git](https://git-scm.com/downloads)，选择默认安装选项。 
1. 从[此链接](https://storage.googleapis.com/kubernetes-release/release/v1.9.0/bin/windows/amd64/kubectl.exe)下载 kubectl.exe，并将其保存到你路径上的某个位置。
1. 下载并运行[通连环境 CLI 安装程序](https://aka.ms/get-vsce-windows)。 

### <a name="install-on-linux"></a>在 Linux 上安装
即将推出...

## <a name="get-kubernetes-debugging-for-vs-code"></a>获取适用于 VS Code 的 Kubernetes 调试
虽然可将通连环境 CLI 作为独立工具使用，但使用 VS Code 的 .NET Core 和 Node.js 开发者也可以使用 Kubernetes 调试等丰富功能。

1. 如果尚未安装，请安装 [VS Code](https://code.visualstudio.com/Download)。
1. 下载 [VS 通连环境扩展](https://aka.ms/get-vsce-code)。
1. 安装扩展： 

```cmd
code --install-extension path-to-downloaded-extension/vsce-0.1.0.vsix
```
