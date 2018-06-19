---
title: 在 Visual Studio 中为诊断数据适配器创建自定义数据编辑器
ms.date: 10/19/2016
ms.topic: conceptual
helpviewer_keywords:
- Diagnostic Data Adapter, creating custom editor
ms.assetid: 24970227-d1ea-4f6d-9839-e911478848ba
author: gewarren
ms.author: gewarren
manager: douge
ms.prod: visual-studio-dev15
ms.technology: vs-ide-test
ms.openlocfilehash: 6141defb2248cf79888b0ed94824a827bd36815f
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/26/2018
ms.locfileid: "31976303"
---
# <a name="how-to-create-a-custom-editor-for-data-for-your-diagnostic-data-adapter"></a>如何：为诊断数据适配器创建自定义数据编辑器

创建诊断数据适配器后，你可能希望在用户选择自定义诊断数据适配器用于测试设置时，最终用户能够配置特定数据。 例如，您可以选择配置数据，这些配置数据指定要提取的注册表项、要模拟的网络负载级别、存储临时文件或要附加的工作文件的目录。

您必须使用配置文件来设置您的诊断数据适配器的初始值。 可提供自定义编辑器以使用户能够修改配置数据。

若要创建您自己的编辑器，则需要创建实现 <xref:Microsoft.VisualStudio.TestTools.Execution.IDataCollectorConfigurationEditor> 的用户控件。

诊断数据适配器可使用 <xref:Microsoft.VisualStudio.TestTools.Execution.DataCollectorConfigurationEditorAttribute> 来指定要用于编辑诊断数据配置设置的编辑器类。

还可以指定要使用的默认配置数据。  有关示例默认配置，请参阅[用于创建诊断数据适配器的示例项目](../test/sample-project-for-creating-a-diagnostic-data-adapter.md)。

使用自定义诊断数据适配器时，执行以下过程可创建自定义编辑器来更新测试设置的数据。

> [!NOTE]
> 若要创建自定义编辑器，必须首先创建诊断数据适配器，其中对类应用了 <xref:Microsoft.VisualStudio.TestTools.Execution.DataCollectorConfigurationEditorAttribute>。 可以在该特性中使用可选 <xref:Microsoft.VisualStudio.TestTools.Execution.DataCollectorConfigurationEditorAttribute.HelpUri*> 属性，以指定编辑器的帮助内容源。 有关如何创建诊断数据适配器的详细信息，请参阅[如何：创建诊断数据适配器](../test/how-to-create-a-diagnostic-data-adapter.md)。

有关诊断数据适配器项目（包括自定义配置编辑器）的完整示例，请参阅[用于创建诊断数据适配器的示例项目](../test/sample-project-for-creating-a-diagnostic-data-adapter.md)。

## <a name="to-create-a-custom-editor-for-your-diagnostic-data-adapter"></a>为诊断数据适配器创建自定义编辑器

1.  在诊断数据适配器的项目中创建用户控件：

    1.  右键单击包含诊断数据适配器类的代码项目，指向“添加”，再指向“用户控件”。

    2.  在此示例中，向窗体中添加具有文本：“Data File Name:”的标签和名为“FileTextBox”的文本框，以使用户能输入必要的数据。

    > [!NOTE]
    > 目前仅支持 Windows 窗体用户控件。

2.  将这些行添加到声明部分：

    ```csharp
    using System.Xml;
    using Microsoft.VisualStudio.TestTools.Common;
    using Microsoft.VisualStudio.TestTools.Execution;
    ```

3.  使此用户控件成为自定义编辑器。

    1.  在代码项目中右键单击该用户控件，然后指向“查看代码”。

    2.  如下所示设置该类，以实现编辑器接口 <xref:Microsoft.VisualStudio.TestTools.Execution.IDataCollectorConfigurationEditor>：

    ```csharp
    public partial class MyDataConfigEditor :
         UserControl, IDataCollectorConfigurationEditor
    ```

    1.  右键单击代码中的 <xref:Microsoft.VisualStudio.TestTools.Execution.IDataCollectorConfigurationEditor>，再选择“实现接口”命令。 您必须为此接口实现的方法将添加到该类中。

    2.  将 <xref:Microsoft.VisualStudio.TestTools.Execution.DataCollectorConfigurationEditorAttribute> 添加到编辑器用户控件中以将它标识为诊断数据适配器编辑器，用诊断数据适配器的相应信息来替换“公司”、“产品”和“版本”：

        ```csharp
        [DataCollectorConfigurationEditorTypeUri(
            "configurationeditor://MyCompany/MyConfigEditor/1.0")]
        ```

4.  添加两个私有变量，如下所示：

    ```csharp
    private DataCollectorSettings collectorSettings;
    private IServiceProvider ServiceProvider { get; set; }
    ```

5.  添加代码以初始化诊断数据适配器的编辑器。 可使用设置变量中的数据向用户控件中的字段添加默认值。 此数据位于适配器的 XML 配置文件的 `<DefaultConfiguration>` 元素中。

    ```csharp
    public void Initialize(
        IServiceProvider svcProvider,
        DataCollectorSettings settings)
    {
        ServiceProvider = svcProvider;
        collectorSettings = settings;

        // Display the default file name as listed in the settings file.
        this.SuspendLayout();
        this.FileTextBox.Text = getText(collectorSettings.Configuration);
        this.ResumeLayout();
    }
    ```

6.  添加代码以将来自编辑器中控件的数据存回诊断数据适配器 API 所需的 XML 格式，如下所示：

    ```csharp
    public DataCollectorSettings SaveData()
    {
        collectorSettings.Configuration.InnerXml =
            String.Format(
    @"<MyCollectorName
        xmlns=""http://MyCompany/schemas/MyDiagnosticDataCollector/1.0"">
      <File FullPath=""{0}"" />
    </MyCollectorName>",
        FileTextBox.Text);
        return collectorSettings;
    }
    ```

7.  如果这对您很重要，请在 `VerifyData` 方法中添加代码以验证数据是否正确，也可以直接使该方法返回 `true`。

    ```csharp
    public bool VerifyData()
    {
        // Not currently verifying data
        return true;
    }
    ```

8.  （可选）可以在 `ResetToAgentDefaults()` 方法（该方法使用专用 `getText()` 方法）中添加代码，以将数据重置为 XML 配置文件中提供的初始设置。

    ```csharp
    // Reset to default value from XML configuration
    // using a custom getText() method
    public void ResetToAgentDefaults()
    {
        this.FileTextBox.Text = getText(collectorSettings.DefaultConfiguration);
    }

    // Local method to read the configuration settings
    private string getText(XmlElement element)
    {
        // Setup namespace manager with our namespace
        XmlNamespaceManager nsmgr =
            new XmlNamespaceManager(
                element.OwnerDocument.NameTable);

        // Find all the "File" elements under our configuration
        XmlNodeList files = element.SelectNodes("//ns:MyCollectorName/ns:File", nsmgr);

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
    ```

9. 生成解决方案。 将数据诊断适配器程序集和 XML 配置文件 (`<diagnostic data adapter name>.dll.config`) 复制到基于安装目录的以下位置：%ProgramFiles(x86)%\Microsoft Visual Studio\2017\Enterprise\Common7\IDE\PrivateAssemblies\DataCollectors。

    > [!NOTE]
    > 虽然配置编辑器与诊断数据适配器可位于不同的项目和程序集中，但它们也可位于同一程序集中。

10. 若要使用正在测试的诊断数据适配器，必须从现有测试设置列表中进行选择，或者从 Microsoft 测试管理器或 Visual Studio 创建一个新的诊断数据适配器，然后选择它。

     该适配器将显示在测试设置的“数据和诊断”选项卡上，并具有你指派给该类的友好名称。

11. 若要为测试设置配置诊断数据适配器，请选择适配器名称旁的“配置”。

     此时将显示您的自定义编辑器。

12. 根据需要编辑自定义编辑器中的字段，然后选择“保存”。

13. 如果是从 Microsoft 测试管理器运行测试，则可以在运行测试前将这些测试设置分配给测试计划，也可以使用“使用选项运行”命令分配测试设置并重写测试设置。 有关测试设置的详细信息，请参阅[使用测试设置收集诊断信息](../test/collect-diagnostic-information-using-test-settings.md)。

14. 在将您的新配置编辑器与诊断数据适配器一起使用之前，必须先将 <xref:Microsoft.VisualStudio.TestTools.Execution.DataCollectorConfigurationEditorAttribute> 应用于要使用该编辑器的每个诊断数据适配器类，然后在客户端计算机上重新编译并重新安装它们。 有关如何安装诊断数据适配器和配置编辑器的详细信息，请参阅[如何：安装自定义诊断数据适配器](../test/how-to-install-a-custom-diagnostic-data-adapter.md)。

15. 使用选择了你的诊断数据适配器的测试设置运行测试。

     你在编辑器中指定的数据文件将被附加到测试结果中。

 有关如何在运行测试时配置测试设置以使用环境的详细信息，请参阅[测试时收集诊断数据 (VSTS) ](/vsts/manual-test/collect-diagnostic-data)或[在手动测试中收集诊断数据 (VSTS)](/vsts/manual-test/mtm/collect-more-diagnostic-data-in-manual-tests)。

## <a name="see-also"></a>请参阅

- <xref:Microsoft.VisualStudio.TestTools.Execution.IDataCollectorConfigurationEditor>
- <xref:Microsoft.VisualStudio.TestTools.Execution.DataCollectorConfigurationEditorAttribute>
- <xref:Microsoft.VisualStudio.TestTools.Execution.DataCollectorConfigurationEditorAttribute>
- [创建诊断数据适配器以收集自定义数据或影响测试计算机](../test/create-a-diagnostic-data-adapter-to-collect-custom-data-or-affect-a-test-machine.md)
- [使用测试设置收集诊断信息](../test/collect-diagnostic-information-using-test-settings.md)
- [用于创建诊断数据适配器的示例项目](../test/sample-project-for-creating-a-diagnostic-data-adapter.md)