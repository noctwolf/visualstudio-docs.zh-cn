---
title: 用于在 Visual Studio 中创建诊断数据适配器的示例项目
ms.date: 10/19/2016
ms.topic: sample
helpviewer_keywords:
- Diagnostic Data Adapter [Visual Studio ALM]
- samples. Diagnostic Data Adapter [Visual Studio ALM]
- Diagnostic Data Adapter, sample
ms.assetid: 548bdc5e-338f-4be7-a555-e6a2efb1df6b
author: gewarren
ms.author: gewarren
manager: douge
ms.prod: visual-studio-dev15
ms.technology: vs-ide-test
ms.openlocfilehash: 421f49ec9cfca99a62b80ddf71073a481b3a0c7e
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/23/2018
ms.locfileid: "49878201"
---
# <a name="sample-project-for-creating-a-diagnostic-data-adapter"></a>用于创建诊断数据适配器的示例项目

“MyDiagnosticDataAdapter”是一个简单的诊断数据适配器，该适配器可在你运行测试时，将日志文件附加到测试结果中。

 你需要在安装了诊断数据收集器或配置编辑器的任何计算机上拥有管理权限。

## <a name="example-data-adapter"></a>示例数据适配器

本示例演示如何执行以下任务：

-   应用属性以使 Microsoft 测试管理器能够发现作为诊断数据适配器的类。

-   应用属性以使 Microsoft 测试管理器能够发现一个用户控件类，该用户控件类作为一个编辑器，用于更改诊断数据适配器的配置。

-   访问默认配置数据。

-   注册特定诊断数据收集事件。

-   通过将日志文件发送到 <xref:Microsoft.VisualStudio.TestTools.Execution.DataCollectionSink> 来附加该文件。

```csharp
// My Data Collector Class
using Microsoft.VisualStudio.TestTools.Common;
using Microsoft.VisualStudio.TestTools.Execution;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Xml;
using System;

namespace MyCompany.MyDiagnosticDataAdapters
{
    // Provide a URI and friendly name for your diagnostic data adapter
    [DataCollectorTypeUri("datacollector://MyCompany/MyDataCollector/1.0")]
    [DataCollectorFriendlyName("Collect Log Files sample", false)]
    // Designate your chosen configuration editor
    [DataCollectorConfigurationEditor(
        "configurationeditor://MyCompany/MyDataConfigEditor/1.0")]
    public class MyDataCollector : DataCollector
    {
        private DataCollectionEvents dataEvents;
        private DataCollectionLogger dataLogger;
        private DataCollectionSink dataSink;
        private XmlElement configurationSettings;

        // Required method called by the testing framework
        public override void Initialize(
            XmlElement configurationElement,
            DataCollectionEvents events,
            DataCollectionSink sink,
            DataCollectionLogger logger,
            DataCollectionEnvironmentContext environmentContext)
        {
            dataEvents = events; // The test events
            dataLogger = logger; // The error and warning log
            dataSink = sink;     // Saves collected data
            // Configuration from the test settings
            configurationSettings = configurationElement;

            // Register common events for the data collector
            // Not all of the events are used in this class
            dataEvents.SessionStart +=
                new EventHandler<SessionStartEventArgs>(OnSessionStart);
            dataEvents.SessionEnd +=
                new EventHandler<SessionEndEventArgs>(OnSessionEnd);
            dataEvents.TestCaseStart +=
                new EventHandler<TestCaseStartEventArgs>(OnTestCaseStart);
            dataEvents.TestCaseEnd +=
                new EventHandler<TestCaseEndEventArgs>(OnTestCaseEnd);
            dataEvents.DataRequest +=
                new EventHandler<DataRequestEventArgs>(OnDataRequest);
        }

        protected override void Dispose(bool disposing)
        {
            if (disposing)
            {
                dataEvents.SessionStart -=
                    new EventHandler<SessionStartEventArgs>(OnSessionStart);
                dataEvents.SessionEnd -=
                    new EventHandler<SessionEndEventArgs>(OnSessionEnd);
                dataEvents.TestCaseStart -=
                    new EventHandler<TestCaseStartEventArgs>(OnTestCaseStart);
                dataEvents.TestCaseEnd -=
                    new EventHandler<TestCaseEndEventArgs>(OnTestCaseEnd);
                dataEvents.DataRequest -=
                    new EventHandler<DataRequestEventArgs>(OnDataRequest);
            }
        }

        #region Event Handlers
        public void OnSessionStart(object sender, SessionStartEventArgs e)
        {
            // TODO: Provide implementation
        }

        public void OnSessionEnd(object sender, SessionEndEventArgs e)
        {
            // TODO: Provide implementation
        }

        public void OnTestCaseStart(object sender, TestCaseEventArgs e)
        {
            // TODO: Provide implementation
        }

        public void OnTestCaseEnd(object sender, TestCaseEndEventArgs e)
        {
            // Get any files to be collected that are
            // configured in your test settings
            List<string> files = getFilesToCollect();

            // For each of the files, send the file to the data sink
            // which will attach it to the test results or to a bug
            foreach (string file in files)
            {
                dataSink.SendFileAsync(e.Context, file, false);
            }
        }

        public void OnDataRequest(object sender, DataRequestEventArgs e)
        {
            // TODO: Provide implementation
            // Most likely this occurs because a bug is being filed
        }
        #endregion

        // A private method to collect the configured file names
        private List<string> getFilesToCollect()
        {
            // Seetup namespace manager with our namespace
            XmlNamespaceManager nsmgr =
                new XmlNamespaceManager(
                    configurationSettings.OwnerDocument.NameTable);
            nsmgr.AddNamespace("ns",
                "http://MyCompany/schemas/MyDataCollector/1.0");

            // Find all of the "File" elements under our configuration
            XmlNodeList files =
                configurationSettings.SelectNodes(
                    "//ns:MyDataCollector/ns:File");

            // Build the list of files to collect from the
            // "FullPath" attributes of the "File" nodes.
            List<string> result = new List<string>();
            foreach (XmlNode fileNode in files)
            {
                XmlAttribute pathAttribute =
                    fileNode.Attributes["FullPath"];
                if (pathAttribute != null &&
                    !String.IsNullOrEmpty(pathAttribute.Value))
                {
                    result.Add(pathAttribute.Value);
                }
            }

            return result;
        }
    }
}
```

## <a name="example-configuration-editor"></a>示例配置编辑器

这是诊断数据适配器的示例配置编辑器。 在项目中添加一个用户控件，并创建一个十分简单的窗体，该窗体包含一个标签（“Name of Log File:”）和一个名为“FileTextBox”的文本框。

```csharp
using Microsoft.VisualStudio.TestTools.Common;
using Microsoft.VisualStudio.TestTools.Execution;
using System.Collections.Generic;
using System.ComponentModel;
using System.Drawing;
using System.Linq;
using System.Text;
using System.Windows.Forms;
using System.Xml;
using System;

namespace MyCompany.DiagnosticDataAdapters.ConfigurationEditors
{
    [DataCollectorConfigurationEditorTypeUri(
        "configurationeditor://MyCompany/MyConfigEditor/1.0")]
    public partial class MyDataConfigEditor :
        UserControl, IDataCollectorConfigurationEditor
    {
        private DataCollectorSettings collectorSettings;

        // Create a private property for the service provider
        private IServiceProvider ServiceProvider { get; set; }

        // Constructor
        public MyConfigurationEditor()
        {
            InitializeComponent();
        }

        // Required method called by the testing framework
        public void Initialize(
            IServiceProvider svcProvider,
            DataCollectorSettings settings)
        {
            ServiceProvider = svcProvider;
            collectorSettings = settings;

            // Display the file name as listed in the settings file.
            // If the configuration has not been updated before, this
            // data will be provided by the default configuration
            // section from <nameofcollector>.dll.config:
            // <DefaultConfiguration>
            //   <MyCollectorName
            //       xmlns="http://MyCompany/schemas/ProductName/Version");
            //     <File FullPath="C:\temp\logfile1.txt" />
            //   </MyCollectorName>
            // </DefaultConfiguration>
            this.SuspendLayout();
            this.FileTextBox.Text = GetText(collectorSettings.Configuration);
            this.ResumeLayout();
        }

        // Can be used to verify data before saving it
        public bool VerifyData()
        {
            // Not currently verifying data
            return true;
        }

        // Reset to default value from XML configuration
        // using a custom method
        public void ResetToAgentDefaults()
        {
            this.FileTextBox.Text =
                getText(collectorSettings.DefaultConfiguration);
        }

        // Saves data changed in the editor to the test configuration
        // settings. Does not change the default value.
        public DataCollectorSettings SaveData()
        {
            collectorSettings.Configuration.InnerXml =
                String.Format(
                    @"<MyCollectorName
      xmlns=""http://MyCompany/schemas/MyDataCollector/1.0"">
  <File FullPath=""{0}"" />
</MyCollectorName>",
                    FileTextBox.Text);
            return collectorSettings;
        }

        // Reads the configuration settings
        private string getText(XmlElement element)
        {
            // Setup namespace manager with our namespace
            XmlNamespaceManager nsmgr =
                new XmlNamespaceManager(
                    element.OwnerDocument.NameTable);

            // Find all the "File" elements under our configuration
            XmlNodeList files = element.SelectNodes("//ns:MyDataCollector/ns:File", nsmgr);

            string result = String.Empty;
            if (files.Count > 0)
            {
                XmlAttribute pathAttribute = files[0].Attributes["FullPath"];
                if (pathAttribute != null &&
                    !String.IsNullOrEmpty(pathAttribute.Value))
                {
                    result = pathAttribute.Value;
                }
            }

            return result;
        }
    }
}
```

## <a name="example-configuration-file"></a>示例配置文件

下面是诊断数据收集器配置编辑器的示例配置文件。

```xml
<?xml version="1.0" encoding="utf-8" ?>
<configuration>
  <configSections>
    <section
      name="DataCollectorConfiguration"
      type="Microsoft.VisualStudio.QualityTools.Execution.DataCollectorConfigurationSection,
        Microsoft.visualStudio.QualityTools.ExecutionCommon,
        Version=4.0.0.0, Culture=neutral,
        PublicKeyToken=b03f5f7f11d50a3a" />
  </configSections>
  <DataCollectorConfiguration
      xmlns="http://microsoft.com/schemas/VisualStudio/TeamTest/11">
    <DataCollector
        typeUri="datacollector://MyCompany/MyDataCollector/1.0">
      <DefaultConfiguration>
        <!-- Your default config settings-->
        <File FullPath="c:\temp\logfile1.txt" />
      </DefaultConfiguration>
    </DataCollector>
  </DataCollectorConfiguration>
</configuration>
```

## <a name="compile-the-code"></a>编译代码

### <a name="to-create-the-code-project-for-this-diagnostic-adapter"></a>创建此诊断适配器的代码项目

1.  创建一个名为“MyDataCollector”的新类库项目。

2.  在“解决方案资源管理器”中，右键单击项目，然后选择“属性”。 若要选择要添加的文件夹，请选择“引用路径”，然后选择省略号 (…)。

     此时将显示“选择引用路径”对话框。

3.  基于你的安装目录选择以下路径：%ProgramFiles(x86)%\Microsoft Visual Studio\2017\Enterprise\Common7\IDE\PrivateAssemblies。 选择 **“确定”**。

4.  若要向引用路径添加文件夹，请选择“添加文件夹”。

     该文件夹将显示在引用路径列表中。

5.  选择“全部保存”图标以保存引用路径。

6.  添加程序集“Microsoft.VisualStudio.QualityTools.ExecutionCommon”。

    1.  在“解决方案资源管理器”中，右键单击“引用”，然后选择“添加引用”。

    2.  选择“浏览”并找到“Microsoft.VisualStudio.QualityTools.ExecutionCommon.dll”。

         此程序集位于“%ProgramFiles(x86)%\Microsoft Visual Studio\2017\Enterprise\Common7\IDE\PrivateAssemblies”。

    3.  选择 **“确定”**。

7.  添加程序集“Microsoft.VisualStudio.QualityTools.Common”。

    1.  在解决方案资源管理器中，右键单击“引用”，并选择“添加引用”。

    2.  选择“浏览”并找到“Microsoft.VisualStudio.QualityTools.Common.dll”。

         此程序集位于“%ProgramFiles(x86)%\Microsoft Visual Studio\2017\Enterprise\Common7\IDE\PrivateAssemblies”。

    3.  选择 **“确定”**。

8.  将本文档前面列出的诊断数据适配器类复制到你的类库的类中。 保存此类。

9. 要将用户控件添加到项目中，右键单击解决方案资源管理器中的 MyDataCollector 项目，指向“添加”，然后选择“用户控件”。 选择“添加”。

10. 使用工具箱向该用户控件添加一个标签，并将 Text 属性改为“文件名:”。

11. 使用工具箱向该用户控件添加一个文本框，并将其名称改为“textBoxFileName”。

12. 在“解决方案资源管理器”中，右键单击用户控件，然后选择“查看代码”。 将此用户控件类替换为本文档前面列出的用户控件类。 保存此类。

    > [!NOTE]
    > 默认情况下，用户控件名为 UserControl1。 确保该用户控件类代码使用你的用户控件的名称。

13. 若要创建配置文件，请在“解决方案资源管理器”中右键单击解决方案，指向“添加”，然后选择“新建项”。 选择“应用程序配置文件”，然后选择“添加”。 这将向解决方案添加一个名为 App.config 的文件。

14. 将前面示例中的 XML 复制到该 XML 文件中。 保存该文件。

15. 生成解决方案，然后将生成的程序集和 App.config 文件复制到 %ProgramFiles(x86)%\Microsoft Visual Studio\2017\Enterprise\Common7\IDE\PrivateAssemblies\DataCollectors 目录中 。

16. 创建使用此自定义诊断数据适配器的测试设置。 将测试设置配置为收集存在的文件。

     如果是从 Microsoft 测试管理器运行测试，则可以在运行测试前将这些测试设置分配给测试计划，也可以使用“使用选项运行”命令分配测试设置并重写测试设置。 有关测试设置的详细信息，请参阅[使用测试设置收集诊断信息](../test/collect-diagnostic-information-using-test-settings.md)。

17. 使用选择了你的诊断数据适配器的测试设置运行测试。

     执行测试时，你指定的数据文件将被附加到测试结果中。

## <a name="see-also"></a>请参阅

- [如何：创建诊断数据适配器](../test/how-to-create-a-diagnostic-data-adapter.md)
- [如何：为诊断数据适配器创建自定义数据编辑器](../test/how-to-create-a-custom-editor-for-data-for-your-diagnostic-data-adapter.md)
- [如何：安装自定义诊断数据适配器](../test/how-to-install-a-custom-diagnostic-data-adapter.md)
- [创建诊断数据适配器以收集自定义数据或影响测试计算机](../test/create-a-diagnostic-data-adapter-to-collect-custom-data-or-affect-a-test-machine.md)