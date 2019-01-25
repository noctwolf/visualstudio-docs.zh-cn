---
title: IProcessDebugManager Interface | Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
helpviewer_keywords:
- IProcessDebugManager interface
ms.assetid: b6ecb2bd-a4d1-4857-9232-036c154d0cb1
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 5feb67b1a616eeaa855b27cb12ea9b3146545ebd
ms.sourcegitcommit: 8bf9e51c77a5a602fab9513b9187e59e57dfebad
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/16/2019
ms.locfileid: "54345118"
---
# <a name="iprocessdebugmanager-interface"></a>IProcessDebugManager 接口
进程调试管理器的主接口。 此接口可以在进程中创建、添加或删除虚拟应用程序。 它可以枚举堆栈帧和应用程序线程。  
  
 除了继承的方法之外`IUnknown`，则`IProcessDebugManager`接口公开以下方法。  
  
## <a name="methods-in-vtable-order"></a>Vtable 顺序中的方法  
  
|方法|描述|  
|------------|-----------------|  
|[IProcessDebugManager::CreateApplication](../../winscript/reference/iprocessdebugmanager-createapplication.md)|创建一个新的调试应用程序对象，此应用程序。|  
|[IProcessDebugManager::GetDefaultApplication](../../winscript/reference/iprocessdebugmanager-getdefaultapplication.md)|返回当前进程的默认应用程序对象。|  
|[IProcessDebugManager::AddApplication](../../winscript/reference/iprocessdebugmanager-addapplication.md)|将添加到计算机调试管理器的列表正在运行的应用程序的应用程序。|  
|[IProcessDebugManager::RemoveApplication](../../winscript/reference/iprocessdebugmanager-removeapplication.md)|删除应用程序从正在运行的应用程序列表。|  
|[IProcessDebugManager::CreateDebugDocumentHelper](../../winscript/reference/iprocessdebugmanager-createdebugdocumenthelper.md)|创建此应用程序的新调试文档帮助程序。|