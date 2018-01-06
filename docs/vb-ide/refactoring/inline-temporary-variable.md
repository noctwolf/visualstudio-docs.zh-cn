---
title: "内联临时变量的重构 (Visual Basic 中) |Microsoft 文档"
ms.custom: 
ms.date: 11/17/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a63d6407-5acb-4d5f-8c0e-ecedddc07177
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 3607e646f5f1ccc6121e5ee8a5b71772008f1ce8
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="inline-a-temporary-variable-in-visual-basic"></a>内联在 Visual Basic 中的临时变量
**新增功能：**可删除临时变量的用途，并将其替换为实际的代码。

**何时：**使用的临时变量会使代码难以理解。  

**原因：**删除临时变量可能会使代码易于阅读在某些情况下

**如何：**

1. 突出显示，或将文本光标置于要进行内联的临时变量：

   ![突出显示的代码](media/inline_highlight.png)

1. 接下来，请执行以下任一操作：
   * **键盘**
     * 按**Ctrl +。** 向触发器**快速操作和重构**菜单，然后选择**内联临时变量**从预览窗口弹出窗口。
   * **鼠标**
     * 右键单击代码中，选择**快速操作和重构**菜单，然后选择**内联临时变量**从预览窗口弹出窗口。

   将删除变量和其用法立即替换该变量的值。

   ![内联结果](media/inline_result.png)

## <a name="see-also"></a>请参阅
[重构 (Visual Basic)](../refactoring-vb.md)