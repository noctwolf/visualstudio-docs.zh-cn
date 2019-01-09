---
title: IActiveScript::AddTypeLib |Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IActiveScript.AddTypeLib
apilocation:
- scrobj.dll
helpviewer_keywords:
- IActiveScript_AddTypeLib
ms.assetid: 8e507ea8-c80a-471c-b482-ae753c6e8595
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 695edbd6f5356959785e54dc38f28b68c8c0400e
ms.sourcegitcommit: 116e9614867e0b3c627ce9001012a4c39435a42b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/08/2019
ms.locfileid: "54092535"
---
# <a name="iactivescriptaddtypelib"></a>IActiveScript::AddTypeLib
将类型库添加到该脚本在命名空间。 它类似于`#include`C/c + + 中的指令。 它允许一组预定义项目类的定义，如`typedefs`，和命名的常量添加到可供脚本运行时环境。  
  
## <a name="syntax"></a>语法  
  
```cpp
HRESULT AddTypeLib(  
    REFGUID guidTypeLib,  // CLSID of type library  
    DWORD dwMaj,          // major version number  
    DWORD dwMin,          // minor version number  
    DWORD dwFlags         // option flags  
);  
```  
  
#### <a name="parameters"></a>参数  
 `guidTypeLib`  
 [in]若要添加的类型库的 CLSID。  
  
 `dwMaj`  
 [in]主版本号。  
  
 `dwMin`  
 [in]次版本号。  
  
 `dwFlags`  
 [in]选项标志。 可以是以下值：  
  
|值|含义|  
|-----------|-------------|  
|SCRIPTTYPELIB_ISCONTROL|类型库描述主机所使用的 ActiveX 控件。|  
  
## <a name="return-value"></a>返回值  
 返回以下值之一：  
  
|返回值|含义|  
|------------------|-------------|  
|`S_OK`|成功。|  
|`E_INVALIDARG`|参数无效。|  
|`E_UNEXPECTED`|不应在调用 （例如，脚本引擎具有尚未加载或初始化）。|  
|`TYPE_E_CANTLOADLIBRARY`|无法加载指定的类型库。|  
  
## <a name="see-also"></a>请参阅  
 [IActiveScript](../../winscript/reference/iactivescript.md)