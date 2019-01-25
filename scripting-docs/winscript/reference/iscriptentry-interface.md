---
title: IScriptEntry 接口 |Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
helpviewer_keywords:
- IScriptEntry interface
ms.assetid: 86da3bc1-58b7-4d73-87ab-bc3ce34e3f41
caps.latest.revision: 12
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 9d7b33e2e5c90d5c489fe283575b4a2e45671f9a
ms.sourcegitcommit: 8bf9e51c77a5a602fab9513b9187e59e57dfebad
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/16/2019
ms.locfileid: "54349343"
---
# <a name="iscriptentry-interface"></a>IScriptEntry 接口
一个对象，实现`IScriptEntry`接口表示一个脚本块或函数对象。  
  
 除了继承的方法之外`IScriptNode`，则`IScriptEntry`接口公开以下方法。  
  
## <a name="methods-in-vtable-order"></a>Vtable 顺序中的方法  
  
|方法|描述|  
|------------|-----------------|  
|[IScriptEntry::GetBody](../../winscript/reference/iscriptentry-getbody.md)|返回对应的文本正文的`IScriptEntry`脚本块、 函数块或 scriptlet。|  
|[IScriptEntry::GetItemName](../../winscript/reference/iscriptentry-getitemname.md)|返回标识的项名称`IScriptEntry`对象。|  
|[IScriptEntry::GetName](../../winscript/reference/iscriptentry-getname.md)|对于表示单个对象 （如某个函数） 的条目，返回的对象的名称。|  
|[IScriptEntry::GetRange](../../winscript/reference/iscriptentry-getrange.md)|返回的起始位置和长度的一个条目。|  
|[IScriptEntry::GetSignature](../../winscript/reference/iscriptentry-getsignature.md)|返回类型信息`IScriptEntry`函数对象。|  
|[IScriptEntry::GetText](../../winscript/reference/iscriptentry-gettext.md)|返回对应的文本`IScriptEntry`脚本块中或包含在源代码`IScriptScriptlet`事件处理程序。|  
|[IScriptEntry::SetBody](../../winscript/reference/iscriptentry-setbody.md)|设置的正文中的文本`IScriptEntry`脚本块或`IScriptScriptlet`scriptlet。|  
|[IScriptEntry::SetItemName](../../winscript/reference/iscriptentry-setitemname.md)|设置标识的项名称`IScriptEntry`对象。|  
|[IScriptEntry::SetName](../../winscript/reference/iscriptentry-setname.md)|对于表示单个对象 （如某个函数） 的条目，设置的对象的名称。|  
|[IScriptEntry::SetSignature](../../winscript/reference/iscriptentry-setsignature.md)|设置类型信息`IScriptEntry`函数对象。|  
|[IScriptEntry::SetText](../../winscript/reference/iscriptentry-settext.md)|设置对应的文本`IScriptEntry`脚本块中或包含在源代码`IScriptScriptlet`事件处理程序。|  
  
## <a name="see-also"></a>请参阅  
 [活动脚本创作接口](../../winscript/reference/active-script-authoring-interfaces.md)