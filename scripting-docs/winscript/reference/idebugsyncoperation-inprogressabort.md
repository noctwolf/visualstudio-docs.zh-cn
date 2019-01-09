---
title: IDebugSyncOperation::InProgressAbort |Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IDebugSyncOperation.InProgressAbort
apilocation:
- jscript.dll
helpviewer_keywords:
- IDebugSyncOperation::InProgressAbort
ms.assetid: bfd0889c-b627-4843-b1c6-b6b918f42d61
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: cab8bae7f131d24c1a2c7272dc8d1178e12bf0e6
ms.sourcegitcommit: 116e9614867e0b3c627ce9001012a4c39435a42b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/08/2019
ms.locfileid: "54095519"
---
# <a name="idebugsyncoperationinprogressabort"></a>IDebugSyncOperation::InProgressAbort
取消正在进行另一个线程上的操作。  
  
## <a name="syntax"></a>语法  
  
```cpp
HRESULT InProgressAbort();  
```  
  
#### <a name="parameters"></a>参数  
 此方法需要任何参数。  
  
## <a name="return-value"></a>返回值  
 该方法返回 `HRESULT`。 可能的值包括（但并不限于）下表中的项。  
  
|“值”|描述|  
|-----------|-----------------|  
|`S_OK`|方法成功。|  
|`E_NOTIMPL`|无法取消该操作。|  
|`E_ABORT`|无法完成该操作。|  
  
## <a name="remarks"></a>备注  
 进程调试管理器调用此方法要取消正在进行另一线程中的操作的调试器线程。  
  
 如果`InProgressAbort`方法无法完成该操作，它将返回`E_ABORT`越早越好。 此方法可返回`E_NOTIMPL`如果不能取消该操作。  
  
## <a name="see-also"></a>请参阅  
 [IDebugSyncOperation 接口](../../winscript/reference/idebugsyncoperation-interface.md)