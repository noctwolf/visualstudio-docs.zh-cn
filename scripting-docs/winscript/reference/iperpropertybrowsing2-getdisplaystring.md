---
title: IPerPropertyBrowsing2::GetDisplayString |Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IPerPropertyBrowsing2.GetDisplayString
apilocation:
- scrobj.dll
helpviewer_keywords:
- IPerPropertyBrowsing2::GetDisplayString
ms.assetid: 8f75c6a9-86a9-4e2d-8cb4-74e7b1c0a524
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: e4947ebdeac26ae759fb739dd417607dea885ee5
ms.sourcegitcommit: 116e9614867e0b3c627ce9001012a4c39435a42b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/08/2019
ms.locfileid: "54091568"
---
# <a name="iperpropertybrowsing2getdisplaystring"></a>IPerPropertyBrowsing2::GetDisplayString
获取要显示不是本质上可查看返回的文本的字符串是描述属性的名称，并在调用方的用户界面中显示。  
  
## <a name="syntax"></a>语法  
  
```cpp
HRESULT GetDisplayString(  
   DISPID  dispid,  
   BSTR*  pBstr  
);  
```  
  
#### <a name="parameters"></a>参数  
 `dispid`  
 [in]调度请求其显示名称的属性的标识符。  
  
 `pBstr`  
 [out]指向`BSTR`包含通过标识的属性的显示名称`dispID`。  
  
## <a name="return-value"></a>返回值  
 返回一个有效`HRESULT`，通常`S_OK`。  
  
## <a name="remarks"></a>备注  
 返回的字符串不是属性的合法值。 只需属性的字符串显示它。  
  
## <a name="see-also"></a>请参阅  
 [IPerPropertyBrowsing2 接口 1](../../winscript/reference/iperpropertybrowsing2-interface-1.md)