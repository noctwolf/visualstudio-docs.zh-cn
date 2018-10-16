---
title: 如何： 使用内置的可着色项 |Microsoft Docs
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- colorable items
- language services, built-in colorable items
ms.assetid: 5e5f3436-6bad-4fd2-8823-6a30353ba648
caps.latest.revision: 18
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 9cd6cc62e54fa35a8b146c93e2931b2cf35145b5
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/12/2018
ms.locfileid: "49209764"
---
# <a name="how-to-use-built-in-colorable-items"></a>如何： 使用内置的可着色项
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

使用内置的可着色项之前，您必须首先向发出信号，集成的开发环境 (IDE) 不提供此示例将为你自己自定义可着色项<xref:Microsoft.VisualStudio.TextManager.Interop.IVsProvideColorableItems>对象。 通过设置语言服务的注册表项执行此操作。  
  
### <a name="to-use-built-in-colorable-items"></a>若要使用内置的可着色项  
  
1.  下 HKEY_LOCAL_MACHINE\VisualStudio\\*X.Y*\Languages\Language 服务\\*语言名称*，其中*X.Y* 版本[!INCLUDE[vsprvs](../../includes/vsprvs-md.md)]并*语言名称*是名称的语言，创建名为的 DWORD 注册表项值`RequestStockColors`。  
  
2.  设置`RequestStockColors`注册表项值设置为 1。  
  
     创建的注册表项，您的着色器的后<xref:Microsoft.VisualStudio.TextManager.Interop.IVsColorizer.ColorizeLine%2A>方法可以使用的成员<xref:Microsoft.VisualStudio.TextManager.Interop.DEFAULTITEMS>枚举，以供在编辑器的颜色属性的数组中填充。  
  
    > [!NOTE]
    >  如果你要提供自定义可着色项未设置此注册表项。 有关详细信息，请参阅[自定义可着色项](../../extensibility/internals/custom-colorable-items.md)。  
  
## <a name="see-also"></a>请参阅  
 [自定义编辑器中的语法着色](../../extensibility/syntax-coloring-in-custom-editors.md)   
 [旧版语言服务中的语法着色](../../extensibility/internals/syntax-coloring-in-a-legacy-language-service.md)   
 [实现语法着色](../../extensibility/internals/implementing-syntax-coloring.md)   
 [自定义可着色项](../../extensibility/internals/custom-colorable-items.md)   
 [注册旧版语言服务](../../extensibility/internals/registering-a-legacy-language-service2.md)

