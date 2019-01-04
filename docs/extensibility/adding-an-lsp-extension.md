---
title: 添加语言服务器协议扩展 |Microsoft Docs
ms.date: 11/14/2017
ms.topic: conceptual
ms.assetid: 52f12785-1c51-4c2c-8228-c8e10316cd83
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: ad112d34c8f23a7738137f148f00a38a27335424
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/02/2019
ms.locfileid: "53966555"
---
# <a name="add-a-language-server-protocol-extension"></a>添加语言服务器协议扩展

语言服务器协议 (LSP) 是一种常见协议，格式为 JSON RPC v2.0，用于提供各种代码编辑器的服务功能的语言。 使用协议时，开发人员可以编写单语言版服务器提供服务功能，如 IntelliSense、 错误诊断的语言中，查找所有引用、 对各种支持 LSP 的代码编辑器等。 传统上，可以通过以下任一方法添加在 Visual Studio 中的语言服务使用 TextMate 语法文件用于提供基本功能，如语法突出显示，或通过编写使用 Visual Studio 扩展性 Api 的完整集的自定义语言服务为提供更丰富的数据。 现在，对 LSP 提供了一个第三个选项的支持。

![在 Visual Studio 中的语言服务器协议服务](media/lsp-service-in-VS.png)

## <a name="language-server-protocol"></a>语言服务器协议

![语言服务器协议实现](media/lsp-implementation.png)

本文介绍如何创建 Visual Studio 扩展中使用的 LSP 基于语言服务器。 它假定您已经开发了 LSP 基于语言服务器，并只是想要将其集成到 Visual Studio。

有关支持 Visual Studio 中，语言服务器可以与客户端通信 (Visual Studio) 通过任何基于流的传输机制，例如：

* 标准输入/输出流
* 命名的管道
* 套接字 (仅 TCP)

LSP 和 Visual Studio 中的为其支持的目的是不是 Visual Studio 产品的一部分的载入语言服务。 它不是以扩展 Visual Studio 中的现有语言服务 （如 C# 中)。 若要扩展现有的语言，请参阅语言服务扩展性指南 (例如， ["Roslyn".NET 编译器平台](../extensibility/dotnet-compiler-platform-roslyn-extensibility.md))。

该协议本身的详细信息，请参阅文档[此处](https://github.com/Microsoft/language-server-protocol)。

详细了解如何创建示例语言服务器或如何将现有的语言服务器集成到 Visual Studio Code，请参阅文档[此处](https://code.visualstudio.com/docs/extensions/example-language-server)。

## <a name="language-server-protocol-features-supported"></a>支持的语言服务器协议功能

LSP 支持以下功能在 Visual Studio 中到目前为止：

消息 | 在 Visual Studio 中提供支持
--- | ---
初始化 | 是
已初始化 | 是
关机 | 是
退出 | 是
$/ cancelRequest | 是
窗口/showMessage | 是
window/showMessageRequest | 是
窗口/日志消息 | 是
遥测数据/事件 |
客户端/registerCapability |
客户端/unregisterCapability |
workspace/didChangeConfiguration | 是
workspace/didChangeWatchedFiles | 是
工作区/符号 | 是
workspace/executeCommand | 是
工作区/applyEdit | 是
textDocument/publishDiagnostics | 是
textDocument/didOpen | 是
textDocument/didChange | 是
textDocument/willSave |
textDocument/willSaveWaitUntil |
textDocument/didSave | 是
textDocument/didClose | 是
textDocument/完成 | 是
完成/解决 | 是
textDocument/hover | 是
textDocument/signatureHelp | 是
textDocument/references | 是
textDocument/documentHighlight | 是
textDocument/documentSymbol | 是
textDocument/格式设置 | 是
textDocument/rangeFormatting | 是
textDocument/onTypeFormatting |
textDocument/definition | 是
textDocument/codeAction | 是
textDocument/codeLens |
codeLens/resolve |
textDocument/documentLink |
documentLink/resolve |
textDocument/rename | 是

## <a name="getting-started"></a>入门

> [!NOTE]
> 开始使用 Visual Studio 15.8 预览版 3，对通用语言服务器协议的支持已内置到 Visual Studio。  如果已生成了我们的预览的 LSP 扩展[语言服务器客户端 VSIX](https://marketplace.visualstudio.com/items?itemName=vsext.LanguageServerClientPreview)版本，它们将停止工作后向已升级到 15.8 预览版 3 或更高版本。  你将需要执行以下操作以获取你恢复正常工作的 LSP 扩展：
>
> 1. 卸载 Microsoft Visual Studio 语言服务器协议预览版 VSIX。  从 15.8 预览版 4 开始，你执行升级在 Visual Studio 中，每次我们将自动检测并删除其预览 VSIX 为您在升级过程。
>
> 2. 更新到最新的非预览版本，Nuget 引用[LSP 包](https://www.nuget.org/packages/Microsoft.VisualStudio.LanguageServer.Client)。
>
> 3. 在 VSIX 清单中删除到 Microsoft Visual Studio 语言服务器协议预览 VSIX 的依赖关系。
>
> 4. 请确保在 VSIX 指定 Visual Studio 15.8 预览版 3 作为安装目标的下限。
>
> 5. 重新生成并重新部署。

### <a name="create-a-vsix-project"></a>创建一个 VSIX 项目

若要创建使用 LSP 基于语言服务器的语言服务扩展，首先请确保你有**Visual Studio 扩展开发**VS 实例已安装工作负载。

接下来通过导航到创建新的空白 VSIXProject**文件** > **新建项目** > **Visual C#**  >  **可扩展性** > **VSIX 项目**:

![创建 vsix 项目](media/lsp-vsix-project.png)

### <a name="language-server-and-runtime-installation"></a>语言服务器和运行时安装

默认情况下，对语言服务器本身或执行它们所需的运行时，将不包含为 LSP 基于语言服务器支持在 Visual Studio 中创建的扩展。 扩展开发人员负责分发语言服务器和所需的运行时。 有几种方法来执行此操作：

* 作为内容文件，可以在 VSIX 中嵌入语言服务器。
* 创建 MSI 来安装语言服务器和/或需要运行时。
* 提供有关 Marketplace 告知用户如何获取运行时和语言的服务器的说明。

### <a name="textmate-grammar-files"></a>TextMate 语法文件

LSP 不包括如何提供对语言的文本着色的规范。 若要提供自定义颜色设置为在 Visual Studio 中的语言，扩展开发人员可以使用 TextMate 语法文件。 若要添加自定义 TextMate 语法或主题文件，请执行以下步骤：

1. 创建一个名为"语法"内您的扩展插件 （也可以是你选择的任何名称）。

2. 内部*语法*文件夹，包括任何 *\*.tmlanguage*，  *\*.plist*，  *\*.tmtheme*，或 *\*.json*您希望提供自定义着色的文件。

3. 右键单击文件并选择**属性**。 更改**构建**操作**内容**并**包含在 VSIX**属性设为 true。

4. 创建 *.pkgdef*文件，并添加与此类似的行：

   ```xml
   [$RootKey$\TextMate\Repositories]
   "MyLang"="$PackageFolder$\Grammars"
   ```

5. 右键单击文件并选择**属性**。 更改**构建**操作**内容**并**包含在 VSIX**属性设为 true。

完成前面的步骤之后,*语法*文件夹添加到包的安装目录作为存储库源名为 MyLang' （'MyLang 是只是消除二义性的名称，可以是任何唯一的字符串）。 所有的语法 (*.tmlanguage*文件) 和主题文件 (*.tmtheme*文件) 在此目录将作为潜在选取和它们会取代 TextMate 随提供的内置语法。 如果声明的语法文件的扩展名匹配所打开的文件的扩展名，将步骤 TextMate。

## <a name="create-a-simple-language-client"></a>创建一个简单的语言，客户端

### <a name="main-interface---ilanguageclientdotnetapimicrosoftvisualstudiolanguageserverclientilanguageclientviewvisualstudiosdk-2017"></a>主接口- [ILanguageClient](/dotnet/api/microsoft.visualstudio.languageserver.client.ilanguageclient?view=visualstudiosdk-2017)

创建 VSIX 项目后，将以下 NuGet 包添加到你的项目：

* [Microsoft.VisualStudio.LanguageServer.Client](https://www.nuget.org/packages/Microsoft.VisualStudio.LanguageServer.Client)

> [!NOTE]
> 时，完成前面的步骤后，可采用 NuGet 包的依赖项的 Newtonsoft.Json 和 StreamJsonRpc 包添加到你的项目。 **除非您确信，将 Visual Studio 的版本上安装这些新的版本不更新这些包的扩展定目标**。 程序集将不会包括在 VSIX 中-在相反，它们将提取从 Visual Studio 安装目录。 如果你正在引用的程序集的版本比你的扩展的用户的计算机上安装的内容更新*不起作用*。

你可以然后创建一个新类实现[ILanguageClient](/dotnet/api/microsoft.visualstudio.languageserver.client.ilanguageclient?view=visualstudiosdk-2017)接口，所需的语言客户端连接到基于 LSP 语言服务器的主接口。

下面是一个示例：

```csharp
namespace MockLanguageExtension
{
    [ContentType("bar")]
    [Export(typeof(ILanguageClient))]
    public class BarLanguageClient : ILanguageClient
    {
        public string Name => "Bar Language Extension";

        public IEnumerable<string> ConfigurationSections => null;

        public object InitializationOptions => null;

        public IEnumerable<string> FilesToWatch => null;

        public event AsyncEventHandler<EventArgs> StartAsync;
        public event AsyncEventHandler<EventArgs> StopAsync;

        public async Task<Connection> ActivateAsync(CancellationToken token)
        {
            await Task.Yield();

            ProcessStartInfo info = new ProcessStartInfo();
            info.FileName = Path.Combine(Path.GetDirectoryName(Assembly.GetExecutingAssembly().Location), "Server", @"MockLanguageServer.exe");
            info.Arguments = "bar";
            info.RedirectStandardInput = true;
            info.RedirectStandardOutput = true;
            info.UseShellExecute = false;
            info.CreateNoWindow = true;

            Process process = new Process();
            process.StartInfo = info;

            if (process.Start())
            {
                return new Connection(process.StandardOutput.BaseStream, process.StandardInput.BaseStream);
            }

            return null;
        }

        public async Task OnLoadedAsync()
        {
            await StartAsync.InvokeAsync(this, EventArgs.Empty);
        }

        public Task OnServerInitializeFailedAsync(Exception e)
        {
            return Task.CompletedTask;
        }

        public Task OnServerInitializedAsync()
        {
            return Task.CompletedTask;
        }
    }
}
```

需要实现的主要方法是[OnLoadedAsync](/dotnet/api/microsoft.visualstudio.languageserver.client.ilanguageclient.onloadedasync?view=visualstudiosdk-2017)并[ActivateAsync](/dotnet/api/microsoft.visualstudio.languageserver.client.ilanguageclient.activateasync?view=visualstudiosdk-2017)。 [OnLoadedAsync](/dotnet/api/microsoft.visualstudio.languageserver.client.ilanguageclient.onloadedasync?view=visualstudiosdk-2017)当 Visual Studio 已加载您的扩展插件和语言服务器已准备好启动时调用。 在这种方法，可以调用[StartAsync](/dotnet/api/microsoft.visualstudio.languageserver.client.ilanguageclient.startasync?view=visualstudiosdk-2017)立即要指示应启动语言服务器，或可以执行额外的逻辑并调用委托[StartAsync](/dotnet/api/microsoft.visualstudio.languageserver.client.ilanguageclient.startasync?view=visualstudiosdk-2017)更高版本。 **若要激活你的语言服务器，必须在某一时刻调用 StartAsync。**

[ActivateAsync](/dotnet/api/microsoft.visualstudio.languageserver.client.ilanguageclient.activateasync?view=visualstudiosdk-2017)是通过调用最终调用的方法[StartAsync](/dotnet/api/microsoft.visualstudio.languageserver.client.ilanguageclient.startasync?view=visualstudiosdk-2017)委托; 它包含用于启动语言服务器，并与它建立连接的逻辑。 必须返回一个连接对象，包含用于向服务器写入和从服务器读取的流。 此处引发的任何异常被捕获和通过 Visual Studio 中的信息栏消息向用户显示。

### <a name="activation"></a>激活

一旦实现语言客户端类，您将需要定义为其定义如何将 Visual Studio 中加载和激活的两个属性：

```csharp
  [Export(typeof(ILanguageClient))]
  [ContentType("bar")]
```

### <a name="mef"></a>MEF

Visual Studio 将使用[MEF](https://github.com/Microsoft/vs-mef/blob/master/doc/index.md) (Managed Extensibility Framework) 来管理其可扩展性点。 [导出](/dotnet/api/system.componentmodel.composition.exportattribute)属性指示到 Visual Studio 中，此类应作为一个扩展点拾取并在适当时加载。

若要使用 MEF，你必须定义 MEF 为 VSIX 清单中的资产。

打开您的 VSIX 清单设计器并导航到**资产**选项卡：

![添加 MEF 资产](media/lsp-add-asset.png)

单击新建以创建新的资产：

![定义 MEF 资产](media/lsp-define-asset.png)

* **类型**:Microsoft.VisualStudio.MefComponent
* **源**:当前解决方案中的项目
* **项目**: [项目]

### <a name="content-type-definition"></a>内容类型定义

当前加载 LSP 基于语言服务器扩展插件的唯一方法是通过文件内容类型。 也就是说，定义语言客户端类时 (它实现[ILanguageClient](/dotnet/api/microsoft.visualstudio.languageserver.client.ilanguageclient?view=visualstudiosdk-2017))，将需要定义类型的文件，当打开时，将导致你的扩展加载。 如果打开的不匹配定义的内容类型的文件，将不加载你的扩展。

这是通过定义一个或多个 ContentTypeDefinition 类：

```csharp
namespace MockLanguageExtension
{
    public class BarContentDefinition
    {
        [Export]
        [Name("bar")]
        [BaseDefinition(CodeRemoteContentDefinition.CodeRemoteContentTypeName)]
        internal static ContentTypeDefinition BarContentTypeDefinition;


        [Export]
        [FileExtension(".bar")]
        [ContentType("bar")]
        internal static FileExtensionToContentTypeDefinition BarFileExtensionDefinition;
    }
}
```

在上述示例中，为以结尾的文件创建的内容类型定义 *.bar*文件扩展名。 内容类型定义给定名称"bar"和**必须**派生自[CodeRemoteContentTypeName](/dotnet/api/microsoft.visualstudio.languageserver.client.coderemotecontentdefinition.coderemotecontenttypename?view=visualstudiosdk-2017)。

后添加的内容类型定义，就可以定义何时加载语言客户端扩展语言客户端类中：

```csharp
    [ContentType("bar")]
    [Export(typeof(ILanguageClient))]
    public class BarLanguageClient : ILanguageClient
    {
    }
```

添加的 LSP 语言服务器的支持不需要您在 Visual Studio 中实现您自己的项目系统。 客户可以在 Visual Studio，若要开始使用你的语言服务中打开单个文件或文件夹。 实际上，对 LSP 语言服务器设计用于仅在打开的文件夹/文件方案中的支持。 如果实现自定义项目系统时，某些功能 （例如设置） 将不起作用。

## <a name="advanced-features"></a>高级功能

### <a name="settings"></a>设置

支持自定义特定于语言的服务器的设置不可用，但仍在改进过程中。 设置是特定于语言服务器支持和通常控制语言服务器如何发出数据。 例如，语言服务器可能会报告错误的最大数目设置。 扩展创建者定义的特定项目的用户可以更改默认值。

请按照这些步骤将对设置的支持添加到你的 LSP 语言服务扩展：

1. 添加 JSON 文件 (例如， *MockLanguageExtensionSettings.json*) 中的项目中包含的设置和它们的默认值。 例如：

   ```json
   {
    "foo.maxNumberOfProblems": -1
   }
   ```
2. 右键单击 JSON 文件并选择**属性**。 更改**生成**操作保存到"内容"和"包含在 VSIX 中的属性设为 true。

3. 实现 ConfigurationSections 并返回 JSON 文件中定义的设置的前缀的列表 （在 Visual Studio Code 中，这将映射到在 package.json 中的配置节名称）：

   ```csharp
   public IEnumerable<string> ConfigurationSections
   {
      get
      {
          yield return "foo";
      }
   }
   ```

4. 将.pkgdef 文件添加到项目 （添加新的文本文件并将文件扩展名更改为.pkgdef）。 Pkgdef 文件应包含此信息：

   ```xml
    [$RootKey$\OpenFolder\Settings\VSWorkspaceSettings\[settings-name]]
    @="$PackageFolder$\[settings-file-name].json"
   ```

    示例:
    ```xml
    [$RootKey$\OpenFolder\Settings\VSWorkspaceSettings\MockLanguageExtension]
    @="$PackageFolder$\MockLanguageExtensionSettings.json"
    ```

5. 右键单击.pkgdef 文件，然后选择**属性**。 更改**构建**操作**内容**并**包含在 VSIX**属性设为 true。

6. 打开*source.extension.vsixmanifest*文件，并添加中的资产**资产**选项卡：

   ![编辑 vspackage 资产](media/lsp-add-vspackage-asset.png)

   * **类型**:Microsoft.VisualStudio.VsPackage
   * **源**:文件系统上的文件
   * **路径**: [路径你 *.pkgdef*文件]

### <a name="user-editing-of-settings-for-a-workspace"></a>用户编辑的工作区设置

1. 用户打开包含你的服务器拥有的文件的工作区。
2. 用户将添加的文件中 *.vs*名为的文件夹*VSWorkspaceSettings.json*。
3. 用户添加到一个行*VSWorkspaceSettings.json*文件服务器提供的设置。 例如：

   ```json
   {
    "foo.maxNumberOfProblems": 10
   }
   ```
   ### <a name="enabling-diagnostics-tracing"></a>启用诊断跟踪
   可以启用诊断跟踪输出之间的客户端和服务器，在调试问题时非常有用的所有消息。  若要启用诊断跟踪，请执行以下操作：

4. 打开或创建工作区设置文件*VSWorkspaceSettings.json* （请参阅"用户编辑的工作区设置"）。
5. 在设置 json 文件中添加以下行：

```json
{
    "foo.trace.server": "Off"
}
```

有三个可能值为跟踪详细级别：
* "关闭": 完全关闭跟踪
* "消息": 跟踪打开的跟踪，但唯一的方法名称和响应 ID。
* "详细": 跟踪打开状态;跟踪整个 rpc 消息。

当跟踪打开的内容写入到的文件中 *%temp%\VisualStudio\LSP*目录。  在日志遵循的命名格式 *[LanguageClientName]-[日期时间戳].log*。  目前，仅可以为打开文件夹方案启用跟踪。  打开单个文件以激活语言服务器没有诊断跟踪支持。

### <a name="custom-messages"></a>自定义消息

有到位的 Api，以便将消息传递到和从语言服务器不属于标准语言服务器协议的接收消息。 若要处理自定义消息，请实现[ILanguageClientCustomMessage](/dotnet/api/microsoft.visualstudio.languageserver.client.ilanguageclientcustommessage?view=visualstudiosdk-2017)语言客户端类中的接口。 [VS StreamJsonRpc](https://github.com/Microsoft/vs-streamjsonrpc/blob/master/doc/index.md)库用于传输语言客户端和服务器之间的自定义消息。 因为您 LSP 语言的客户端扩展就像任何其他 Visual Studio 扩展一样，您可以决定添加附加功能 （即不受 LSP） 到 （使用其他 Visual Studio Api） 的 Visual Studio 中通过自定义消息扩展。

#### <a name="receiving-custom-messages"></a>接收自定义消息

若要从服务器接收自定义消息，实现[CustomMessageTarget](/dotnet/api/microsoft.visualstudio.languageserver.client.ilanguageclientcustommessage.custommessagetarget?view=visualstudiosdk-2017)上的属性[ILanguageClientCustomMessage](/dotnet/api/microsoft.visualstudio.languageserver.client.ilanguageclientcustommessage?view=visualstudiosdk-2017)并返回一个对象，知道如何处理自定义消息. 下面的示例：

```csharp
internal class MockCustomLanguageClient : MockLanguageClient, ILanguageClientCustomMessage
{
    private JsonRpc customMessageRpc;

    public MockCustomLanguageClient() : base()
    {
        CustomMessageTarget = new CustomTarget();
    }

    public object CustomMessageTarget
    {
        get;
        set;
    }

    public class CustomTarget
    {
        public void OnCustomNotification(JToken arg)
        {
            // Provide logic on what happens OnCustomNotification is called from the language server
        }

        public string OnCustomRequest(string test)
        {
            // Provide logic on what happens OnCustomRequest is called from the language server
        }
    }
}
```

#### <a name="sending-custom-messages"></a>发送自定义消息

若要将自定义消息发送到服务器，实现[AttachForCustomMessageAsync](/dotnet/api/microsoft.visualstudio.languageserver.client.ilanguageclientcustommessage.attachforcustommessageasync?view=visualstudiosdk-2017)方法[ILanguageClientCustomMessage](/dotnet/api/microsoft.visualstudio.languageserver.client.ilanguageclientcustommessage?view=visualstudiosdk-2017)。 当你的语言服务器已启动并准备好接收消息时调用此方法。 一个[JsonRpc](https://github.com/Microsoft/vs-streamjsonrpc/blob/master/src/StreamJsonRpc/JsonRpc.cs)对象作为参数，您可以保留它以将消息发送到语言服务器使用传递[VS StreamJsonRpc](https://github.com/Microsoft/vs-streamjsonrpc/blob/master/doc/index.md) Api。 下面的示例：

```csharp
internal class MockCustomLanguageClient : MockLanguageClient, ILanguageClientCustomMessage
{
    private JsonRpc customMessageRpc;

    public MockCustomLanguageClient() : base()
    {
        CustomMessageTarget = new CustomTarget();
    }

    public async Task AttachForCustomMessageAsync(JsonRpc rpc)
    {
        await Task.Yield();

        this.customMessageRpc = rpc;
    }

    public async Task SendServerCustomNotification(object arg)
    {    
        await this.customMessageRpc.NotifyWithParameterObjectAsync("OnCustomNotification", arg);
    }

    public async Task<string> SendServerCustomMessage(string test)
    {
        return await this.customMessageRpc.InvokeAsync<string>("OnCustomRequest", test);
    }
}
```

### <a name="middle-layer"></a>中间层

有时扩展开发人员可能想要截获 LSP 消息发送到和接收到来自语言服务器。 例如，扩展开发人员可能想要更改特定的 LSP 消息发送的消息参数或修改从 LSP 的功能 （例如完成） 语言服务器返回的结果。 如果这是必需的扩展开发人员可以使用 MiddleLayer API 截获 LSP 消息。

每个 LSP 消息具有用于侦听它自己中间层接口。 若要截获特定消息，创建实现该消息的中间层接口的类。 然后，实现[ILanguageClientCustomMessage](/dotnet/api/microsoft.visualstudio.languageserver.client.ilanguageclientcustommessage?view=visualstudiosdk-2017)语言客户端类中接口，并返回实例中的应用对象[MiddleLayer](/dotnet/api/microsoft.visualstudio.languageserver.client.ilanguageclientcustommessage.middlelayer?view=visualstudiosdk-2017)属性。 下面的示例：

```csharp
public class MockLanguageClient: ILanguageClient, ILanguageClientCustomMessage
{
    public object MiddleLayer => MiddleLayerProvider.Instance;

    private class MiddleLayerProvider : ILanguageClientWorkspaceSymbolProvider
    {
        internal readonly static MiddleLayerProvider Instance = new MiddleLayerProvider();

        private MiddleLayerProvider()
        {
        }

        public async Task<SymbolInformation[]> RequestWorkspaceSymbols(WorkspaceSymbolParams param, Func<WorkspaceSymbolParams, Task<SymbolInformation[]>> sendRequest)
        {
            // Send along the request as given
            SymbolInformation[] symbols = await sendRequest(param);

            // Only return symbols that are "files"
            return symbols.Where(sym => string.Equals(new Uri(sym.Location.Uri).Scheme, "file", StringComparison.OrdinalIgnoreCase)).ToArray();
        }
    }
}
```

中间层功能是仍处于开发阶段，尚不全面。

## <a name="sample-lsp-language-server-extension"></a>示例 LSP 语言服务器扩展

若要查看示例扩展插件使用 Visual Studio 中的 LSP 客户端 API 的源代码，请参阅 VSSDK 扩展性示例[LSP 示例](https://github.com/Microsoft/VSSDK-Extensibility-Samples/tree/master/LanguageServerProtocol)。

## <a name="faq"></a>FAQ

**我想要构建自定义项目系统，以补充我 LSP 语言服务器，以提供更丰富的功能支持在 Visual Studio 中，要完成这么做？**

依赖于对基于 LSP 的语言在 Visual Studio 中的服务器的支持[打开文件夹功能](https://blogs.msdn.microsoft.com/visualstudio/2016/04/12/open-any-folder-with-visual-studio-15-preview/)和专门设计为不需要自定义项目系统。 您可以构建按照你自己自定义项目系统[此处](https://github.com/Microsoft/VSProjectSystem)，但某些功能，例如设置，可能无法正常工作。 LSP 语言服务器的默认值初始化逻辑是文件夹的传入当前正在打开的根文件夹位置，因此，如果使用自定义项目系统，可能需要在初始化以确保语言服务器可以提供自定义逻辑正常启动。

**如何添加调试器支持？**

我们将提供的支持[常见调试协议](https://code.visualstudio.com/docs/extensionAPI/api-debugging)未来版本中。

**如果已经与受支持的语言安装服务 (例如 JavaScript)，可以仍安装提供了附加功能 （如 linting) 的 LSP 语言服务器扩展？**

是的但并非所有功能将正常工作。 LSP 语言服务器扩展的最终目标是能够通过 Visual Studio 本身不支持的语言服务。 您可以创建扩展插件，提供更多支持使用 LSP 语言服务器，但某些功能 （如 IntelliSense) 不会顺畅的体验。 一般情况下，建议用于提供新语言体验，不扩展现有的 LSP 语言服务器扩展。

**其中将我已完成的 LSP 语言服务器 VSIX 的发布？**

请参阅 Marketplace 说明[此处](walkthrough-publishing-a-visual-studio-extension.md)。
