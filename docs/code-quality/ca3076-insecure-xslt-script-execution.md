---
title: "CA3076： 不安全的 XSLT 脚本执行 |Microsoft 文档"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 53cb7a46-c564-488f-bc51-0e210a7853c9
caps.latest.revision: "5"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: a304d5b405431bca78b3978e25b00d3cf7cc96c2
ms.sourcegitcommit: f0ddee934713ea9126fa107018a57a94a05eafd3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/12/2017
---
# <a name="ca3076-insecure-xslt-script-execution"></a>CA3076: 不安全的 XSLT 脚本执行
|||  
|-|-|  
|TypeName|InsecureXSLTScriptExecution|  
|CheckId|CA3076|  
|类别|Microsoft.Security|  
|是否重大更改|非重大更改|  
  
## <a name="cause"></a>原因  
 如果你执行[可扩展样式表语言转换 (XSLT)](https://support.microsoft.com/en-us/kb/313997)在.NET 应用程序以不安全的方式，处理器可能会解析不受信任会把泄露给攻击者，从而导致敏感信息的 URI 引用拒绝服务和跨站点攻击。  
  
## <a name="rule-description"></a>规则说明  
 **XSLT**是万维网联合会 (W3C) 标准，用于转换 XML 数据。 XSLT 通常用于编写样式表，以将 XML 数据转换为其他格式，如 HTML、固定长度的文本、以逗号分隔的文本或其他 XML 格式。 尽管默认情况下禁止，你仍可以选择为项目启用该功能。  
  
 为确保不暴露攻击面，每当 XslCompiledTransform.<xref:System.Xml.Xsl.XslCompiledTransform.Load%2A> 接收 <xref:System.Xml.Xsl.XsltSettings> 和 <xref:System.Xml.XmlResolver>的不安全组合实例时，则会触发此规则，这会允许处理恶意脚本。  
  
## <a name="how-to-fix-violations"></a>如何解决冲突  
  
-   将不安全的 XsltSettings 参数替换为 XsltSettings.<xref:System.Xml.Xsl.XsltSettings.Default%2A> 或者替换为已禁用文档函数和脚本执行的实例。  
  
-   将 <xref:System.Xml.XmlResolver> 参数替换为 null 或 <xref:System.Xml.XmlSecureResolver> 实例。  
  
## <a name="when-to-suppress-warnings"></a>何时禁止显示警告  
 除非确信已知道输入是来自受信任的源，否则请勿禁止显示此警告的规则。  
  
## <a name="pseudo-code-examples"></a>伪代码示例  
  
### <a name="violation"></a>冲突  
  
```csharp  
using System.Xml;  
using System.Xml.Xsl;  
  
namespace TestNamespace   
{   
    class TestClass   
    {  
         void TestMethod()   
        {    
             XslCompiledTransform xslCompiledTransform = new XslCompiledTransform();   
             var settings = XsltSettings.TrustedXslt;   
             var resolver = new XmlUrlResolver();   
             xslCompiledTransform.Load("testStylesheet", settings, resolver); // warn   
        }  
    }   
}   
```  
  
### <a name="solution"></a>解决方案  
  
```csharp  
using System.Xml;   
using System.Xml.Xsl;   
  
namespace TestNamespace   
{   
    class TestClass   
    {   
        void TestMethod()   
        {   
            XslCompiledTransform xslCompiledTransform = new XslCompiledTransform();   
            var settings = XsltSettings.Default;   
            var resolver = new XmlUrlResolver();   
            xslCompiledTransform.Load("testStylesheet", settings, resolver);   
        }   
    }   
}  
```  
  
### <a name="violation"></a>冲突  
  
```csharp  
using System.Xml;   
using System.Xml.Xsl;   
  
namespace TestNamespace   
{   
    class TestClass   
    {   
        private static void TestMethod(XsltSettings settings)   
        {   
            try   
            {   
                XslCompiledTransform xslCompiledTransform = new XslCompiledTransform();   
                var resolver = new XmlUrlResolver();   
                xslCompiledTransform.Load("testStylesheet", settings, resolver); // warn   
            }   
            catch { throw; }   
            finally { }   
        }   
    }   
}  
```  
  
### <a name="solution"></a>解决方案  
  
```csharp  
using System.Xml;   
using System.Xml.Xsl;   
  
namespace TestNamespace   
{   
    class TestClass   
    {   
        private static void TestMethod(XsltSettings settings)   
        {   
            try   
            {   
                XslCompiledTransform xslCompiledTransform = new XslCompiledTransform();   
                settings.EnableDocumentFunction = false;   
                settings.EnableScript = false;   
                var resolver = new XmlUrlResolver();   
                xslCompiledTransform.Load("testStylesheet", settings, resolver);   
            }   
            catch { throw; }   
            finally { }   
        }   
    }   
}  
```