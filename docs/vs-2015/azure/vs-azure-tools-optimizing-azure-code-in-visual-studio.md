---
title: 优化 Visual Studio 中的 Azure 代码 |Microsoft Docs
description: 了解有关 Azure 的代码在 Visual Studio 中的优化工具可帮助提高代码的更多的可靠性和性能。
author: ghogen
manager: douge
ms.assetid: ed48ee06-e2d2-4322-af22-07200fb16987
ms.topic: conceptual
ms.custom: vs-azure
ms.workload: azure-vs
ms.date: 11/11/2016
ms.author: ghogen
ms.prod: visual-studio-dev14
ms.technology: vs-azure
ms.openlocfilehash: d1d0f5a69015a6c6596e1a2b7ee85b12f4116d6b
ms.sourcegitcommit: e481d0055c0724d20003509000fd5f72fe9d1340
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/05/2018
ms.locfileid: "51001462"
---
# <a name="optimizing-your-azure-code"></a>优化 Azure 代码
使用 Microsoft Azure 的应用程序进行编程时, 有某些编码做法，应遵循为了帮助避免应用程序可伸缩性、 行为和云环境中的性能问题。 Microsoft 提供了一个 Azure 代码分析工具来识别并标识了一些这些经常遇到的问题和可帮助你解决这些问题。 您可以下载 NuGet 通过 Visual Studio 中的工具。

## <a name="azure-code-analysis-rules"></a>Azure 代码分析规则
Azure 代码分析工具使用以下规则来找到已知的影响性能的问题时自动标记 Azure 代码。 检测到问题显示为警告或编译器错误。 通常通过灯泡图标提供代码修补程序或解决警告或错误的一些建议。

## <a name="avoid-using-default-in-process-session-state-mode"></a>避免使用默认 （进程内） 会话状态模式
### <a name="id"></a>Id
AP0000

### <a name="description"></a>描述
如果为云应用程序使用默认 （进程内） 会话状态模式下，可能会丢失会话状态。

请分享看法和意见[Azure 代码分析反馈](http://go.microsoft.com/fwlink/?LinkId=403771)。

### <a name="reason"></a>原因
默认情况下，web.config 文件中指定的会话状态模式为进程内。 此外，如果在配置文件中指定任何条目，会话状态模式默认为进程内。 进程内模式在 web 服务器上的内存中存储会话状态。 当实例重新启动或负载平衡或故障转移支持使用的新实例时，不会保存在 web 服务器上的内存中存储的会话状态。 这种情况下阻止不在云上可缩放应用程序。

ASP.NET 会话状态的会话状态数据支持多个不同的存储选项： InProc、 StateServer、 SQLServer、 Custom 和 Off。 建议使用托管的数据的自定义模式在外部会话状态存储，如[适用于 Redis 的 Azure 会话状态提供程序](http://go.microsoft.com/fwlink/?LinkId=401521)。

### <a name="solution"></a>解决方案
建议的解决方案之一是在托管的缓存服务存储会话状态。 了解如何使用[适用于 Redis 的 Azure 会话状态提供程序](http://go.microsoft.com/fwlink/?LinkId=401521)存储会话状态。 此外可以在其他位置，以确保你的应用程序是可扩展的云存储会话状态。 若要详细了解替代解决方案，请阅读[会话状态模式](https://msdn.microsoft.com/library/ms178586)。

## <a name="run-method-should-not-be-async"></a>不应异步运行的方法。
### <a name="id"></a>Id
AP1000

### <a name="description"></a>描述
创建异步方法 (如[await](https://msdn.microsoft.com/library/hh156528.aspx)) 之外[run （)](https://msdn.microsoft.com/library/azure/microsoft.windowsazure.serviceruntime.roleentrypoint.run.aspx)方法，然后调用的异步方法[run （)](https://msdn.microsoft.com/library/azure/microsoft.windowsazure.serviceruntime.roleentrypoint.run.aspx)。 声明[ [run （)](https://msdn.microsoft.com/library/azure/microsoft.windowsazure.serviceruntime.roleentrypoint.run.aspx) ](https://msdn.microsoft.com/library/azure/microsoft.windowsazure.serviceruntime.roleentrypoint.run.aspx)为异步方法将导致辅助角色进入重新启动循环。

请分享看法和意见[Azure 代码分析反馈](http://go.microsoft.com/fwlink/?LinkId=403771)。

### <a name="reason"></a>原因
内部调用异步方法[run （)](https://msdn.microsoft.com/library/azure/microsoft.windowsazure.serviceruntime.roleentrypoint.run.aspx)方法会导致云服务运行时回收辅助角色。 辅助角色启动时内, 发生的所有程序执行[run （)](https://msdn.microsoft.com/library/azure/microsoft.windowsazure.serviceruntime.roleentrypoint.run.aspx)方法。 退出[run （)](https://msdn.microsoft.com/library/azure/microsoft.windowsazure.serviceruntime.roleentrypoint.run.aspx)方法将导致辅助角色重新启动。 当辅助角色运行时调用异步方法时，它会异步方法之后调度所有操作，然后返回。 这将导致辅助角色要从其退出[ [ [ [run （)](https://msdn.microsoft.com/library/azure/microsoft.windowsazure.serviceruntime.roleentrypoint.run.aspx) ](https://msdn.microsoft.com/library/azure/microsoft.windowsazure.serviceruntime.roleentrypoint.run.aspx) ](https://msdn.microsoft.com/library/azure/microsoft.windowsazure.serviceruntime.roleentrypoint.run.aspx) ](https://msdn.microsoft.com/library/azure/microsoft.windowsazure.serviceruntime.roleentrypoint.run.aspx)方法并重新启动。 在下一轮执行时，辅助角色再次调用异步方法，并重新启动，导致辅助角色再次回收。

### <a name="solution"></a>解决方案
将所有异步操作之外[run （)](https://msdn.microsoft.com/library/azure/microsoft.windowsazure.serviceruntime.roleentrypoint.run.aspx)方法。 然后，调用重构的异步方法，从内部[ [run （)](https://msdn.microsoft.com/library/azure/microsoft.windowsazure.serviceruntime.roleentrypoint.run.aspx) ](https://msdn.microsoft.com/library/azure/microsoft.windowsazure.serviceruntime.roleentrypoint.run.aspx)方法，例如 RunAsync （）.wait 形式。 Azure 代码分析工具可以帮助解决此问题。

下面的代码段演示了此问题的代码修复：

```
public override void Run()
{
    RunAsync().Wait();
}

public async Task RunAsync()
{
    //Asynchronous operations code logic
    // This is a sample worker implementation. Replace with your logic.

    Trace.TraceInformation("WorkerRole1 entry point called");

    HttpClient client = new HttpClient();

    Task<string> urlString = client.GetStringAsync("http://msdn.microsoft.com");

    while (true)
    {
        Thread.Sleep(10000);
        Trace.TraceInformation("Working");

        string stream = await urlString;
    }

}
```

## <a name="use-service-bus-shared-access-signature-authentication"></a>使用服务总线共享访问签名身份验证
### <a name="id"></a>Id
AP2000

### <a name="description"></a>描述
使用共享访问签名 (SAS) 进行身份验证。 有关服务总线身份验证将弃用访问控制服务 (ACS)。

请分享看法和意见[Azure 代码分析反馈](http://go.microsoft.com/fwlink/?LinkId=403771)。

### <a name="reason"></a>原因
为了增强安全性，Azure Active Directory 是 ACS 身份验证替换 SAS 身份验证。 请参阅[Azure Active Directory 是 ACS 的未来](https://cloudblogs.microsoft.com/enterprisemobility/2013/06/22/azure-active-directory-is-the-future-of-acs/)有关过渡计划的信息。

### <a name="solution"></a>解决方案
在应用中使用 SAS 身份验证。 下面的示例演示如何使用现有的 SAS 令牌来访问服务总线命名空间或实体。

```
MessagingFactory listenMF = MessagingFactory.Create(endpoints, new StaticSASTokenProvider(subscriptionToken));
SubscriptionClient sc = listenMF.CreateSubscriptionClient(topicPath, subscriptionName);
BrokeredMessage receivedMessage = sc.Receive();
```

请参阅以下主题以了解更多信息。

* 有关概述，请参阅[共享访问签名身份验证与服务总线](https://msdn.microsoft.com/library/dn170477.aspx)
* [如何使用服务总线的共享访问签名身份验证](https://msdn.microsoft.com/library/dn205161.aspx)
* 有关示例项目，请参阅[服务总线订阅使用共享访问签名 (SAS) 身份验证](http://code.msdn.microsoft.com/windowsazure/Using-Shared-Access-e605b37c)

## <a name="consider-using-onmessage-method-to-avoid-receive-loop"></a>请考虑使用 OnMessage 方法来避免"receive 循环"
### <a name="id"></a>Id
AP2002

### <a name="description"></a>描述
为了避免陷入"receive 循环，"调用**OnMessage**方法是更好的解决方案，用于接收消息相对于调用**接收**方法。 但是，如果必须使用**接收**方法，并且你指定了非默认服务器等待时间，请确保服务器等待时间超过一分钟。

请分享看法和意见[Azure 代码分析反馈](http://go.microsoft.com/fwlink/?LinkId=403771)。

### <a name="reason"></a>原因
调用时**OnMessage**，客户端启动的内部消息泵不断轮询队列或订阅。 此消息泵包含发出消息接收调用一个无限循环。 如果在调用超时，则会颁发新的调用。 超时间隔由的值[OperationTimeout](https://msdn.microsoft.com/library/microsoft.servicebus.messaging.messagingfactorysettings.operationtimeout.aspx)的属性[MessagingFactory](https://msdn.microsoft.com/library/microsoft.servicebus.messaging.messagingfactory.aspx)正在使用。

使用的优点**OnMessage**相比**接收**是用户无需手动轮询消息、 处理异常、 多个并行处理消息，并完成消息。

如果您调用**接收**而无需使用其默认值，请确保*ServerWaitTime*值是多个 1 分钟。 设置*ServerWaitTime*为超过 1 分钟可防止服务器完全收到消息前超时。

### <a name="solution"></a>解决方案
请参阅下面的代码示例了解建议用法。 有关更多详细信息，请参阅[QueueClient.OnMessage 方法 (Microsoft.ServiceBus.Messaging)](https://msdn.microsoft.com/library/microsoft.servicebus.messaging.queueclient.onmessage.aspx)并[QueueClient.Receive 方法 (Microsoft.ServiceBus.Messaging)](https://msdn.microsoft.com/library/microsoft.servicebus.messaging.queueclient.receive.aspx)。

若要提高 Azure 消息传送基础结构的性能，请参阅设计模式[异步消息传送入门](https://msdn.microsoft.com/library/dn589781.aspx)。

下面是使用的示例**OnMessage**接收消息。

```
void ReceiveMessages()
{
    // Initialize message pump options.
    OnMessageOptions options = new OnMessageOptions();
    options.AutoComplete = true; // Indicates if the message-pump should call complete on messages after the callback has completed processing.
    options.MaxConcurrentCalls = 1; // Indicates the maximum number of concurrent calls to the callback the pump should initiate.
    options.ExceptionReceived += LogErrors; // Enables you to get notified of any errors encountered by the message pump.

    // Start receiving messages.
    QueueClient client = QueueClient.Create("myQueue");
    client.OnMessage((receivedMessage) => // Initiates the message pump and callback is invoked for each message that is recieved, calling close on the client will stop the pump.
    {
        // Process the message.
    }, options);
    Console.WriteLine("Press any key to exit.");
    Console.ReadKey();
```

下面是使用的示例**接收**和默认服务器等待时间。

```
string connectionString =  
CloudConfigurationManager.GetSetting("Microsoft.ServiceBus.ConnectionString");

QueueClient Client =  
    QueueClient.CreateFromConnectionString(connectionString, "TestQueue");

while (true)  
{   
   BrokeredMessage message = Client.Receive();
   if (message != null)
   {
      try  
      {
         Console.WriteLine("Body: " + message.GetBody<string>());
         Console.WriteLine("MessageID: " + message.MessageId);
         Console.WriteLine("Test Property: " +  
            message.Properties["TestProperty"]);

         // Remove message from queue
         message.Complete();
      }

      catch (Exception)
      {
         // Indicate a problem, unlock message in queue
         message.Abandon();
      }
   }
```

下面是使用的示例**接收**和非默认服务器等待时间。

```
while (true)  
{   
   BrokeredMessage message = Client.Receive(new TimeSpan(0,1,0));

   if (message != null)
   {
      try  
      {
         Console.WriteLine("Body: " + message.GetBody<string>());
         Console.WriteLine("MessageID: " + message.MessageId);
         Console.WriteLine("Test Property: " +  
            message.Properties["TestProperty"]);

         // Remove message from queue
         message.Complete();
      }

      catch (Exception)
      {
         // Indicate a problem, unlock message in queue
         message.Abandon();
      }
   }
}
```
## <a name="consider-using-asynchronous-service-bus-methods"></a>请考虑使用异步服务总线方法
### <a name="id"></a>Id
AP2003

### <a name="description"></a>描述
使用异步服务总线方法来改善中转消息传送的性能。

请分享看法和意见[Azure 代码分析反馈](http://go.microsoft.com/fwlink/?LinkId=403771)。

### <a name="reason"></a>原因
使用异步方法使应用程序程序并行性效果，因为执行每个调用不会阻止主线程。 使用服务总线消息传送方法、 执行操作时 （发送、 接收、 删除等） 需要时间。 这一次通过服务总线服务请求和答复的延迟时间除了包括处理操作。 若要增加每次操作的数目，操作必须同时执行。 有关详细信息请参阅[使用服务总线中转消息传送改善性能的最佳实践](https://msdn.microsoft.com/library/azure/hh528527.aspx)。

### <a name="solution"></a>解决方案
请参阅[QueueClient 类 (Microsoft.ServiceBus.Messaging)](https://msdn.microsoft.com/library/microsoft.servicebus.messaging.queueclient.aspx)有关如何使用建议的异步方法的信息。

若要提高 Azure 消息传送基础结构的性能，请参阅设计模式[异步消息传送入门](https://msdn.microsoft.com/library/dn589781.aspx)。

## <a name="consider-partitioning-service-bus-queues-and-topics"></a>请考虑分区服务总线队列和主题
### <a name="id"></a>Id
AP2004

### <a name="description"></a>描述
分区服务总线队列和主题使用服务总线消息传送更好的性能。

请分享看法和意见[Azure 代码分析反馈](http://go.microsoft.com/fwlink/?LinkId=403771)。

### <a name="reason"></a>原因
分区服务总线队列和主题提高性能吞吐量和服务可用性，因为分区的队列或主题的总吞吐量不再受到单个消息中转站或消息存储性能。 此外，消息传送存储的临时中断不会使分区的队列或主题不可用。 有关详细信息，请参阅[分区消息实体](https://msdn.microsoft.com/library/azure/dn520246.aspx)。

### <a name="solution"></a>解决方案
以下代码段演示如何进行分区消息传送实体。

```
// Create partitioned topic.
NamespaceManager ns = NamespaceManager.CreateFromConnectionString(myConnectionString);
TopicDescription td = new TopicDescription(TopicName);
td.EnablePartitioning = true;
ns.CreateTopic(td);
```

有关详细信息，请参阅[分区服务总线队列和主题 |Microsoft Azure 博客](https://azure.microsoft.com/blog/2013/10/29/partitioned-service-bus-queues-and-topics/)和签出[Microsoft Azure 服务总线分区队列](https://code.msdn.microsoft.com/windowsazure/Service-Bus-Partitioned-7dfd3f1f)示例。

## <a name="do-not-set-sharedaccessstarttime"></a>不要设置 SharedAccessStartTime
### <a name="id"></a>Id
AP3001

### <a name="description"></a>描述
您应避免使用为当前时间的 SharedAccessStartTimeset 以立即启动共享访问策略。 只需设置此属性，如果你想要在以后启动共享访问策略。

请分享看法和意见[Azure 代码分析反馈](http://go.microsoft.com/fwlink/?LinkId=403771)。

### <a name="reason"></a>原因
时钟同步会导致在数据中心之间的时间略有不同。 例如，从逻辑上将认为将存储 SAS 策略的开始时间设置为当前时间，使用 DateTime.Now 或类似方法将使 SAS 策略立即生效。 但是，由于有时数据中心可能会略迟于开始时间，而其他人之前其数据中心之间的轻微时间差可能会导致出现此问题。 因此，SAS 策略可能会过期很快 （或者甚至立即） 如果策略生存时间设置太短。

在 Azure 存储使用共享访问签名的更多指导，请参阅[介绍表 SAS （共享访问签名）、 队列 SAS 和 Blob SAS-Microsoft Azure 存储团队博客-更新站点主页-MSDN 博客](http://blogs.msdn.com/b/windowsazurestorage/archive/2012/06/12/introducing-table-sas-shared-access-signature-queue-sas-and-update-to-blob-sas.aspx)。

### <a name="solution"></a>解决方案
删除设置的共享的访问策略的开始时间的语句。 Azure 代码分析工具提供了针对此问题的修补程序。 有关安全管理的详细信息，请参阅设计模式[Valet 密钥模式](https://msdn.microsoft.com/library/dn568102.aspx)。

下面的代码段演示了此问题的代码修复。

```
// The shared access policy provides  
// read/write access to the container for 10 hours.
blobPermissions.SharedAccessPolicies.Add("mypolicy", new SharedAccessBlobPolicy()
{
   // To ensure SAS is valid immediately, don’t set start time.
   // This way, you can avoid failures caused by small clock differences.
   SharedAccessExpiryTime = DateTime.UtcNow.AddHours(10),
   Permissions = SharedAccessBlobPermissions.Write |
      SharedAccessBlobPermissions.Read
});
```

## <a name="shared-access-policy-expiry-time-must-be-more-than-five-minutes"></a>共享访问策略的到期时间必须超过五分钟
### <a name="id"></a>Id
AP3002

### <a name="description"></a>描述
可以为五分钟差异由于种情况称为"时钟偏差。"的不同位置的数据中心之间最 为了防止 SAS 策略令牌过期时间早于计划，设置为超过五分钟的到期时间。

请分享看法和意见[Azure 代码分析反馈](http://go.microsoft.com/fwlink/?LinkId=403771)。

### <a name="reason"></a>原因
位于世界各地的不同位置的数据中心以时钟信号来同步。 因为它需要要传送到不同位置的时钟信号的时间，可以有位于不同地理位置的数据中心之间的时间方差尽管据推测同步的所有内容。 这种时间差可能会影响共享访问策略开始时间和过期时间间隔。 因此，若要确保共享访问策略将立即生效，无指定的开始时间。 此外，请确保在到期时间超过 5 分钟，以防止提前超时。

有关在 Azure 存储使用共享访问签名的详细信息，请参阅[介绍表 SAS （共享访问签名）、 队列 SAS 和 Blob SAS-Microsoft Azure 存储团队博客-更新站点主页-MSDN 博客](http://blogs.msdn.com/b/windowsazurestorage/archive/2012/06/12/introducing-table-sas-shared-access-signature-queue-sas-and-update-to-blob-sas.aspx)。

### <a name="solution"></a>解决方案
有关安全管理的详细信息，请参阅设计模式[Valet 密钥模式](https://msdn.microsoft.com/library/dn568102.aspx)。

下面是未指定共享访问策略开始时间的示例。

```
// The shared access policy provides  
// read/write access to the container for 10 hours.
blobPermissions.SharedAccessPolicies.Add("mypolicy", new SharedAccessBlobPolicy()
{
   // To ensure SAS is valid immediately, don’t set start time.
   // This way, you can avoid failures caused by small clock differences.
   SharedAccessExpiryTime = DateTime.UtcNow.AddHours(10),
   Permissions = SharedAccessBlobPermissions.Write |
      SharedAccessBlobPermissions.Read
});
```

下面是与策略过期期限超过五分钟指定共享访问策略开始时间的示例。

```
// The shared access policy provides  
// read/write access to the container for 10 hours.
blobPermissions.SharedAccessPolicies.Add("mypolicy", new SharedAccessBlobPolicy()
{
   // To ensure SAS is valid immediately, don’t set start time.
   // This way, you can avoid failures caused by small clock differences.
  SharedAccessStartTime = new DateTime(2014,1,20),   
 SharedAccessExpiryTime = new DateTime(2014, 1, 21),
   Permissions = SharedAccessBlobPermissions.Write |
      SharedAccessBlobPermissions.Read
});
```

有关详细信息，请参阅[创建和使用共享访问签名](https://msdn.microsoft.com/library/azure/jj721951.aspx)。

## <a name="use-cloudconfigurationmanager"></a>使用 CloudConfigurationManager
### <a name="id"></a>Id
AP4000

### <a name="description"></a>描述
使用[ConfigurationManager](https://msdn.microsoft.com/library/system.configuration.configurationmanager\(v=vs.110\).aspx)类的项目，如 Azure 网站和 Azure 移动服务不会造成运行时问题。 最佳做法，但是，它是一个好办法使用云[ConfigurationManager](https://msdn.microsoft.com/library/system.configuration.configurationmanager\(v=vs.110\).aspx)作为统一管理所有 Azure 云应用程序的配置方式。

请分享看法和意见[Azure 代码分析反馈](http://go.microsoft.com/fwlink/?LinkId=403771)。

### <a name="reason"></a>原因
CloudConfigurationManager 读取适合应用程序环境的配置文件。

[CloudConfigurationManager](https://msdn.microsoft.com/library/azure/microsoft.windowsazure.cloudconfigurationmanager.aspx)

### <a name="solution"></a>解决方案
若要使用对代码进行重构[CloudConfigurationManager 类](https://msdn.microsoft.com/library/azure/microsoft.windowsazure.cloudconfigurationmanager.aspx)。 代码修复此问题提供的 Azure 代码分析工具。

下面的代码段演示了此问题的代码修复。 替换

`var settings = ConfigurationManager.AppSettings["mySettings"];`

替换为

`var settings = CloudConfigurationManager.GetSetting("mySettings");`

下面是如何在 App.config 或 Web.config 文件中存储的配置设置的示例。 将设置添加到配置文件的 appSettings 节。 下面是前面的代码示例的 Web.config 文件。

```
<appSettings>
    <add key="webpages:Version" value="3.0.0.0" />
    <add key="webpages:Enabled" value="false" />
    <add key="ClientValidationEnabled" value="true" />
    <add key="UnobtrusiveJavaScriptEnabled" value="true" />
    <add key="mySettings" value="[put_your_setting_here]"/>
  </appSettings>  
```

## <a name="avoid-using-hard-coded-connection-strings"></a>避免使用硬编码的连接字符串
### <a name="id"></a>Id
AP4001

### <a name="description"></a>描述
如果使用硬编码的连接字符串，并且需要更高版本更新它们，您必须对源代码进行更改并重新编译应用程序。 但是，如果在配置文件中存储连接字符串，您可以更改这些更高版本只需更新配置文件。

请分享看法和意见[Azure 代码分析反馈](http://go.microsoft.com/fwlink/?LinkId=403771)。

### <a name="reason"></a>原因
进行硬编码连接字符串是个糟糕的做法，因为它引入了问题，当需要快速更改连接字符串。 此外，如果项目需要签入到源代码管理，硬编码的连接字符串引发安全漏洞，因为可以在源代码中查看字符串。

### <a name="solution"></a>解决方案
在配置文件或 Azure 环境中存储连接字符串。

* 对于独立应用程序使用 app.config 来存储连接字符串设置。
* 对于 IIS 承载的 web 应用程序，使用 web.config 来存储连接字符串。
* 对于 ASP.NET vNext 应用程序，使用 configuration.json 来存储连接字符串。

有关使用 web.config 或 app.config 等配置文件的信息，请参阅[ASP.NET Web 配置准则](https://msdn.microsoft.com/library/vstudio/ff400235\(v=vs.100\).aspx)。 有关 Azure 环境变量工作的信息，请参阅[Azure 网站： 应用程序字符串和连接字符串工作](https://azure.microsoft.com/blog/2013/07/17/windows-azure-web-sites-how-application-strings-and-connection-strings-work/)。 在源代码管理中存储连接字符串的信息，请参阅[避免将敏感信息，如连接字符串放置在源代码存储库中存储的文件内](http://www.asp.net/aspnet/overview/developing-apps-with-windows-azure/building-real-world-cloud-apps-with-windows-azure/source-control)。

## <a name="use-diagnostics-configuration-file"></a>使用诊断配置文件
### <a name="id"></a>Id
AP5000

### <a name="description"></a>描述
而不是使用 Microsoft.WindowsAzure.Diagnostics 编程 API，如在代码中配置诊断设置，应在 diagnostics.wadcfg 文件中配置诊断设置。 （或者，如果使用 Azure SDK 2.5 的 diagnostics.wadcfgx）。 通过执行此操作，可以更改诊断设置，而无需重新编译代码。

请分享看法和意见[Azure 代码分析反馈](http://go.microsoft.com/fwlink/?LinkId=403771)。

### <a name="reason"></a>原因
Azure SDK 2.5 （它使用 Azure 诊断 1.3）、 Azure 诊断 (WAD) 无法通过使用多种不同的方法进行配置之前： 将它添加到的配置 blob 在存储中，使用命令性代码、 声明性配置或默认值配置。 但是，若要配置诊断的首选的方法是使用 XML 配置文件 （diagnostics.wadcfg 或 diagnositcs.wadcfgx SDK 2.5 及更高版本） 应用程序项目中。 在此方法中，diagnostics.wadcfg 文件完全定义的配置和可以更新并重新部署。 混合使用 diagnostics.wadcfg 配置文件的设置配置所使用的编程方法与[DiagnosticMonitor](https://msdn.microsoft.com/library/microsoft.windowsazure.diagnostics.diagnosticmonitor.aspx)或[RoleInstanceDiagnosticManager](https://msdn.microsoft.com/library/microsoft.windowsazure.diagnostics.management.roleinstancediagnosticmanager.aspx)类可以会造成混淆。 请参阅[初始化或更改 Azure 诊断配置](https://msdn.microsoft.com/library/azure/hh411537.aspx)有关详细信息。

从 WAD 1.3 （包含 Azure SDK 2.5） 开始，不再可以使用代码来配置诊断。 因此，可以只需提供应用或更新诊断扩展时的配置。

### <a name="solution"></a>解决方案
使用诊断配置设计器将诊断设置移到诊断配置文件 （diagnositcs.wadcfg 或 diagnositcs.wadcfgx SDK 2.5 及更高版本）。 此外建议你安装[Azure SDK 2.5](http://go.microsoft.com/fwlink/?LinkId=513188)并使用最新的诊断功能。

1. 在你想要配置的角色的快捷菜单，选择属性并选择配置选项卡。
2. 在中**诊断**部分中，请确保**启用诊断**复选框处于选中状态。
3. 选择**配置**按钮。

   ![访问启用诊断选项](./media/vs-azure-tools-optimizing-azure-code-in-visual-studio/IC796660.png)

   请参阅[针对 Azure 云服务和虚拟机配置诊断](vs-azure-tools-diagnostics-for-cloud-services-and-virtual-machines.md)有关详细信息。

## <a name="avoid-declaring-dbcontext-objects-as-static"></a>避免 DbContext 对象声明为静态
### <a name="id"></a>Id
AP6000

### <a name="description"></a>描述
若要节省内存，请避免 DBContext 对象声明为静态。

请分享看法和意见[Azure 代码分析反馈](http://go.microsoft.com/fwlink/?LinkId=403771)。

### <a name="reason"></a>原因
DBContext 对象保存每个调用的查询结果。 不会释放静态 DBContext 对象，直到应用程序域卸载为止。 因此，静态 DBContext 对象可能占用大量的内存。

### <a name="solution"></a>解决方案
将 DBContext 声明为局部变量或非静态实例字段，将它用于任务，并让它在使用后释放。

以下示例 MVC 控制器类演示如何使用 DBContext 对象。

```
public class BlogsController : Controller
    {
        //BloggingContext is a subclass to DbContext        
        private BloggingContext db = new BloggingContext();
        // GET: Blogs
        public ActionResult Index()
        {
            //business logics…
            return View();
        }
        protected override void Dispose(bool disposing)
        {
            if (disposing)
            {
                db.Dispose();
            }
            base.Dispose(disposing);
        }
    }
```

## <a name="next-steps"></a>后续步骤
若要了解有关优化和 Azure 应用进行故障排除的详细信息，请参阅[使用 Visual Studio 的 Azure 应用服务中 web 应用进行故障排除](/azure/app-service/web-sites-dotnet-troubleshoot-visual-studio)。
