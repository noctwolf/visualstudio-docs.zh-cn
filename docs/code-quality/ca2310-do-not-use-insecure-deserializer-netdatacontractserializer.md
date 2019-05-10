---
title: CA2310:不要使用不安全反序列化程序 NetDataContractSerializer
ms.date: 05/01/2019
ms.topic: reference
author: dotpaul
ms.author: paulming
manager: jillfra
dev_langs:
- CSharp
- VB
ms.workload:
- multiple
f1_keywords:
- CA2310
- DoNotUseInsecureDeserializerNetDataContractSerializer
ms.openlocfilehash: e4af6bbfbd7e14b99f39ffa0adb5d1117c200d9a
ms.sourcegitcommit: db30651dc0ce4d0b274479b23a6bd102a5559098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/06/2019
ms.locfileid: "65135425"
---
# <a name="ca2310-do-not-use-insecure-deserializer-netdatacontractserializer"></a>CA2310:不要使用不安全反序列化程序 NetDataContractSerializer

|||
|-|-|
|TypeName|DoNotUseInsecureDeserializerNetDataContractSerializer|
|CheckId|CA2310|
|类别|Microsoft.Security|
|是否重大更改|非重大更改|

## <a name="cause"></a>原因

一个<xref:System.Runtime.Serialization.NetDataContractSerializer?displayProperty=nameWithType>反序列化方法是调用或引用。

## <a name="rule-description"></a>规则说明

[!INCLUDE[insecure-deserializers-description](includes/insecure-deserializers-description-md.md)]

此规则查找<xref:System.Runtime.Serialization.NetDataContractSerializer?displayProperty=nameWithType>反序列化方法调用或引用。 如果你想要反序列化时，才<xref:System.Runtime.Serialization.NetDataContractSerializer.Binder>属性设置为限制类型中，禁用此规则，并启用规则[CA2311](ca2311-do-not-deserialize-without-first-setting-netdatacontractserializer-binder.md)并[CA2312](ca2312-ensure-netdatacontractserializer-binder-is-set-before-deserializing.md)相反。

## <a name="how-to-fix-violations"></a>如何解决冲突

- 如果可能，而是使用安全的序列化程序和**不允许攻击者能够指定任意类型进行反序列化**。 一些更安全的序列化程序包括：
  - <xref:System.Runtime.Serialization.DataContractSerializer?displayProperty=nameWithType>
  - <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer?displayProperty=nameWithType>
  - <xref:System.Web.Script.Serialization.JavaScriptSerializer?displayProperty=nameWithType> -永远不会使用<xref:System.Web.Script.Serialization.SimpleTypeResolver?displayProperty=nameWithType>。 如果必须使用类型解析程序，到预期的列表限制反序列化的类型。
  - <xref:System.Xml.Serialization.XmlSerializer?displayProperty=nameWithType>
  - Newtonsoft Json.NET-使用 TypeNameHandling.None。 如果必须为 TypeNameHandling 使用另一个值，限制对具有自定义 ISerializationBinder 预期列表反序列化的类型。
  - 协议缓冲区
- 使序列化的数据篡改。 在序列化之后, 密码学角度上登录序列化的数据。 在反序列化之前验证的加密签名。 保护从公布的加密密钥和密钥轮换的设计。
- 限制反序列化的类型。 实现一个自定义<xref:System.Runtime.Serialization.SerializationBinder?displayProperty=nameWithType>。 反序列化之前<xref:System.Runtime.Serialization.NetDataContractSerializer>，将<xref:System.Runtime.Serialization.NetDataContractSerializer.Binder>属性设置为您的自定义的一个实例<xref:System.Runtime.Serialization.SerializationBinder>。 在重写<xref:System.Runtime.Serialization.SerializationBinder.BindToType%2A>方法，如果类型为意外，引发异常。
- 如果你限制反序列化的类型，可能想要禁用此规则，并启用规则[CA2311](ca2311-do-not-deserialize-without-first-setting-netdatacontractserializer-binder.md)并[CA2312](ca2312-ensure-netdatacontractserializer-binder-is-set-before-deserializing.md)。 规则[CA2311](ca2311-do-not-deserialize-without-first-setting-netdatacontractserializer-binder.md)并[CA2312](ca2312-ensure-netdatacontractserializer-binder-is-set-before-deserializing.md)帮助，请确保<xref:System.Runtime.Serialization.NetDataContractSerializer.Binder>属性始终设置反序列化之前。

## <a name="when-to-suppress-warnings"></a>何时禁止显示警告

[!INCLUDE[insecure-deserializers-common-safe-to-suppress](includes/insecure-deserializers-common-safe-to-suppress-md.md)]

## <a name="pseudo-code-examples"></a>伪代码示例

### <a name="violation"></a>冲突

```csharp
using System.IO;
using System.Runtime.Serialization;

public class ExampleClass
{
    public object MyDeserialize(byte[] bytes)
    {
        NetDataContractSerializer serializer = new NetDataContractSerializer();
        return serializer.Deserialize(new MemoryStream(bytes));
    }
}
```

```vb
Imports System.IO
Imports System.Runtime.Serialization

Public Class ExampleClass
    Public Function MyDeserialize(bytes As Byte()) As Object
        Dim serializer As NetDataContractSerializer = New NetDataContractSerializer()
        Return serializer.Deserialize(New MemoryStream(bytes))
    End Function
End Class
```

## <a name="related-rules"></a>相关的规则

[CA2311:反序列化而无需第一个设置 NetDataContractSerializer.Binder](ca2311-do-not-deserialize-without-first-setting-netdatacontractserializer-binder.md)

[CA2312:确保在反序列化之前设置 NetDataContractSerializer.Binder](ca2312-ensure-netdatacontractserializer-binder-is-set-before-deserializing.md)
