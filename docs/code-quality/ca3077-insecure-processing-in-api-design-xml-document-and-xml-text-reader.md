---
title: CA3077：API 设计、XML 文档和 XML 文本读取器中的不安全处理
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-code-analysis
ms.topic: reference
ms.assetid: 7f33771b-f3c8-4c02-bef6-f581b623c303
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: ae63583edac9b3ff6fefef416c8c1ce19d6e88f6
ms.sourcegitcommit: 568bb0b944d16cfe1af624879fa3d3594d020187
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/13/2018
ms.locfileid: "45549084"
---
# <a name="ca3077-insecure-processing-in-api-design-xml-document-and-xml-text-reader"></a>CA3077：API 设计、XML 文档和 XML 文本读取器中的不安全处理
|||
|-|-|
|TypeName|InsecureDTDProcessingInAPIDesign|
|CheckId|CA3077|
|类别|Microsoft.Security|
|是否重大更改|非重大更改|

## <a name="cause"></a>原因
 当设计派生自 XMLDocument 和 XMLTextReader 的 API 时，请注意 <xref:System.Xml.XmlReaderSettings.DtdProcessing%2A>。  当引用或解析外部实体源或设置 XML 中的不安全值时，使用不安全的 DTDProcessing 实例可能会导致信息泄露。

## <a name="rule-description"></a>规则说明
 一个*文档类型定义 (DTD)* 定义的是 XML 分析器可以确定文档有效性的两种方式之一[World Wide Web 联合会 (W3C) 可扩展标记语言 (XML) 1.0](http://www.w3.org/TR/2008/REC-xml-20081126/)。 此规则查找接受不受信任数据的某些属性和实例以提醒开发人员有关的潜在 [Information Disclosure](/dotnet/framework/wcf/feature-details/information-disclosure) 威胁，该威胁可能会导致 [拒绝服务 (DoS)](/dotnet/framework/wcf/feature-details/denial-of-service) 攻击。 在以下情况下触发此规则：

- <xref:System.Xml.XmlDocument> 或<xref:System.Xml.XmlTextReader>类使用默认冲突解决程序值进行 DTD 处理。

- 没有为 XmlDocument 或 XmlTextReader 派生类定义的构造函数或没有用于 <xref:System.Xml.XmlResolver>的安全值。

## <a name="how-to-fix-violations"></a>如何解决冲突

- 捕获和处理所有 XmlTextReader 异常正确以避免路径信息泄露。

- 使用<xref:System.Xml.XmlSecureResolver>而不是 XmlResolver 来限制 XmlTextReader 可以访问的资源。

## <a name="when-to-suppress-warnings"></a>何时禁止显示警告
 除非确信已知道输入是来自受信任的源，否则请勿禁止显示此警告的规则。

## <a name="pseudo-code-examples"></a>伪代码示例

### <a name="violation"></a>冲突

```csharp
using System;
using System.Xml;

namespace TestNamespace
{
    class TestClass : XmlDocument
    {
        public TestClass () {} // warn
    }

    class TestClass2 : XmlTextReader
    {
        public TestClass2() // warn
        {
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
    class TestClass : XmlDocument
    {
        public TestClass ()
        {
            XmlResolver = null;
        }
    }

    class TestClass2 : XmlTextReader
    {
        public TestClass2()
        {
               XmlResolver = null;
        }
    }
}
```