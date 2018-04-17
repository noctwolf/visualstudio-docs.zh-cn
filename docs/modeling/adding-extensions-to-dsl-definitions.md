---
title: 将扩展添加到 DSL 定义 |Microsoft 文档
ms.custom: ''
ms.date: 11/04/2016
ms.topic: conceptual
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.technology: vs-ide-modeling
ms.openlocfilehash: a689d902a58eb747cbaec0bf7cebd740ade3e9bf
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/16/2018
---
# <a name="adding-extensions-to-dsl-definitions"></a>向 DSL 定义中添加扩展
DSL 定义扩展，可创建的域特定语言 (DSL) 的扩展包。 DSL 的方式相同，DSL 扩展，它包含在 Visual Studio 集成扩展 (VSIX) 中，可以安装在用户的计算机上。 中的其他功能可以动态启用和禁用在运行时。 Dsl 不必专门为扩展，并且扩展可以被设计为更高版本或者由第三方而无需更改扩展的 DSL。  
  
 其他功能可以包括以下：  
  
-   模型和呈现元素的属性  
  
-   形状和连接器的修饰符  
  
-   类、 关系、 形状和连接器  
  
-   验证约束  
  
-   工具箱项和选项卡  
  
 扩展 DSL 的用户可以创建和保存模型包含实例的其他功能，和其他已安装相应的扩展的用户可以读取这些。 尚未安装该扩展的用户不能使用其他功能，但它们可以更新和保存模型而不会丢失的其他功能。  

[!INCLUDE[modeling_sdk_info](includes/modeling_sdk_info.md)]

## <a name="see-also"></a>另请参阅  
 [相关的博客文章](https://blogs.msdn.microsoft.com/visualstudioalm/tag/code-index/)
