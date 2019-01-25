---
title: IActiveScriptSiteWindow | Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
helpviewer_keywords:
- IActiveScriptSiteWindow interface
ms.assetid: 96d5c493-2c0b-47e2-848b-4a8dacdcd65c
caps.latest.revision: 7
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 9a160b17f4a46237ab78b378664a046fe8a0e7d4
ms.sourcegitcommit: 8bf9e51c77a5a602fab9513b9187e59e57dfebad
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/16/2019
ms.locfileid: "54345716"
---
# <a name="iactivescriptsitewindow"></a>IActiveScriptSiteWindow
此接口由该主机在与相同的对象支持用户界面实现[IActiveScriptSite](../../winscript/reference/iactivescriptsite.md) 。 不支持用户界面，如服务器、 主机不会实现`IActiveScriptSiteWindow`接口。 脚本引擎通过调用来访问此接口`QueryInterface`从`IActiveScriptSite`。  
  
## <a name="methods-in-vtable-order"></a>Vtable 顺序中的方法  
  
|方法|描述|  
|------------|-----------------|  
|[IActiveScriptSiteWindow::GetWindow](../../winscript/reference/iactivescriptsitewindow-getwindow.md)|检索可作为所有者的脚本引擎必须显示一个弹出窗口的窗口句柄。|  
|[IActiveScriptSiteWindow::EnableModeless](../../winscript/reference/iactivescriptsitewindow-enablemodeless.md)|将导致主机启用或禁用其主窗口，以及任何无模式对话框。|  
  
## <a name="see-also"></a>请参阅  
 [活动脚本接口](../../winscript/reference/active-script-interfaces.md)