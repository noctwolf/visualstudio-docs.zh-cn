---
title: "如何： 提供异步的 Visual Studio 服务 |Microsoft 文档"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 0448274c-d3d2-4e12-9d11-8aca78a1f3f5
caps.latest.revision: 
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload:
- vssdk
ms.openlocfilehash: ea22a30d6f31099ca5d69d9cd8178188577febfe
ms.sourcegitcommit: a80e7ef2f0a0f6d906a44f4d696aeb208bc1ad70
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/21/2018
---
# <a name="how-to-provide-an-asynchronous-visual-studio-service"></a>如何： 提供异步的 Visual Studio 服务
如果你想要获得服务，而不必阻止 UI 线程，你应该创建异步的服务，以及加载后台线程上的包。 为此你可以使用<xref:Microsoft.VisualStudio.Shell.AsyncPackage>而不是<xref:Microsoft.VisualStudio.Shell.Package>，使用异步包的特殊异步方法中添加服务。
  
 提供同步的 Visual Studio 服务有关的信息，请参阅[如何： 提供服务](../extensibility/how-to-provide-a-service.md)。  
  
## <a name="implementing-an-asynchronous-service"></a>实现异步服务  
  
1.  创建 VSIX 项目 (**文件 > 新建 > 项目 > Visual C# > Extensiblity > VSIX 项目**)。 将项目**TestAsync**。  
  
2.  将 VSPackage 添加到项目。 选择中的项目节点**解决方案资源管理器**单击**添加 > 新项 > Visual C# 项 > 扩展性 > Visual Studio 包**。 将此文件命名**TestAsyncPackage.cs**。  
  
3.  TestAsyncPackage.cs，在将更改要继承 AsyncPackage 而不是包的包：  
  
    ```csharp  
    public sealed class TestAsyncPackage : AsyncPackage  
    ```  
  
4.  若要实现的服务，你需要创建三种类型：  
  
    -   一个标识的服务的接口。 许多这些接口为空，即，它们有没有方法，因为它们仅用来查询服务。
  
    -   用于描述服务接口的接口。 此接口包括要实现的方法。  
  
    -   实现服务以及服务接口的类。  
  
5.  下面的示例演示三种类型的非常基本实现。 服务类的构造函数必须设置服务提供程序。 在此示例中我们将只是添加服务包代码文件。  
  
6.  将以下代码添加到包文件 using 语句：  
  
    ```csharp  
    using System.Threading;  
    using System.Threading.Tasks;  
    using System.Runtime.CompilerServices;  
    using System.IO;
    using IAsyncServiceProvider = Microsoft.VisualStudio.Shell.IAsyncServiceProvider;
    using Task = System.Threading.Tasks.Task;
    ```  
  
7.  以下是异步的服务实现。 请注意，你需要在构造函数中设置的异步服务提供程序，而不是同步服务提供程序：  
  
    ```csharp
    public class TextWriterService : STextWriterService, ITextWriterService  
    {  
        private IAsyncServiceProvider asyncServiceProvider;  
        
        public TextWriterService(IAsyncServiceProvider provider)  
        {
            // constructor should only be used for simple initialization
            // any usage of Visual Studio service, expensive background operations should happen in the
            // asynchronous InitializeAsync method for best performance
            asyncServiceProvider = provider;  
        }
        
        public async Task InitializeAsync(CancellationToken cancellationToken)
        {
            // We have to use JoinableTaskFactory as code will switch to main thread in some parts
            await ThreadHelper.JoinableTaskFactory.RunAsync(async () =>
            {
                await TaskScheduler.Default;
                // do background operations that involve IO or other async methods
                
                await ThreadHelper.JoinableTaskFactory.SwitchToMainThreadAsync(cancellationToken);               
                // query Visual Studio services on main thread unless they are documented as free threaded explicitly.
                // The reason for this is the final cast to service interface (such as IVsShell) may involve COM operations to add/release references.
                
                IVsShell vsShell = this.asyncServiceProvider.GetServiceAsync(typeof(SVsShell)) as IVsShell;
                // use Visual Studio services to continue initialization
            });
        }
        
        public async Task WriteLineAsync(string path, string line)  
        {  
            StreamWriter writer = new StreamWriter(path);  
            await writer.WriteLineAsync(line);  
            writer.Close();  
        }  
    }  

    public interface STextWriterService  
    {  
    }  
    
    public interface ITextWriterService   
    {  
        System.Threading.Tasks.Task WriteLineAsync(string path, string line);  
    }  
    ```  
  
## <a name="registering-a-service"></a>注册服务  
 若要注册服务，添加<xref:Microsoft.VisualStudio.Shell.ProvideServiceAttribute>到包，以提供服务。 不同于注册同步服务，你必须确保包和服务支持异步加载：
  
-   你必须添加**AllowsBackgroundLoading = true**字段<xref:Microsoft.VisualStudio.Shell.PackageRegistrationAttribute>若要确保包可以以异步方式初始化 PackageRegistrationAttribute 有关详细信息，请参阅[注册和撤消注册 Vspackage](../extensibility/registering-and-unregistering-vspackages.md)。  
  
-   你必须添加**IsAsyncQueryable = true**字段<xref:Microsoft.VisualStudio.Shell.ProvideServiceAttribute>以确保服务实例可以以异步方式初始化。

 下面是与异步服务注册 AsyncPackage 示例：
  
```csharp  
[ProvideService((typeof(STextWriterService)), IsAsyncQueryable = true)]  
[ProvideAutoLoad(UIContextGuids80.SolutionExists, PackageAutoLoadFlags.BackgroundLoad)]  
[PackageRegistration(UseManagedResourcesOnly = true, AllowsBackgroundLoading = true)]   
[Guid(TestAsyncPackage.PackageGuidString)]  
public sealed class TestAsyncPackage : AsyncPackage  
{. . . }  
```  
  
## <a name="adding-a-service"></a>添加服务  
  
1.  在 TestAsyncPackage.cs，删除`Initialize()`方法并重写`InitializeAsync()`方法。 添加服务，并添加一个用于创建服务的回调方法。 下面是添加服务的异步初始值设定项的示例：  
  
    ```csharp
    protected override async Task InitializeAsync(CancellationToken cancellationToken, IProgress<ServiceProgressData> progress)  
    {  
        await base.InitializeAsync(cancellationToken, progress);  
        this.AddService(typeof(STextWriterService), CreateTextWriterService);
    }  
  
    ```  
  
2.  添加对 Microsoft.VisualStudio.Shell.Interop.14.0.DesignTime.dll 的引用。  
  
3.  作为异步方法，创建并返回该服务实现的回调方法。  
  
    ```csharp  
    public async Task<object> CreateTextWriterService(IAsyncServiceContainer container, CancellationToken cancellationToken, Type serviceType)  
    {  
        TextWriterService service = new TextWriterService(this);  
        await service.InitializeAsync(cancellationToken);
        return service;
    }  
  
    ```  
  
## <a name="using-a-service"></a>使用服务  
 现在，您可以获取该服务，使用它的方法。  
  
1.  我们将介绍此初始值设定项，但您可以获取的服务任意位置你想要使用服务。  
  
    ```csharp  
    protected override async System.Threading.Tasks.Task InitializeAsync(CancellationToken cancellationToken, IProgress<ServiceProgressData> progress)  
    {  
        await base.InitializeAsync(cancellationToken, progress);  
        this.AddService(typeof(STextWriterService), CreateTextWriterService);  
  
        ITextWriterService textService = await this.GetServiceAsync(typeof(STextWriterService)) as ITextWriterService;  
  
        await textService.WriteLineAsync(<userpath>), "this is a test");  
  
    }  
  
    ```  
  
     不要忘记将更改 *\<userpath >*到文件名和您的计算机有意义的路径 ！  
  
2.  生成并运行代码。 出现 Visual Studio 的实验实例后，打开的解决方案。 这将导致自动上载到 AsyncPackage。 当运行具有初始值设定项时，你应在你指定的位置中找到的文件。  
  
## <a name="using-an-asynchronous-service-in-a-command-handler"></a>在命令处理程序中使用异步服务  
 下面是如何在菜单命令中使用异步服务的示例。 你可以使用此处显示要在其他非异步方法中使用该服务的过程。  
  
1.  将菜单命令添加到你的项目。 (在**解决方案资源管理器**，选择项目节点，右键单击，并选择**添加 / 新项 / 扩展性 / 自定义命令**。)作为命令文件名**TestAsyncCommand.cs。**  
  
2.  自定义命令模板重新添加`Initialize()`TestAsyncPackage.cs 文件才能初始化该命令的方法。 在 initialize （） 方法中，将复制初始化命令的行。 应如下所示：  
  
    ```csharp
    TestAsyncCommand.Initialize(this);  
    ```  
  
     移动到此行`InitializeAsync()`AsyncPackageForService.cs 文件中的方法。 由于这是在异步初始化中，你必须初始化命令使用之前来切换到主线程<xref:Microsoft.VisualStudio.Threading.JoinableTaskFactory.SwitchToMainThreadAsync%2A>。 它现在应如下所示：  
  
    ```csharp  
  
    protected override async System.Threading.Tasks.Task InitializeAsync(CancellationToken cancellationToken, IProgress<ServiceProgressData> progress)  
    {  
        await base.InitializeAsync(cancellationToken, progress);  
        this.AddService(typeof(STextWriterService), CreateTextWriterService);  

        ITextWriterService textService =   
           await this.GetServiceAsync(typeof(STextWriterService)) as ITextWriterService;  
  
        await textService.WriteLineAsync((<userpath>, "this is a test");  
  
        await ThreadHelper.JoinableTaskFactory.SwitchToMainThreadAsync();  
        TestAsyncCommand.Initialize(this);
    }  
  
    ```  
  
3.  删除`Initialize()`方法。  
  
4.  在 TestAsyncCommand.cs 文件中查找`MenuItemCallback()`方法。 删除方法的正文。  
  
5.  添加 using 语句：  
  
    ```csharp 
    using System.IO;  
    ```  
  
6.  添加名为的异步方法`UseTextWriterAsync()`，该获取的服务，并使用其方法：  
  
    ```csharp  
    private async System.Threading.Tasks.Task UseTextWriterAsync()  
    {  
        // Query text writer service asynchronously to avoid a blocking call.
        ITextWriterService textService =   
           await AsyncServiceProvider.GlobalProvider.GetServiceAsync(typeof(STextWriterService))  
              as ITextWriterService;  

        // don't forget to change <userpath> to a local path  
        await textService.WriteLineAsync((<userpath>),"this is a test");  
       }  
  
    ```  
  
7.  调用此方法从`MenuItemCallback()`方法：  
  
    ```csharp
    private void MenuItemCallback(object sender, EventArgs e)  
    {  
        UseTextWriterAsync();  
    }  
  
    ```  
  
8.  生成解决方案并启动调试。 出现 Visual Studio 的实验实例时，请转到**工具**菜单并查找**调用 TestAsyncCommand**菜单项。 时单击它，TextWriterService 将写入到你指定的文件。 （你不需要打开的解决方案，因为调用该命令也会导致要加载的包。）  
  
## <a name="see-also"></a>另请参阅  
 [使用并提供服务](../extensibility/using-and-providing-services.md)
