---
title: CA3147:使用 ValidateAntiForgeryToken 标记谓词处理程序
ms.date: 08/08/2018
ms.prod: visual-studio-dev15
ms.topic: reference
author: dotpaul
ms.author: paulming
manager: jillfra
dev_langs:
- CSharp
ms.workload:
- multiple
ms.openlocfilehash: 630d16b17f687842574348d86c1591a5433d9bfa
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/25/2019
ms.locfileid: "55037133"
---
# <a name="ca3147-mark-verb-handlers-with-validateantiforgerytoken"></a>CA3147:使用 ValidateAntiForgeryToken 标记谓词处理程序

|||
|-|-|
|TypeName|MarkVerbHandlersWithValidateAntiForgeryToken|
|CheckId|CA3147|
|类别|Microsoft.Security|
|是否重大更改|非重大更改|

## <a name="cause"></a>原因

ASP.NET MVC 控制器操作方法不标记有[ValidateAntiForgeryTokenAttribute](/previous-versions/aspnet/web-frameworks/dd492108(v=vs.118))，或属性指定的 HTTP 谓词，如[HttpGetAttribute](/previous-versions/aspnet/web-frameworks/ee470993(v%3dvs.118))或[AcceptVerbsAttribute](/previous-versions/aspnet/web-frameworks/dd470553%28v%3dvs.118%29)。

## <a name="rule-description"></a>规则说明

在设计时的 ASP.NET MVC 控制器，留意跨站点请求伪造攻击。 跨站点请求伪造攻击可以将恶意请求从身份验证的用户发送到 ASP.NET MVC 控制器。 有关详细信息，请参阅[在 ASP.NET MVC 和 web pages 中的 XSRF/CSRF 防护](/aspnet/mvc/overview/security/xsrfcsrf-prevention-in-aspnet-mvc-and-web-pages)。

此规则检查该 ASP.NET MVC 控制器操作方法是：

- 具有[ValidateAntiforgeryTokenAttribute](/previous-versions/aspnet/web-frameworks/dd492108%28v%3dvs.118%29)并指定允许的 HTTP 谓词，不包括 HTTP GET。

- 允许的谓词指定 HTTP GET。

## <a name="how-to-fix-violations"></a>如何解决冲突

- 处理 HTTP GET 请求，不具有可能有害的负面影响的 ASP.NET MVC 控制器操作，将添加[HttpGetAttribute](/previous-versions/aspnet/web-frameworks/ee470993%28v%3dvs.118%29)方法。

   如果具有 ASP.NET MVC 控制器操作处理 HTTP GET 请求，并具有潜在的有害副作用，如修改敏感数据，你的应用程序是易受到跨站点请求伪造攻击。  你将需要重新设计应用程序，以便只有 HTTP POST、 PUT 或 DELETE 请求执行敏感操作。

- 处理 HTTP POST 的 ASP.NET MVC 控制器操作，PUT 或 DELETE 请求时，添加[ValidateAntiForgeryTokenAttribute](/previous-versions/aspnet/web-frameworks/dd492108(v=vs.118))和指定允许的 HTTP 谓词的属性 ([AcceptVerbsAttribute](/previous-versions/aspnet/web-frameworks/dd470553%28v%3dvs.118%29)[HttpPostAttribute](/previous-versions/aspnet/web-frameworks/ee264023%28v%3dvs.118%29)， [HttpPutAttribute](/previous-versions/aspnet/web-frameworks/ee470909%28v%3dvs.118%29)，或[HttpDeleteAttribute](/previous-versions/aspnet/web-frameworks/ee470917%28v%3dvs.118%29))。 此外，您需要调用[HtmlHelper.AntiForgeryToken()](/previous-versions/aspnet/web-frameworks/dd504812%28v%3dvs.118%29)从你的 MVC 视图或 Razor web 页面的方法。 有关示例，请参阅[检查 edit 方法和编辑视图](/aspnet/mvc/overview/getting-started/introduction/examining-the-edit-methods-and-edit-view)。

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
