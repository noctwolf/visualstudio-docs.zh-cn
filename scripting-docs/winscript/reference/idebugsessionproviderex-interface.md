---
title: IDebugSessionProviderEx 接口 |Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
ms.assetid: 26c5da2d-8c93-4d2b-94d2-97aaa377dcfe
caps.latest.revision: 6
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: fae1cf673f47d3be586f83320b2d2c38c817e2cf
ms.sourcegitcommit: 8bf9e51c77a5a602fab9513b9187e59e57dfebad
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/16/2019
ms.locfileid: "54349213"
---
# <a name="idebugsessionproviderex-interface"></a>IDebugSessionProviderEx 接口
提供由调试器 IDE 以启用主机和语言启动调试的主要接口。 它将建立一个正在运行的应用程序的调试会话。 此接口由计算机调试管理器实现。  
  
 除了继承的方法之外`IUnknown`，则`IDebugSessionProviderEx`接口公开以下方法。  
  
## <a name="methods-in-vtable-order"></a>Vtable 顺序中的方法  
  
|方法|描述|  
|------------|-----------------|  
|[IDebugSessionProviderEx:CanJITDebug](../../winscript/reference/idebugsessionproviderex-canjitdebug.md)|确定是否能使用指定的应用程序进行实时调试。|  
|[IDebugSessionProviderEx:StartDebugSession](../../winscript/reference/idebugsessionproviderex-startdebugsession.md)|启动具有指定的应用程序的调试会话。|