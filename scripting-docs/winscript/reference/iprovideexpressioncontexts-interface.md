---
title: IProvideExpressionContexts Interface | Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
helpviewer_keywords:
- IProvideExpressionContexts interface
ms.assetid: e4c70f2c-7d86-4fdc-a1cb-f5a0bb8ed037
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: b40825884b3c63af6be6d8bc852a5da4805f8975
ms.sourcegitcommit: d3a485d47c6ba01b0fc9878cbbb7fe88755b29af
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2019
ms.locfileid: "58152046"
---
# <a name="iprovideexpressioncontexts-interface"></a>IProvideExpressionContexts 接口
提供枚举特定组件已知的表达式上下文的一种方式。 脚本引擎通常情况下实现此接口。  
  
 进程调试管理器使用此接口以查找与给定线程关联的所有全局表达式上下文。  
  
> [!NOTE]
>  此接口是从所需的线程内调用的。 它是由实现者确定当前线程，并返回相应的枚举器。  
  
## <a name="methods"></a>方法  
 除了继承的方法之外`IUnknown`，则`IProvideExpressionContexts`接口公开以下方法。  
  
|方法|描述|  
|------------|-----------------|  
|[IProvideExpressionContexts::EnumExpressionContexts](../../winscript/reference/iprovideexpressioncontexts-enumexpressioncontexts.md)|返回已知的此组件表达式上下文的枚举器。|