## <a name="initialize-debug-assets-with-the-vs-code-extension"></a>使用 VS Code 扩展初始化调试资产
首先需配置代码项目，以便 VS Code 与 Azure 中的开发环境通信。 通连环境的 VS Code 扩展提供了帮助程序命令来设置调试配置。 

打开“命令面板”（使用“查看”>“命令面板”菜单），并使用自动完成键入并选择命令 `Connected Environment: Create configuration files for connected development`。 

此操作将通连环境的调试配置添加到 `.vscode` 文件夹中。

![](../media/vsce-command-palette.png)

> [!Note]
> **重要提示**：由于存在 bug，请先关闭并重新打开 VS Code，然后再继续操作。