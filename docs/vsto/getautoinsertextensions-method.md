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
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: f8573576b40afabb5ec568a0c471e7b1d79560ba
ms.sourcegitcommit: 1466ac0f49ebf7448ea4507ae3f79acb25d51d3e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/22/2018
---
# <a name="getautoinsertextensions-method"></a>GetAutoInsertExtensions 方法
  获取有关要自动插入在调试过程中的 Office 应用程序的信息。  
  
 此方法保留供将来使用。  
  
## <a name="syntax"></a>语法  
  
```c  
HRESULT GetAutoInsertExtensions(  
    [out, retval] SAFEARRAY(BSTR)* psaExtensionNames  
);  
```  
  
### <a name="parameters"></a>参数  
  
|参数|描述|  
|---------------|-----------------|  
|*psaExtensionNames*|Office 应用程序扩展名称。|  
  
## <a name="return-value"></a>返回值  
 HRESULT 值，指示方法是否已成功完成。  
  
## <a name="remarks"></a>备注  
 作为 Office 应用程序扩展名称，它对应于下一个值返回办公室要插入的每个应用**HKEY_CURRENT_USER\Software\Microsoft\Office\WEF\Developer**。 主机必须查找注册表中的这些值，然后自动插入扩展。  
  
  