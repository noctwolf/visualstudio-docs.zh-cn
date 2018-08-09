---
title: CA3147： 将标记与 ValidateAntiForgeryToken 谓词处理程序
ms.date: 08/08/2018
ms.prod: visual-studio-dev15
ms.technology: vs-ide-code-analysis
ms.topic: reference
author: dotpaul
ms.author: paulming
manager: douge
dev_langs:
- CSharp
ms.workload:
- multiple
ms.openlocfilehash: 4b4369cfd310be9322d17b8bdbfe79880f2aa579
ms.sourcegitcommit: 96a6d1f16d06ca28d309d05b6e9fbd52f628cdbc
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/09/2018
ms.locfileid: "40008690"
---
# <a name="ca3147-mark-verb-handlers-with-validateantiforgerytoken"></a>CA3147： 将标记与 ValidateAntiForgeryToken 谓词处理程序

|||
|-|-|
|TypeName|MarkVerbHandlersWithValidateAntiForgeryToken|
|CheckId|CA3147|
|类别|Microsoft.Security|
|是否重大更改|非重大更改|

## <a name="cause"></a>原因

ASP.NET MVC 控制器操作方法不标记有<xref:Microsoft.AspNetCore.Mvc.ValidateAntiForgeryTokenAttribute?displayProperty=fullName>，或属性指定的 HTTP 谓词，例如<xref:Microsoft.AspNetCore.Mvc.HttpGetAttribute?displayProperty=fullName>或<xref:Microsoft.AspNetCore.Mvc.AcceptVerbsAttribute?displayProperty=fullName>。

## <a name="rule-description"></a>规则说明

在设计时的 ASP.NET MVC 控制器，留意跨站点请求伪造攻击。 跨站点请求伪造攻击可以将恶意请求从身份验证的用户发送到 ASP.NET MVC 控制器。 有关详细信息，请参阅[在 ASP.NET MVC 和 web pages 中的 XSRF/CSRF 防护](/aspnet/mvc/overview/security/xsrfcsrf-prevention-in-aspnet-mvc-and-web-pages)。

此规则检查该 ASP.NET MVC 控制器操作方法是：

- 具有<xref:Microsoft.AspNetCore.Mvc.ValidateAntiForgeryTokenAttribute>并指定允许的 HTTP 谓词，不包括 HTTP GET。

- 允许的谓词指定 HTTP GET。

## <a name="how-to-fix-violations"></a>如何解决冲突

- 处理 HTTP GET 请求，不具有可能有害的负面影响的 ASP.NET MVC 控制器操作，将添加<xref:Microsoft.AspNetCore.Mvc.HttpGetAttribute>方法。

   如果具有 ASP.NET MVC 控制器操作处理 HTTP GET 请求，并具有潜在的有害副作用，如修改敏感数据，你的应用程序是易受到跨站点请求伪造攻击。  你将需要重新设计应用程序，以便只有 HTTP POST、 PUT 或 DELETE 请求执行敏感操作。

- 处理 HTTP POST 的 ASP.NET MVC 控制器操作，PUT 或 DELETE 请求时，添加<xref:Microsoft.AspNetCore.Mvc.ValidateAntiForgeryTokenAttribute>和指定允许的 HTTP 谓词的属性 (<xref:Microsoft.AspNetCore.Mvc.AcceptVerbsAttribute>， <xref:Microsoft.AspNetCore.Mvc.HttpPostAttribute>， <xref:Microsoft.AspNetCore.Mvc.HttpPutAttribute>，或<xref:Microsoft.AspNetCore.Mvc.HttpDeleteAttribute>)。 此外，您需要调用<xref:Microsoft.AspNetCore.Mvc.ViewFeatures.HtmlHelper.AntiForgeryToken%2A?displayProperty=nameWithType>从你的 MVC 视图或 Razor web 页面。 有关示例，请参阅[检查 edit 方法和编辑视图](/aspnet/mvc/overview/getting-started/introduction/examining-the-edit-methods-and-edit-view)。

## <a name="when-to-suppress-warnings"></a>何时禁止显示警告

则可以安全地禁止显示此规则的警告，如果：

- ASP.NET MVC 控制器操作没有任何有害的副作用。

- 应用程序中以不同的方式进行验证防伪令牌。

## <a name="validateantiforgerytoken-attribute-example"></a>ValidateAntiForgeryToken 特性的示例

### <a name="violation"></a>冲突

```csharp
namespace TestNamespace
{
    using System.Web.Mvc;

    public class TestController : Controller
    {
        public ActionResult TransferMoney(string toAccount, string amount)
        {
            // You don't want an attacker to specify to who and how much money to transfer.

            return null;
        }
    }
}
```

### <a name="solution"></a>解决方案

```csharp
using System;
using System.Xml;

namespace TestNamespace
{
    using System.Web.Mvc;

    public class TestController : Controller
    {
        [HttpPost]
        [ValidateAntiForgeryToken]
        public ActionResult TransferMoney(string toAccount, string amount)
        {
            return null;
        }
    }
}
```

## <a name="httpget-attribute-example"></a>HttpGet 属性示例

### <a name="violation"></a>冲突

```csharp
namespace TestNamespace
{
    using System.Web.Mvc;

    public class TestController : Controller
    {
        public ActionResult Help(int topicId)
        {
            // This Help method is an example of a read-only operation with no harmful side effects.
            return null;
        }
    }
}
```

### <a name="solution"></a>解决方案

```csharp
namespace TestNamespace
{
    using System.Web.Mvc;

    public class TestController : Controller
    {
        [HttpGet]
        public ActionResult Help(int topicId)
        {
            return null;
        }
    }
}
```
