---
title: IScriptNode::GetParent |Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IScriptNode.GetParent
apilocation:
- scrobj.dll
helpviewer_keywords:
- IScriptNode::GetParent
ms.assetid: 0fb813f6-ab94-46b2-b0cf-ef5d1cd38ae4
caps.latest.revision: 7
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: b45fc7be1a5178e952fefcd794171410d149a1f4
ms.sourcegitcommit: 116e9614867e0b3c627ce9001012a4c39435a42b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/08/2019
ms.locfileid: "54090020"
---
# <a name="iscriptnodegetparent"></a>IScriptNode::GetParent
返回`IScriptNode`是父对象的对象。  
  
## <a name="syntax"></a>语法  
  
```cpp
HRESULT GetParent(  
   IScriptNode       **ppsnParent  
);  
```  
  
#### <a name="parameters"></a>参数  
 `ppsnParent`  
 [out]一个变量来接收指向指针的地址`IScriptNode`接口的父实例。  
  
 如果类实现`IScriptEntry`或`IScriptScriptlet`、`IScriptNode`返回对象。  
  
 如果类实现`IScriptNode`（表示网页上），则返回 NULL。  
  
## <a name="return-value"></a>返回值  
 一个 `HRESULT`。 可能的值包括（但并不限于）下表中的项。  
  
|值|描述|  
|-----------|-----------------|  
|`S_OK`|方法成功。|  
  
## <a name="remarks"></a>备注  
  
## <a name="see-also"></a>请参阅  
 [IScriptNode 接口](../../winscript/reference/iscriptnode-interface.md)