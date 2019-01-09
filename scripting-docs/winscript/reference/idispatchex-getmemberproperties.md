---
title: IDispatchEx::GetMemberProperties |Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IDispatchEx.GetMemberProperties
apilocation:
- scrobj.dll
helpviewer_keywords:
- GetMemberProperties method
ms.assetid: 20d43209-12e2-472a-9bf3-81eced137b71
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 51e01ef3fa6d5e0611875f6402b79e53f8c83cac
ms.sourcegitcommit: 116e9614867e0b3c627ce9001012a4c39435a42b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/08/2019
ms.locfileid: "54088187"
---
# <a name="idispatchexgetmemberproperties"></a>IDispatchEx::GetMemberProperties
检索成员的属性。  
  
## <a name="syntax"></a>语法  
  
```cpp
HRESULT GetMemberProperties(  
   DISPID id,  
   DWORD grfdexFetch,  
   DWORD *pgrfdex  
);  
```  
  
#### <a name="parameters"></a>参数  
 `id`  
 标识成员。 使用`GetDispID`或`GetNextDispID`若要获取的调度标识符。  
  
 `grfdexFetch`  
 确定要检索的属性。 这可以是下列出的值的组合`pgrfdex`和/或以下值的组合：  
  
|值|含义|  
|-----------|-------------|  
|grfdexPropCanAll|FdexPropCanGet、 fdexPropCanPut、 fdexPropCanPutRef、 fdexPropCanCall、 fdexPropCanConstruct 和 fdexPropCanSourceEvents 相结合。|  
|grfdexPropCannotAll|FdexPropCannotGet、 fdexPropCannotPut、 fdexPropCannotPutRef、 fdexPropCannotCall、 fdexPropCannotConstruct 和 fdexPropCannotSourceEvents 相结合。|  
|grfdexPropExtraAll|FdexPropNoSideEffects 和 fdexPropDynamicType 相结合。|  
|grfdexPropAll|GrfdexPropCanAll、 grfdexPropCannotAll 和 grfdexPropExtraAll 相结合。|  
  
 `pgrfdex`  
 地址`DWORD`用于接收请求的属性。 这可以是以下值的组合：  
  
|值|含义|  
|-----------|-------------|  
|fdexPropCanGet|可以使用 DISPATCH_PROPERTYGET 获取该成员。|  
|fdexPropCannotGet|不能使用 DISPATCH_PROPERTYGET 获取该成员。|  
|fdexPropCanPut|可以使用 DISPATCH_PROPERTYPUT 设置该成员。|  
|fdexPropCannotPut|该成员不能使用 DISPATCH_PROPERTYPUT 进行设置。|  
|fdexPropCanPutRef|可以使用 DISPATCH_PROPERTYPUTREF 设置该成员。|  
|fdexPropCannotPutRef|该成员不能使用 DISPATCH_PROPERTYPUTREF 进行设置。|  
|fdexPropNoSideEffects|该成员没有任何副作用。 例如，调试程序可以安全地 get/set/调用此成员而不更改脚本正在调试的状态。|  
|fdexPropDynamicType|该成员是动态的可以更改对象的生存期内。|  
|fdexPropCanCall|作为使用 DISPATCH_METHOD 的方法，可以调用该成员。|  
|fdexPropCannotCall|作为使用 DISPATCH_METHOD 方法不能调用该成员。|  
|fdexPropCanConstruct|可以作为构造函数使用 DISPATCH_CONSTRUCT 调用该成员。|  
|fdexPropCannotConstruct|不能作为构造函数使用 DISPATCH_CONSTRUCT 调用该成员。|  
|fdexPropCanSourceEvents|成员可以激发事件。|  
|fdexPropCannotSourceEvents|成员无法激发事件。|  
  
## <a name="return-value"></a>返回值  
 返回以下值之一：  
  
|||  
|-|-|  
|`S_OK`|成功。|  
|`DISP_E_UNKNOWNNAME`|不知道名称。|  
  
## <a name="example"></a>示例  
  
```cpp
BSTR bstrName;  
   DISPID dispid;  
   IDispatchEx *pdex;   
   DWORD dwProps;  
  
   // Assign to pdex and bstrName  
   if (SUCCEEDED(pdex->GetDispID(bstrName, fdexNameCaseSensitive, &dispid)) &&  
      SUCCEEDED(pdex->GetMemberProperties(dispid, grfdexPropAll, &dwProps)) &&  
         (dwProps & fdexPropCanPut))  
   {  
      // Assign to member  
   }  
```  
  
## <a name="see-also"></a>请参阅  
 [IDispatchEx 接口](../../winscript/reference/idispatchex-interface.md)   
 [IDispatchEx::GetDispID](../../winscript/reference/idispatchex-getdispid.md)   
 [IDispatchEx::GetNextDispID](../../winscript/reference/idispatchex-getnextdispid.md)