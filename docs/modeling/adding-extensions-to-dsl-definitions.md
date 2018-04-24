---
title: 向 DSL 定义中添加扩展
ms.date: 11/04/2016
ms.topic: conceptual
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.technology: vs-ide-modeling
ms.openlocfilehash: 7de01ec87ca4367dcd3453c41e38c653c5184beb
ms.sourcegitcommit: 4c0bc21d2ce2d8e6c9d3b149a7d95f0b4d5b3f85
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/20/2018
---
# <a name="add-extensions-to-dsl-definitions"></a>将扩展添加到 DSL 定义

DSL 定义扩展，可创建的域特定语言 (DSL) 的扩展包。 DSL 的方式相同，DSL 扩展，它包含在 Visual Studio 集成扩展 (VSIX) 中，可以安装在用户的计算机上。 中的其他功能可以动态启用和禁用在运行时。 Dsl 不必专门为扩展，并且扩展可以被设计为更高版本，或者由第三方，而无需更改扩展的 DSL。

DSL 扩展可以包括以下功能：

-   模型和呈现元素的属性

-   形状和连接器的修饰符

-   类、 关系、 形状和连接器

-   验证约束

-   工具箱项和选项卡

扩展 DSL 的用户可以创建和保存模型包含的其他功能的实例。 模型可以读取由其他用户已安装相应的扩展。 尚未安装该扩展的用户不能使用其他功能，但它们可以更新和保存模型而不会丢失的其他功能。

[!INCLUDE[modeling_sdk_info](includes/modeling_sdk_info.md)]

## <a name="see-also"></a>请参阅

- [相关的博客文章](https://blogs.msdn.microsoft.com/visualstudioalm/tag/code-index/)
