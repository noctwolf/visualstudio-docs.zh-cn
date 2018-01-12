---
title: "GetAutoInsertExtensions 方法 |Microsoft 文档"
ms.custom: 
ms.date: 02/02/2017
ms.reviewer: 
ms.suite: 
ms.technology: office-development
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
author: TerryGLee
ms.author: tglee
manager: ghogen
ms.workload: office
ms.openlocfilehash: a53148b0130dd05f3ffc3360a518f9b2b66002e7
ms.sourcegitcommit: f9fbf1f55f9ac14e4e5c6ae58c30dc1800ca6cda
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/10/2018
---
# <a name="getautoinsertextensions-method"></a>GetAutoInsertExtensions 方法
  获取有关要自动插入在调试过程中的 Office 应用程序的信息。  
  
 此方法保留供将来使用。  
  
## <a name="syntax"></a>语法  
  
```  
HRESULT GetAutoInsertExtensions(  
    [out, retval] SAFEARRAY(BSTR)* psaExtensionNames  
);  
```  
  
#### <a name="parameters"></a>参数  
  
|参数|描述|  
|---------------|-----------------|  
|*psaExtensionNames*|Office 应用程序扩展名称。|  
  
## <a name="return-value"></a>返回值  
 HRESULT 值，指示方法是否已成功完成。  
  
## <a name="remarks"></a>备注  
 Office 要插入每个应用作为 Office 应用程序扩展名称，它们对应于下 HKEY_CURRENT_USER\Software\Microsoft\Office\WEF\Developer 值返回。 主机必须查找注册表中的这些值，然后自动插入扩展。  
  
  