---
title: IDebugSessionProvider::StartDebugSession |Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IDebugSessionProvider.StartDebugSession
apilocation:
- scrobj.dll
helpviewer_keywords:
- IDebugSessionProvider::StartDebugSession
ms.assetid: 47697dfb-d4e1-492c-a14f-753e28195a76
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: fe0ce2d55a945c5c35dc82700aa45e1849d6a2c0
ms.sourcegitcommit: 116e9614867e0b3c627ce9001012a4c39435a42b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/08/2019
ms.locfileid: "54096327"
---
# <a name="idebugsessionproviderstartdebugsession"></a>IDebugSessionProvider::StartDebugSession
启动具有指定的应用程序的调试会话。  
  
## <a name="syntax"></a>语法  
  
```cpp
HRESULT StartDebugSession(  
   IRemoteDebugApplication*  pda  
);  
```  
  
#### <a name="parameters"></a>参数  
 `pda`  
 [in]指定调试应用程序。  
  
## <a name="return-value"></a>返回值  
 该方法返回 `HRESULT`。 可能的值包括（但并不限于）下表中的项。  
  
|“值”|描述|  
|-----------|-----------------|  
|`S_OK`|方法成功。|  
  
## <a name="remarks"></a>备注  
 此方法会启动与指定的应用程序的调试会话。 调试程序应调用`IRemoteDebugApplication::ConnectDebugger`之前从该调用返回。  
  
## <a name="see-also"></a>请参阅  
 [IDebugSessionProvider 接口](../../winscript/reference/idebugsessionprovider-interface.md)   
 [IRemoteDebugApplication::ConnectDebugger](../../winscript/reference/iremotedebugapplication-connectdebugger.md)