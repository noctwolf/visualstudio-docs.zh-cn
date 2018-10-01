---
title: IEEVisualizerDataProvider::GetNewObjectForVisualizer |Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- IEEVisualizerDataProvider::GetNewObjectForVisualizer
helpviewer_keywords:
- IEEVisualizerDataProvider::GetNewObjectForVisualizer method
ms.assetid: a898d549-4898-4fde-aad1-e8bb89129652
caps.latest.revision: 12
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: f344033e719a06cba084bedcda2a495bd48a70a6
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2018
ms.locfileid: "47471220"
---
# <a name="ieevisualizerdataprovidergetnewobjectforvisualizer"></a>IEEVisualizerDataProvider::GetNewObjectForVisualizer
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

本主题的最新版本，请参阅[IEEVisualizerDataProvider::GetNewObjectForVisualizer](https://docs.microsoft.com/visualstudio/extensibility/debugger/reference/ieevisualizerdataprovider-getnewobjectforvisualizer)。  
  
此方法获取可视化工具的一个新的对象。 此方法将始终从现有对象创建一个新的对象。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT GetNewObjectForVisualizer(  
   IDebugObject** ppObject  
);  
```  
  
```csharp  
int GetNewObjectForVisualizer(  
   out IDebugObject ppObject  
);  
```  
  
#### <a name="parameters"></a>参数  
 `ppObject`  
 [out]新的对象。  
  
## <a name="return-value"></a>返回值  
 如果成功，则返回`S_OK`; 否则为返回错误代码。  
  
## <a name="remarks"></a>备注  
 `This method` 重新计算结果的对象，它当前表示并返回一个新的对象形式的结果。 将更新现有对象，作为评估结果。  
  
## <a name="see-also"></a>请参阅  
 [IEEVisualizerDataProvider](../../../extensibility/debugger/reference/ieevisualizerdataprovider.md)   
 [IDebugObject](../../../extensibility/debugger/reference/idebugobject.md)

