托管服务器的 web 部署 3.6 提供附加配置功能，可以从用户界面的发布设置文件的创建。

1. 如果必须在 Windows Server 上已安装的 Web 部署 3.6，请使用卸载它**控制面板** > **程序** > **卸载程序**.

1. 接下来，为托管服务器添加 Windows Server 上安装 Web 部署 3.6。

    若要安装托管服务器的 Web 部署，使用[Web 平台安装程序 (WebPI)](https://www.microsoft.com/web/downloads/platform.aspx)。 (若要查找从 IIS 的 Web 平台安装程序链接，选择**IIS**在左窗格中的服务器管理器中。 右键单击服务器并选择**Internet Information Services (IIS) Manager**。)

    在 Web 平台安装程序中，你找到**Web 部署为托管服务器**的应用程序选项卡中。

1. 如果你未不安装**IIS 管理脚本和工具**，立即安装。

    转到**选择服务器角色** > **Web 服务器 (IIS)** > **管理工具**，然后选择**IIS 管理脚本和工具**角色，单击**下一步**，然后安装角色。

    ![安装 IIS 管理脚本和工具](../../deployment/media/tutorial-iis-management-scripts-and-tools.png)

    脚本和工具启用所需的发布设置文件生成。

1. （可选）验证 Web 部署正在运行正确通过打开**控制面板 > 系统和安全 > 管理工具 > 服务**并确保**Web 部署代理服务**正在运行 (服务名称是在旧版本不同）。

    如果代理服务未运行，则启动它。 如果它根本不存在，请转到**控制面板 > 程序 > 卸载程序**，查找**Microsoft Web Deploy <version>** 。 选择**更改**安装，并确保你选择**将安装到本地硬盘**Web 部署组件。 完成更改安装步骤。