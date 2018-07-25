
1. 关闭并重新打开 IIS 管理控制台，在 UI 中显示更新的配置选项。

1. 在 IIS 中，右键单击**Default Web Site**，选择**部署** > **配置 Web 部署发布**。

    ![配置 Web 部署配置](../../deployment/media/tutorial-configure-web-deploy-publishing.png)

1. 在中**配置 Web 部署发布**对话框框中，检查设置。

1. 单击**安装程序**。

    在中**结果**面板中，为指定的用户，并授予访问权限，输出所示的文件 *.publishsettings*中显示在对话框中的位置生成的文件扩展名框。

    ```xml
    <?xml version="1.0" encoding="utf-8"?>
    <publishData>
      <publishProfile
        publishUrl="https://myhostname:8172/msdeploy.axd"
        msdeploySite="Default Web Site"
        destinationAppUrl="http://myhostname:80/"
        mySQLDBConnectionString=""
        SQLServerDBConnectionString=""
        profileName="Default Settings"
        publishMethod="MSDeploy"
        userName="myhostname\myusername" />
    </publishData>
    ```

    根据您的 Windows Server 和 IIS 配置，您可以看到 XML 文件中的不同值。 下面是一些详细信息，请参阅的值：

    * *Msdeploy.axd*文件中引用`publishUrl`属性是一个动态生成的 HTTP 处理程序文件，用于 Web 部署。 (用于测试目的，`http://myhostname:8172`通常也适用。)
    * `publishUrl`端口设置为端口 8172，这是 Web 部署的默认值。
    * `destinationAppUrl`端口设置为端口 80，后者是 IIS 的默认值。
    * 如果无法连接到远程主机上的 Visual Studio 中使用的主机名 （在后续步骤中），测试而不是主机名称的 IP 地址。

    > [!NOTE]
    > 如果要发布到 Azure VM 上运行的 IIS，则必须在网络安全组中打开 Web 部署和 IIS 端口。 有关详细信息，请参阅[安装和运行的 IIS](/azure/virtual-machines/windows/quick-create-portal#open-port-80-for-web-traffic)。

1. 将此文件复制到将运行 Visual Studio 的计算机。
