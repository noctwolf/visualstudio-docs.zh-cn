---
title: IDebugProgram2::GetDebugProperty |Microsoft Docs
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
- IDebugProgram2::GetDebugProperty
helpviewer_keywords:
- IDebugProgram2::GetDebugProperty
ms.assetid: d194224e-f0e6-46ab-85d4-9e2639e28946
caps.latest.revision: 11
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: e92d0a20fb9639e3a969ff30a5b6b512019895a5
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2018
ms.locfileid: "47468642"
---
# <a name="idebugprogram2getdebugproperty"></a>IDebugProgram2::GetDebugProperty
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

本主题的最新版本，请参阅[IDebugProgram2::GetDebugProperty](https://docs.microsoft.com/visualstudio/extensibility/debugger/reference/idebugprogram2-getdebugproperty)。  
  
获取该程序的属性。  
  
## <a name="syntax"></a>语法  
  
```cpp#  
HRESULT GetDebugProperty(   
   IDebugProperty2** ppProperty  
);  
```  
  
```csharp  
int GetDebugProperty(   
   out IDebugProperty2 ppProperty  
);  
```  
  
#### <a name="parameters"></a>参数  
 `ppProperty`  
 [out]返回[IDebugProperty2](../../../extensibility/debugger/reference/idebugproperty2.md)对象，表示该程序的属性。  
  
## <a name="return-value"></a>返回值  
 如果成功，则返回`S_OK`; 否则为返回错误代码。  
  
## <a name="remarks"></a>备注  
 此方法返回的属性是特定于该程序。 如果该程序需要返回多个属性，则[IDebugProperty2](../../../extensibility/debugger/reference/idebugproperty2.md)此方法返回的对象是一个容器的其他属性和调用[EnumChildren](../../../extensibility/debugger/reference/idebugproperty2-enumchildren.md)方法将返回所有属性的列表。  
  
 程序可能会公开任何数量和类型的其他属性，可以通过描述`IDebugProperty2`接口。 IDE 可能会显示通过泛型属性浏览器用户界面的其他程序属性。  
  
## <a name="see-also"></a>请参阅  
 [IDebugProgram2](../../../extensibility/debugger/reference/idebugprogram2.md)   
 [IDebugProperty2](../../../extensibility/debugger/reference/idebugproperty2.md)   
 [EnumChildren](../../../extensibility/debugger/reference/idebugproperty2-enumchildren.md)

