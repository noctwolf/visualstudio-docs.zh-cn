---
title: “列出寄存器”命令 | Microsoft Docs
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- debug.listregisters
helpviewer_keywords:
- list registers command
- Debug.ListRegisters command
- ListRegisters command
ms.assetid: 19a9d789-f6c9-46b3-b1f6-4934fc33e055
caps.latest.revision: 14
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 9e52b7de812be9168c30093b16041db42ea4676b
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/12/2018
ms.locfileid: "49195411"
---
# <a name="list-registers-command"></a>“列出寄存器”命令
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

  
显示选中寄存器的值并允许修改要显示的寄存器列表。  
  
## <a name="syntax"></a>语法  
  
```  
Debug.ListRegisters [/Display [{register|registerGroup}...]] [/List]  
[/Watch [{register|registerGroup}...]]  
[/Unwatch [{register|registerGroup}...]]  
```  
  
## <a name="switches"></a>开关  
 /Display [{`register`&#124;`registerGroup`}...]  
 显示指定 `register` 或 `registerGroup` 的值。 如果没有指定 `register` 或 `registerGroup`，将显示寄存器的默认列表。 如果没有指定任何开关，则出现相同行为。 例如：  
  
 `Debug.ListRegisters /Display eax`  
  
 等效于  
  
 `Debug.ListRegisters eax`  
  
 /List  
 在列表中显示所有寄存器组。  
  
 /Watch [{`register`&#124;`registerGroup`}...]  
 向列表添加一个或多个 `register` 或 `registerGroup` 值。  
  
 / Unwatch [{`register`&#124;`registerGroup`}...]  
 从列表中删除一个或多个 `register` 或 `registerGroup` 值。  
  
## <a name="remarks"></a>备注  
 别名 `r` 可用来代替 `Debug.ListRegisters`。  
  
## <a name="example"></a>示例  
 此示例使用 `Debug.ListRegisters` 别名 `r` 显示寄存组 `Flags` 的值。  
  
```  
r /Display Flags  
```  
  
## <a name="see-also"></a>请参阅  
 [Visual Studio 命令](../../ide/reference/visual-studio-commands.md)   
 [调试基础知识：“寄存器”窗口](../../debugger/debugging-basics-registers-window.md)   
 [如何：使用“寄存器”窗口](../../debugger/how-to-use-the-registers-window.md)



