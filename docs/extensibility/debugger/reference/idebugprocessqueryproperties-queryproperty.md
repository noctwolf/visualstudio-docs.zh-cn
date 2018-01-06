---
title: "IDebugProcessQueryProperties::QueryProperty |Microsoft 文档"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: IDebugProcessQueryProperties::QueryProperty
ms.assetid: 9a91707d-a590-44ef-b122-69d9816a7a79
caps.latest.revision: "6"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: 9a7635b8da93f777a2952e1f7f7fbe7ad9f245dd
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="idebugprocessquerypropertiesqueryproperty"></a>IDebugProcessQueryProperties::QueryProperty
指定的属性值在调试过程的此方法查询。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT QueryProperty(  
   PROCESS_PROPERTY_TYPE  dwPropType,  
   VARIANT               *pvarPropValue);  
```  
  
```csharp  
int QueryProperty(  
   enum_PROCESS_PROPERTY_TYPE dwPropType,  
   out object                 pvarPropValue);  
```  
  
#### <a name="parameters"></a>参数  
 `dwPropType`  
 [in]查询的属性的定义。 该属性的值有：  
  
-   PROCESS_PROPERTY_COMMAND_LINE = 1  
  
-   PROCESS_PROPERTY_CURRENT_DIRECTORY = 2  
  
-   PROCESS_PROPERTY_ENVIRONMENT_VARIABLES = 3  
  
 `pvarPropValue`  
 [out]属性的值。  
  
## <a name="return-value"></a>返回值  
 如果成功，则返回`S_OK`; 否则为返回错误代码。  
  
## <a name="remarks"></a>备注  
 很少使用此方法。  
  
## <a name="see-also"></a>请参阅  
 [IDebugProcessQueryProperties](../../../extensibility/debugger/reference/idebugprocessqueryproperties.md)