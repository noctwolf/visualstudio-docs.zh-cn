---
title: IDispatchEx::DeleteMemberByDispID |Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IDispatchEx.DeleteMemberByDispID
apilocation:
- scrobj.dll
helpviewer_keywords:
- DeleteMemberByDispID method
ms.assetid: f61231e5-ba93-4ac3-bde8-d363548356b3
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: de99e74cf12939a31c99cdc59ce8ad7fd685ae03
ms.sourcegitcommit: 116e9614867e0b3c627ce9001012a4c39435a42b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/08/2019
ms.locfileid: "54086861"
---
# <a name="idispatchexdeletememberbydispid"></a>IDispatchEx::DeleteMemberByDispID
删除成员的 DISPID。  
  
## <a name="syntax"></a>语法  
  
```cpp
HRESULT DeleteMemberByDispID(  
    DISPID id  
);  
```  
  
#### <a name="parameters"></a>参数  
 `id`  
 成员标识符。 使用`GetDispID`或`GetNextDispID`若要获取的调度标识符。  
  
## <a name="return-value"></a>返回值  
 返回以下值之一：  
  
|||  
|-|-|  
|`S_OK`|成功。|  
|`S_FALSE`|成员存在，但不能删除。|  
  
## <a name="remarks"></a>备注  
 如果删除该成员，则需要保持有效，DISPID `GetNextDispID`。  
  
 如果删除具有给定名称的成员，并且以后重新创建具有相同名称的成员，DISPID 应相同。 （仅大小写不同的成员名称是否"相同"与对象相关。）  
  
## <a name="example"></a>示例  
  
```cpp
BSTR bstrName;  
DISPID dispid;  
IDispatchEx *pdex;   
  
// Assign to pdex and bstrName  
if (SUCCEEDED(pdex->GetDispID(bstrName, fdexNameCaseSensitive, &dispid)))  
    pdex->DeleteMemberByDispID(dispid);  
```  
  
## <a name="see-also"></a>请参阅  
 [IDispatchEx 接口](../../winscript/reference/idispatchex-interface.md)   
 [IDispatchEx::GetDispID](../../winscript/reference/idispatchex-getdispid.md)   
 [IDispatchEx::GetNextDispID](../../winscript/reference/idispatchex-getnextdispid.md)