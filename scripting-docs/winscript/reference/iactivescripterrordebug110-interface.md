---
title: IActiveScriptErrorDebug110 接口 |Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
helpviewer_keywords:
- IActiveScriptErrorDebug110 Interface
ms.assetid: 5c1a4993-4cad-4ccf-89c2-53abfddfe1f2
caps.latest.revision: 6
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 1bac0c15f31f12ae48f6669bf9a0853550f8c191
ms.sourcegitcommit: d3a485d47c6ba01b0fc9878cbbb7fe88755b29af
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2019
ms.locfileid: "58150642"
---
# <a name="iactivescripterrordebug110-interface"></a>IActiveScriptErrorDebug110 接口
将功能添加到[IActiveScriptDebug 接口](../../winscript/reference/iactivescriptdebug-interface.md)。 此接口由 JavaScript 引擎实现，用于确定为什么会发生 BREAKREASON_ERROR 事件。  
  
> [!IMPORTANT]
>  此接口由 PDM v11.0 和更高版本实现。 在 activdbg100.h 中发现。  
  
## <a name="methods"></a>方法  
 `IActiveScriptErrorDebug110` 接口公开以下方法。  
  
|方法|描述|  
|------------|-----------------|  
|[IActiveScriptErrorDebug110::GetExceptionThrownKind](../../winscript/reference/iactivescripterrordebug110-getexceptionthrownkind.md)|返回某一引发的异常的异常类型。|