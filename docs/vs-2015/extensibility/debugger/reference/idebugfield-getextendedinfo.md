---
title: IDebugField::GetExtendedInfo |Microsoft Docs
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- IDebugField::GetExtendedInfo
helpviewer_keywords:
- IDebugField::GetExtendedInfo method
ms.assetid: 46c0dd4d-4fd5-4efd-a908-71e4248e8e8d
caps.latest.revision: 14
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 30bc444b82f81bac44286893cabc674885e25206
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/23/2018
ms.locfileid: "49911559"
---
# <a name="idebugfieldgetextendedinfo"></a>IDebugField::GetExtendedInfo
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

此方法获取扩展字段的信息。  
  
## <a name="syntax"></a>语法  
  
```cpp#  
HRESULT GetExtendedInfo(   
   REFGUID guidExtendedInfo,  
   BYTE**  prgBuffer,  
   DWORD*  pdwLen  
);  
```  
  
```csharp  
int GetExtendedInfo(  
   ref Guid guidExtendedInfo,   
   IntPtr[] prgBuffer,   
   ref uint pdwLen  
);  
```  
  
#### <a name="parameters"></a>参数  
 `guidExtendedInfo`  
 [in]选择要返回的信息。 有效值为：  
  
|“值”|描述|  
|-----------|-----------------|  
|`guidConstantValue`|作为一个字节序列的值。|  
|`guidConstantType`|类型签名形式的类型。|  
  
 `prgBuffer`  
 [out]返回扩展的信息。  
  
 `pdwLen`  
 [in、 out]以字节为单位返回大小的扩展信息。  
  
## <a name="return-value"></a>返回值  
 如果成功，则返回`S_OK`; 否则为返回错误代码。  
  
## <a name="remarks"></a>备注  
 目前，此方法返回类型或常量的值。 调用方必须释放中返回的缓冲区`prgBuffer`通过调用 COM 的`CoTaskMemFree`函数 （c + +） 或<xref:System.Runtime.InteropServices.Marshal.FreeCoTaskMem%2A>(C#)。  
  
## <a name="see-also"></a>请参阅  
 [IDebugField](../../../extensibility/debugger/reference/idebugfield.md)

