---
title: GetAutoInsertExtensions 方法
ms.date: 02/02/2017
ms.topic: conceptual
dev_langs:
- VB
- CSharp
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: fb767ec7301a1d4e0f29003971b017339228fc9f
ms.sourcegitcommit: d0425b6b7d4b99e17ca6ac0671282bc718f80910
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2019
ms.locfileid: "56611173"
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
