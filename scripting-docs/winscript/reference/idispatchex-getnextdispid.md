---
title: IDispatchEx::GetNextDispID |Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IDispatchEx.GetNextDispID
apilocation:
- scrobj.dll
helpviewer_keywords:
- GetNextDispID method
ms.assetid: 8263d441-85ee-47f4-bdba-fbf2ad07e85f
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 24aa5ad2b780d5ff61efcde4d24b6700bb5b353e
ms.sourcegitcommit: 116e9614867e0b3c627ce9001012a4c39435a42b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/08/2019
ms.locfileid: "54092984"
---
# <a name="idispatchexgetnextdispid"></a>IDispatchEx::GetNextDispID
枚举对象的成员。  
  
## <a name="syntax"></a>语法  
  
```cpp
HRESULT GetNextDispID(  
   DWORD grfdex,  
   DISPID id,  
   DISPID *pid  
);  
```  
  
#### <a name="parameters"></a>参数  
 `grfdex`  
 确定要枚举的项的集。 这可以是以下值的组合：  
  
|值|含义|  
|-----------|-------------|  
|fdexEnumDefault|请求该对象枚举的默认元素。 该对象可以枚举元素的任何组。|  
|fdexEnumAll|请求该对象枚举的所有元素。 该对象可以枚举元素的任何组。|  
  
 `id`  
 标识的当前成员。 GetNextDispID 检索后此枚举中的项。 使用 GetDispID 或 GetNextDispID 的上一个调用来获取此标识符。 使用 DISPID_STARTENUM 值来获取第一项的第一个标识符。  
  
 `pid`  
 枚举中接收的下一项的标识符的 DISPID 变量的地址。  
  
 如果通过删除成员`DeleteMemberByName`或`DeleteMemberByDispID`，则`DISPID`需要保持有效， `GetNextDispID`。  
  
## <a name="return-value"></a>返回值  
 返回以下值之一：  
  
|||  
|-|-|  
|`S_OK`|成功。|  
|`S_FALSE`|枚举是完成的。|  
  
## <a name="example"></a>示例  
  
```cpp
HRESULT hr;  
   BSTR bstrName;  
   DISPID dispid;  
   IDispatchEx *pdex;  
  
   // Assign to pdex  
   hr = pdex->GetNextDispID(fdexEnumAll, DISPID_STARTENUM, &dispid);  
   while (hr == NOERROR)  
   {  
      hr = pdex->GetMemberName(dispid, &bstrName);  
      if (!wcscmp(bstrName, OLESTR("Bar")))  
      {  
         SysFreeString(bstrName);  
         return TRUE;  
      }  
      SysFreeString(bstrName);  
      hr = pdex->GetNextDispID(fdexEnumAll, dispid, &dispid);  
   }  
```  
  
## <a name="see-also"></a>请参阅  
 [IDispatchEx 接口](../../winscript/reference/idispatchex-interface.md)   
 [IDispatchEx::GetDispID](../../winscript/reference/idispatchex-getdispid.md)   
 [IDispatchEx::GetNextDispID](#lrfidispatchexgetnextdispid)   
 [IDispatchEx::DeleteMemberByName](../../winscript/reference/idispatchex-deletememberbyname.md)   
 [IDispatchEx::DeleteMemberByDispID](../../winscript/reference/idispatchex-deletememberbydispid.md)