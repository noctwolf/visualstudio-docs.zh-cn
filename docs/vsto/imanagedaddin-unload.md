---
title: IManagedAddin::Unload
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- Unload method
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: db805aa1e00d672b4a0579e546a6827e9135b909
ms.sourcegitcommit: 6944ceb7193d410a2a913ecee6f40c6e87e8a54b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/06/2018
ms.locfileid: "35670311"
---
# <a name="imanagedaddinunload"></a>IManagedAddin::Unload
  只在托管 VSTO 外接程序卸载之前调用。  
  
## <a name="syntax"></a>语法  
  
```csharp
HRESULT Unload();  
```  
  
## <a name="return-value"></a>返回值  
 HRESULT 值，指示方法是否已成功完成。  
  
## <a name="remarks"></a>备注  
 当前版本的 Microsoft Office 不调用此方法。 此方法保留供将来使用。  
  
## <a name="see-also"></a>请参阅  
 [IManagedAddin 接口](../vsto/imanagedaddin-interface.md)   
 [IManagedAddin::Load](../vsto/imanagedaddin-load.md)  
  
  