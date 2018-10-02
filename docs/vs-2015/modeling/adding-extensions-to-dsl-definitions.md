---
title: 向 DSL 定义中添加扩展 |Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-tfs-dev14
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 07e133be-92ab-4936-a02b-45d2012bd0a6
caps.latest.revision: 8
author: gewarren
ms.author: gewarren
manager: douge
ms.openlocfilehash: e3b8cb28edb6959511a0cfdf157e323d6706e5f6
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2018
ms.locfileid: "47476828"
---
# <a name="adding-extensions-to-dsl-definitions"></a>向 DSL 定义中添加扩展
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

本主题的最新版本，请参阅[添加到 DSL 定义的扩展](https://docs.microsoft.com/visualstudio/modeling/adding-extensions-to-dsl-definitions)。  
  
DSL 定义扩展插件，可创建的域特定语言 (DSL) 的扩展包。 DSL 的方式相同，DSL 扩展，它包含在 Visual Studio 集成扩展 (VSIX) 中，可以安装在用户的计算机上。 可以动态启用和禁用在运行时的其他功能。 Dsl 无需显式设计为扩展插件，并扩展可以被设计为更高版本或者由第三方而无需更改扩展的 DSL。  
  
 其他功能可以包括：  
  
-   模型和表示元素的属性  
  
-   形状和连接符的修饰器  
  
-   类、 关系、 形状和连接线  
  
-   验证约束  
  
-   工具箱项和选项卡  
  
 扩展 DSL 的用户可以创建和保存模型包含的其他功能的实例和已安装相应的扩展的其他用户可以读取这些。 未安装该扩展的用户不能使用其他功能，但它们可以更新和保存模型而不会丢失的其他功能。  
  
 有关示例代码和有关此功能的详细信息，请参阅[Visual Studio 可视化和建模 SDK](http://go.microsoft.com/fwlink/?LinkID=186128) Web 站点。  
  
## <a name="see-also"></a>请参阅  
 [Visual Studio 可视化和建模 SDK](http://go.microsoft.com/fwlink/?LinkID=186128)



