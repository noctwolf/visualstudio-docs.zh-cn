---
title: 类设计器中的 Visual C++ 枚举 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-general
ms.topic: conceptual
helpviewer_keywords:
- Class Designer [Visual Studio], enumerations
ms.assetid: 11e90ba1-18cd-44f8-9e26-e3746a7a19d1
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- cplusplus
ms.openlocfilehash: ac804f35c2d917e5443e61d4f2e53cde81165070
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/16/2018
---
# <a name="visual-c-enumerations-in-class-designer"></a>类设计器中的 Visual C++ 枚举
类设计器支持 C++ `enum` 和范围 `enum class` 类型。 下面是一个示例：  
  
```cpp
enum CardSuit {  
   Diamonds = 1,  
   Hearts = 2,  
   Clubs = 3,  
   Spades = 4  
};  
  
// or...  
enum class CardSuit {  
   Diamonds = 1,  
   Hearts = 2,  
   Clubs = 3,  
   Spades = 4  
};
```  
  
类图中的 C++ 枚举形状的外观和工作原理与结构形状类似，只不过其标签显示为 **Enum** 或 **Enum class**，标签的颜色为粉色而不是蓝色，并且具有带颜色的边框左边和上边。 两种枚举形状和结构形状都具有方角。  
  
有关使用 `enum` 类型的更多信息，请参阅[枚举](/cpp/cpp/enumerations-cpp)。  
  
## <a name="see-also"></a>请参阅
[使用 Visual Studio Code](working-with-visual-cpp-code.md)   
[枚举](/cpp/cpp/enumerations-cpp)