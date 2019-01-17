---
title: IProvideExpressionContexts Interface | Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
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
ms.openlocfilehash: 91f4251fec57001ba6c7a4ea1804ec72371418bb
ms.sourcegitcommit: 8bf9e51c77a5a602fab9513b9187e59e57dfebad
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/16/2019
ms.locfileid: "54345092"
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