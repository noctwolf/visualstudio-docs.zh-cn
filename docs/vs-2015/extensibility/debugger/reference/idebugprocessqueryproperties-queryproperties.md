---
title: IDebugProcessQueryProperties::QueryProperties |Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- IDebugProcessQueryProperties::QueryProperties
ms.assetid: 976a9962-b689-45bb-afb6-16b2c5dbc3b8
caps.latest.revision: 6
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 8edda58ecbc0fd59d2a760ac7f9b9e562e92703d
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2018
ms.locfileid: "47482792"
---
# <a name="idebugprocessquerypropertiesqueryproperties"></a>IDebugProcessQueryProperties::QueryProperties
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

本主题的最新版本，请参阅[IDebugProcessQueryProperties::QueryProperties](https://docs.microsoft.com/visualstudio/extensibility/debugger/reference/idebugprocessqueryproperties-queryproperties)。  
  
此方法查询的调试过程指定的属性值。  
  
## <a name="syntax"></a>语法  
  
```cpp#  
HRESULT QueryProperties(  
   ULONG                  celt,  
   PROCESS_PROPERTY_TYPE *rgdwPropTypes,  
   VARIANT               *rgtPropValues);  
```  
  
```csharp  
int QueryProperties(  
   uint                       celt,  
   enum_PROCESS_PROPERTY_TYPE rgdwPropTypes,  
   out object[ ]              rgtPropValues);  
```  
  
#### <a name="parameters"></a>参数  
 `celt`  
 [in]包含的属性定义和属性值的数组的大小。  
  
 `dwPropType`  
 [in]一个数组，包含查询的属性的定义。 可能的值为：  
  
-   PROCESS_PROPERTY_COMMAND_LINE = 1  
  
-   PROCESS_PROPERTY_CURRENT_DIRECTORY = 2  
  
-   PROCESS_PROPERTY_ENVIRONMENT_VARIABLES = 3  
  
 `pvarPropValue`  
 [out]包含属性值的数组。  
  
## <a name="return-value"></a>返回值  
 如果成功，则返回`S_OK`; 否则为返回错误代码。  
  
## <a name="remarks"></a>备注  
 很少使用此方法。  
  
## <a name="see-also"></a>请参阅  
 [IDebugProcessQueryProperties](../../../extensibility/debugger/reference/idebugprocessqueryproperties.md)

