---
title: 不能更改值对话框 |Microsoft Docs
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- vs.debug.variables.failededit
dev_langs:
- FSharp
- VB
- CSharp
- C++
helpviewer_keywords:
- Cannot Change Value dialog box
- variables [debugger], editing
ms.assetid: 19e930c2-5fbf-4c83-aae8-a1dc3f8fcae8
caps.latest.revision: 12
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: cde574c1148af649fe421313cb943e1cebb1e221
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/12/2018
ms.locfileid: "49254717"
---
# <a name="cannot-change-value-dialog-box"></a>“无法更改值”对话框
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Error  
 `The value of this variable cannot be changed` &#124;`The name` *名称* `does not exist in the current context` &#124; *各种其他消息*  
  
 在调试器窗口（“自动”、“监视”或“局部变量”窗口）或“快速监视”对话框中，当尝试将变量内容更改为无效值时，会出现该消息框。 例如，如果尝试将整数变量的值设置为字符串，则将出现此消息框。  
  
## <a name="solution"></a>解决方案  
 确保键入到调试器窗口或“快速监视”对话框中的输入表示要尝试设置的变量的合法值。  
  
## <a name="see-also"></a>请参阅  
 [调试器中的表达式](../debugger/expressions-in-the-debugger.md)



