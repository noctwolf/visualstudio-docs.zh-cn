---
title: IActiveScriptProfilerControl Interface | Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
ms.assetid: 1448b394-9743-41b5-8eb9-5026a45773a4
caps.latest.revision: 10
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 7caa09f384ce460a3e73b21b10d6d8022182dde7
ms.sourcegitcommit: 8bf9e51c77a5a602fab9513b9187e59e57dfebad
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/16/2019
ms.locfileid: "54349486"
---
# <a name="iactivescriptprofilercontrol-interface"></a>IActiveScriptProfilerControl 接口
由支持分析脚本引擎实现。 通常情况下，实现的对象`IActiveScriptProfilerControl`还实现[IActiveScript](../../winscript/reference/iactivescript.md)接口。 在这种情况下，可以获取的句柄`IActiveScriptProfilerControl`接口通过调用`IUnknown::QueryInterface`对象上的方法。 接口提供了用于停止和启动分析脚本引擎上必需的方法。  
  
## <a name="methods"></a>方法  
  
|方法|描述|  
|------------|-----------------|  
|[IActiveScriptProfilerControl::StartProfiling](../../winscript/reference/iactivescriptprofilercontrol-startprofiling.md)|启动脚本引擎的分析。|  
|[IActiveScriptProfilerControl::SetProfilerEventMask](../../winscript/reference/iactivescriptprofilercontrol-setprofilereventmask.md)|设置脚本引擎中的探查器事件掩码。|  
|[IActiveScriptProfilerControl::StopProfiling](../../winscript/reference/iactivescriptprofilercontrol-stopprofiling.md)|停止分析脚本引擎上。|  
  
## <a name="see-also"></a>请参阅  
 [Active Script Profiler 接口](../../winscript/reference/active-script-profiler-interfaces.md)