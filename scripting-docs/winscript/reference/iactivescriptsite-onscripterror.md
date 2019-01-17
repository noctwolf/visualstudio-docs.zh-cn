---
title: IActiveScriptSite::OnScriptError |Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IActiveScriptSite.OnScriptError
apilocation:
- scrobj.dll
helpviewer_keywords:
- IActiveScriptSite_OnScriptError
ms.assetid: 5c9c85cc-21ad-4232-be83-a24cc7570108
caps.latest.revision: 7
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: d2c9cb95615ad0b978cc7fd9943b687e5a7f3cac
ms.sourcegitcommit: 8bf9e51c77a5a602fab9513b9187e59e57dfebad
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/16/2019
ms.locfileid: "54344559"
---
# <a name="iactivescriptsiteonscripterror"></a>IActiveScriptSite::OnScriptError
通知主机引擎运行脚本时发生了执行错误。  
  
## <a name="syntax"></a>语法  
  
```cpp
HRESULT OnScriptError(  
    IActiveScriptError *pase  // address of error interface  
);  
```  
  
#### <a name="parameters"></a>参数  
 `pase`  
 [in]错误对象的地址[IActiveScriptError](../../winscript/reference/iactivescripterror.md)接口。 主机可以使用此接口来获取有关执行错误的信息。  
  
## <a name="return-value"></a>返回值  
 返回`S_OK`正确处理了错误，则否则 OLE 定义的错误代码。  
  
## <a name="see-also"></a>请参阅  
 [IActiveScriptSite](../../winscript/reference/iactivescriptsite.md)