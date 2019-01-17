---
title: IActiveScriptProfilerControl2 Interface | Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
helpviewer_keywords:
- IActiveScriptProfilerControl2 interface
ms.assetid: 89455276-5c23-420b-a7e0-804a32635291
caps.latest.revision: 5
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 9dad5d4a90eecdc6c93d86df9f9b18273bc471a4
ms.sourcegitcommit: 8bf9e51c77a5a602fab9513b9187e59e57dfebad
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/16/2019
ms.locfileid: "54349759"
---
# <a name="iactivescriptprofilercontrol2-interface"></a>IActiveScriptProfilerControl2 接口
提供添加启动或停止分析运行脚本时的功能的方法。  
  
## <a name="methods"></a>方法  
  
|方法|描述|  
|------------|-----------------|  
|[IActiveScriptProfilerControl2::CompleteProfilerStart](../../winscript/reference/iactivescriptprofilercontrol2-completeprofilerstart.md)|通知探查器在所有适用的脚本引擎探查已经开始。 这使您若要获取完整的调用堆栈，则[!INCLUDE[javascript](../../javascript/includes/javascript-md.md)]时开始分析正在运行。|  
|[IActiveScriptProfilerControl2::PrepareProfilerStop](../../winscript/reference/iactivescriptprofilercontrol2-prepareprofilerstop.md)|通知探查器要停止分析在所有适用的脚本引擎。 这使您若要获取完整的调用堆栈，则[!INCLUDE[javascript](../../javascript/includes/javascript-md.md)]时停止分析正在运行。|  
  
## <a name="see-also"></a>请参阅  
 [IActiveScriptProfilerControl 接口](../../winscript/reference/iactivescriptprofilercontrol-interface.md)   
 [Active Script Profiler 接口](../../winscript/reference/active-script-profiler-interfaces.md)