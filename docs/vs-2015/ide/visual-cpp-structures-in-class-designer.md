---
title: 类设计器中的 Visual C++ 结构 | Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Class Designer [Visual Studio], structures
ms.assetid: bad18ab6-d956-47a6-a413-811cc26db5f5
caps.latest.revision: 15
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: a701aae6e9c504d24d149dd5941a0f9623111ce2
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2018
ms.locfileid: "47470633"
---
# <a name="visual-c-structures-in-class-designer"></a>类设计器中的 Visual C++ 结构
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

本主题的最新版本，请参阅[类设计器中的 Visual c + + 结构](https://docs.microsoft.com/visualstudio/ide/visual-cpp-structures-in-class-designer)。  
  
类设计器支持使用关键字 `struct` 声明的 C++ 结构。 下面是一个示例：  
  
```  
struct MyStructure  
{  
   char a;  
   int i;  
   long j;  
};  
```  
  
 若要详细了解如何使用 `struct` 类型，请参阅 [struct](http://msdn.microsoft.com/library/3c6ba273-e248-4ff1-8c69-d2abcf1263c6)。  
  
 类图中的 C++ 结构形状的外观和运行方式都与类形状相似，不同之处在于它的标签名为 **Struct**，且为方角（而不是圆角）。  
  
|代码元素|类设计器视图|  
|------------------|-------------------------|  
|`struct StructureName {};`|**StructureName**<br /><br /> 结构|  
  
## <a name="see-also"></a>请参阅  
 [使用 Visual C++ 代码（类设计器）](../ide/working-with-visual-cpp-code-class-designer.md)   
 [类和结构](http://msdn.microsoft.com/library/516dd496-13fb-4f17-845a-e9ca45437873)   
 [struct](http://msdn.microsoft.com/library/3c6ba273-e248-4ff1-8c69-d2abcf1263c6)



