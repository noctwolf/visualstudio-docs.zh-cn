2. 按 F5（或在终端窗口中键入 `vsce up`）运行服务。 执行此操作会自动在新选择的空间 `scott` 中运行该服务。 
1. 可通过再次运行 `vsce list` 进行确认。 首先，可注意到 `mywebapi` 的实例现在正在 `scott` 空间中运行（`mainline` 中运行的版本仍在运行，但未列出）。 其次，`webfrontend` 的访问点 URL 以文本“scott-”为前缀。 对于 `scott` 空间，此 URL 是唯一的，表示发送到“scott URL”的请求尝试先路由到 `scott` 空间中的服务，然后返回到 `mainline` 空间中的服务。

```
Name         Space     Chart              Ports   Updated     Access Points
-----------  --------  -----------------  ------  ----------  -------------
mywebapi     scott     mywebapi-0.1.0     80/TCP  15s ago     http://localhost:61466
webfrontend  mainline  webfrontend-0.1.0  80/TCP  5h ago      https://scott-webfrontend-contosodev.vsce.io
```

![](../media/space-routing.png)

借助通连环境的此内置功能，可在共享环境中端到端地测试代码，而无需每个开发人员在其空间中重新创建完整的服务堆栈。 请注意，此路由需要在应用代码中转发传播标头，如本指南上一步所示。

## <a name="test-code-in-a-space"></a>在空间中测试代码
若要结合 `webfrontend` 测试 `mywebapi` 的新版本，请打开浏览器并访问 webfrontend 的公共访问点 URL，然后转到“关于”页。 应看到显示的新消息。

现在，删除 URL 的“scott-”部分，然后刷新浏览器。 应看到旧行为（由 `mainline` 中运行的 `mywebapi` 版本呈现）。