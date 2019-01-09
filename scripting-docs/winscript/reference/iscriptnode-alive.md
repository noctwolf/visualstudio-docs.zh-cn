---
title: IScriptNode::Alive |Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IScriptNode.Alive
apilocation:
- scrobj.dll
helpviewer_keywords:
- IScriptNode::Alive
ms.assetid: d2755c83-e9b9-4c0a-acb7-25b554fc9fe8
caps.latest.revision: 11
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 23f0e804cbbbe6683b89f7b629b9677c7b92c64f
ms.sourcegitcommit: 116e9614867e0b3c627ce9001012a4c39435a42b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/08/2019
ms.locfileid: "54089552"
---
# <a name="iscriptnodealive"></a>IScriptNode::Alive
指示对象是否仍处于活动状态。  
  
## <a name="syntax"></a>语法  
  
```cpp
HRESULT Alive();  
```  
  
#### <a name="parameters"></a>参数  
 该方法采用任何参数。  
  
## <a name="return-value"></a>返回值  
 一个 `HRESULT`。 可能的值包括（但并不限于）下表中的项。  
  
|“值”|描述|  
|-----------|-----------------|  
|`S_OK`|脚本节点仍处于活动状态。|  
  
## <a name="remarks"></a>备注  
 如果该对象不处于活动状态，组件对象模型 (COM) 从对此方法的调用封送处理代理返回错误。  
  
## <a name="see-also"></a>请参阅  
 [IScriptNode 接口](../../winscript/reference/iscriptnode-interface.md)