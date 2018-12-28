---
title: GetAutoInsertExtensions 方法
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
author: John-Hart
ms.author: johnhart
manager: douge
ms.workload:
- office
ms.openlocfilehash: 9a12adf6e83e58b877e36dd65d98b617cda3a39b
ms.sourcegitcommit: a205ff1b389fba1803acd32c54df7feb0ef7a203
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/20/2018
ms.locfileid: "53647205"
---
# <a name="getautoinsertextensions-method"></a>GetAutoInsertExtensions 方法
  获取要在调试期间自动插入的 Office 应用的相关信息。  
  
 此方法保留供将来使用。  
  
## <a name="syntax"></a>语法  
  
```csharp
HRESULT GetAutoInsertExtensions(  
    [out, retval] SAFEARRAY(BSTR)* psaExtensionNames  
);  
```  
  
### <a name="parameters"></a>参数  
  
|参数|描述|  
|---------------|-----------------|  
|*psaExtensionNames*|适用于 Office 的应用的扩展名称。|  
  
## <a name="return-value"></a>返回值  
 HRESULT 值，指示方法是否已成功完成。  
  
## <a name="remarks"></a>备注  
 作为 Office 应用程序扩展名称，它对应于下的值返回 Office 要插入的每个应用**HKEY_CURRENT_USER\Software\Microsoft\Office\WEF\Developer**。 主机必须查找注册表中的这些值，然后自动插入扩展。  
  
  