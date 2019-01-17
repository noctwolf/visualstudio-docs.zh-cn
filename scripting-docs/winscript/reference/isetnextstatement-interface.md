---
title: ISetNextStatement 接口 |Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
ms.assetid: b570c2e0-a173-4f14-97d8-f39465753115
caps.latest.revision: 5
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: ac2d6dd0da14be5a624cff0b55985770b8d70fdf
ms.sourcegitcommit: 8bf9e51c77a5a602fab9513b9187e59e57dfebad
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/16/2019
ms.locfileid: "54344052"
---
# <a name="isetnextstatement-interface"></a>ISetNextStatement 接口
此接口由解释器以允许进程调试管理器更新当前语句实现。 从堆栈帧对象中，实现并 PDM 获取此接口通过 QueryInterface。  
  
 接口提供了可用于设置执行点，用于确定要执行的下一个语句的方法。  
  
 除了继承的方法之外`IUnknown`，则`ISetNextStatement`接口公开以下方法。  
  
## <a name="methods-in-vtable-order"></a>Vtable 顺序中的方法  
  
|方法|描述|  
|------------|-----------------|  
|[ISetNextStatement::CanSetNextStatement](../../winscript/reference/isetnextstatement-cansetnextstatement.md)|确定是否可以将执行点设置为指定的位置。|  
|[ISetNextStatement::SetNextStatement](../../winscript/reference/isetnextstatement-setnextstatement.md)|将执行点设置为指定的位置。|