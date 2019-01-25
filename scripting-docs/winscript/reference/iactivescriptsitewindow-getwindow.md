---
title: IActiveScriptSiteWindow::GetWindow |Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IActiveScriptSiteWindow.GetWindow
apilocation:
- scrobj.dll
helpviewer_keywords:
- IActiveScriptSiteWindow_GetWindow
ms.assetid: 6284e38c-9dfb-4d69-903d-f243f78c0331
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 268a54ccdcbd70ed159758720db0735f16d81492
ms.sourcegitcommit: 8bf9e51c77a5a602fab9513b9187e59e57dfebad
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/16/2019
ms.locfileid: "54349044"
---
# <a name="iactivescriptsitewindowgetwindow"></a>IActiveScriptSiteWindow::GetWindow
检索到的窗口可以作为所有者的脚本引擎必须显示一个弹出窗口的句柄。  
  
## <a name="syntax"></a>语法  
  
```cpp
HRESULT GetWindow(  
    HWND *phwnd  // address of variable for window handle  
);  
```  
  
#### <a name="parameters"></a>参数  
 `phwnd`  
 [out]一个变量来接收的窗口句柄的地址。  
  
## <a name="return-value"></a>返回值  
 返回`S_OK`如果成功，或`E_FAIL`是否发生错误。  
  
## <a name="remarks"></a>备注  
 此方法是类似于`IOleWindow::GetWindow`方法。  
  
## <a name="see-also"></a>请参阅  
 [IActiveScriptSiteWindow](../../winscript/reference/iactivescriptsitewindow.md)