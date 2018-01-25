# <a name="create-an-ai-project-from-existing-code"></a>通过现有代码创建 AI 项目

[安装 Visual Studio Tools for AI](installation.md) 后，就可以轻松地将现有 Python 代码引入 Visual Studio 项目。 

> [!Important]
>
> 此处所述的过程不移动或复制原始源文件。 如果要使用副本，请先复制文件夹。

1. 启动 Visual Studio，然后选择“文件”>“新建”>“项目”。

1. 在“新建项目”对话框中，搜索“AI 工具”，选择“从现有的 Python 代码”模板，为项目提供名称和位置，然后选择“确定”。

    ![根据现有代码新建项目，步骤 1](media\create-project-existing\new-ai-project.png)

1. 在出现的向导中，设置现有代码的路径和文件类型筛选器，并指定项目需要的任何搜索路径，然后选择“确定”。 如果不知道搜索路径是什么，则将该字段留空。


![根据现有代码新建项目，步骤 2](media\create-project-existing\azurebatch-newproject.png)

> 如果现有代码是 Azure 机器学习项目的一部分，则选中“是 Azure 机器学习文件夹”，确保成功转换重要的 Azure 机器学习配置详细信息，要使用的试验帐户、工作区、计算上下文等。

1. 要设置启动文件，请在“解决方案资源管理器”中找到该文件，右键单击，然后选择“设置为启动文件”。

8. 如果需要，可按 Ctrl+F5 或选择“调试”>“开始执行(不调试)”运行程序。 

> [!div class="nextstepaction"]
> [教程：在 Visual Studio 中使用 Python](../python/tutorial-working-with-python-in-visual-studio-step-00-installation.md)

## <a name="see-also"></a>请参阅

- [为现有 Python 解释器创建环境](https://docs.microsoft.com/visualstudio/python/python-environments#creating-an-environment-for-an-existing-interpreter)