---
title: IActiveScriptWinRTErrorDebug::GetRestrictedErrorReference |Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
helpviewer_keywords:
- IActiveScriptWinRTErrorDebug::GetRestrictedErrorReference
ms.assetid: fcf60971-9518-4b24-a3a6-1e2e30a02cea
caps.latest.revision: 5
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: b343a67bcf759699d285674827f782159a2c4251
ms.sourcegitcommit: d3a485d47c6ba01b0fc9878cbbb7fe88755b29af
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2019
ms.locfileid: "58149349"
---
# <a name="iactivescriptwinrterrordebuggetrestrictederrorreference"></a>IActiveScriptWinRTErrorDebug::GetRestrictedErrorReference
如果可用，则返回 Windows 运行时限制引用错误。  
  
> [!IMPORTANT]
>  [IActiveScriptWinRTErrorDebug 接口](../../winscript/reference/iactivescriptwinrterrordebug-interface.md)是实现由 PDM v11.0 和更高版本。 在 activdbg100.h 中发现。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT GetRestrictedErrorReference([out] BSTR * referenceString);  
```  
  
#### <a name="parameters"></a>参数  
 `referenceString`  
 [out]引用错误字符串。  
  
## <a name="see-also"></a>请参阅  
 [IActiveScriptWinRTErrorDebug 接口](../../winscript/reference/iactivescriptwinrterrordebug-interface.md)