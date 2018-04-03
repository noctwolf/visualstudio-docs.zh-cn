## <a name="clean-up"></a>清理
要完全删除 Azure 中的通连环境（包括其中所有正在运行的服务），请使用 `vsce env rm` 命令。 请记住：此操作无法撤消。

以下示例列出了活动 Azure 订阅中的通连环境，然后删除了资源组“myenv-rg”中名为“myenv”的环境。

```cmd
vsce env list
vsce env rm --name myenv --resource-group myenv-rg
```

