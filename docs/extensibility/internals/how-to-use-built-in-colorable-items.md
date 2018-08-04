---
title: 如何： 使用内置的可着色项 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- colorable items
- language services, built-in colorable items
ms.assetid: 5e5f3436-6bad-4fd2-8823-6a30353ba648
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 658b024a57912bf96a7988363f2bf363e9cb1f0a
ms.sourcegitcommit: 206e738fc45ff8ec4ddac2dd484e5be37192cfbd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/03/2018
ms.locfileid: "39512585"
---
# <a name="how-to-use-built-in-colorable-items"></a>如何： 使用内置的可着色项
使用内置的可着色项之前，您必须首先向发出信号，集成的开发环境 (IDE) 不提供此示例将为你自己自定义可着色项<xref:Microsoft.VisualStudio.TextManager.Interop.IVsProvideColorableItems>对象。 通过设置语言服务的注册表项执行此操作。  
  
## <a name="to-use-built-in-colorable-items"></a>若要使用内置的可着色项  
  
1.  下**HKEY_LOCAL_MACHINE\VisualStudio\\< X.Y > \Languages\Language 服务\\< 语言名称\>**，其中\<X.Y > 是版本[!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]和\<语言名称 > 是的名称的语言，创建名为的 DWORD 注册表项值**RequestStockColors**。  
  
2.  设置**RequestStockColors**注册表项值为*1*。  
  
     创建的注册表项，您的着色器的后<xref:Microsoft.VisualStudio.TextManager.Interop.IVsColorizer.ColorizeLine%2A>方法可以使用的成员<xref:Microsoft.VisualStudio.TextManager.Interop.DEFAULTITEMS>枚举，以供在编辑器的颜色属性的数组中填充。  
  
    > [!NOTE]
    >  如果你要提供自定义可着色项未设置此注册表项。 有关详细信息，请参阅[自定义可着色项](../../extensibility/internals/custom-colorable-items.md)。  
  
## <a name="see-also"></a>请参阅  
 [自定义编辑器中的语法着色](../../extensibility/syntax-coloring-in-custom-editors.md)   
 [旧版语言服务中的语法着色](../../extensibility/internals/syntax-coloring-in-a-legacy-language-service.md)   
 [实现语法着色](../../extensibility/internals/implementing-syntax-coloring.md)   
 [自定义可着色项](../../extensibility/internals/custom-colorable-items.md)   
 [注册旧版语言服务](../../extensibility/internals/registering-a-legacy-language-service2.md)