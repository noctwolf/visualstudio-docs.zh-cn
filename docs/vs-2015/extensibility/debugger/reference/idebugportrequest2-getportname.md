---
title: IDebugPortRequest2::GetPortName |Microsoft Docs
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
- IDebugPortRequest2::GetPortName
helpviewer_keywords:
- IDebugPortRequest2::GetPortName
ms.assetid: 53e2a3a4-bb34-4a02-a983-6bd84ea70587
caps.latest.revision: 11
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 11097133a3f37058e71ed81a1dd73b71480f27e0
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/12/2018
ms.locfileid: "49185440"
---
# <a name="idebugportrequest2getportname"></a>IDebugPortRequest2::GetPortName
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

获取该端口的名称。  
  
## <a name="syntax"></a>语法  
  
```cpp#  
HRESULT GetPortName(   
   BSTR* pbstrPortName  
);  
```  
  
```csharp  
int GetPortName(   
   out string pbstrPortName  
);  
```  
  
#### <a name="parameters"></a>参数  
 `pbstrPortName`  
 [out]返回的端口的名称。  
  
## <a name="return-value"></a>返回值  
 如果成功，则返回`S_OK`; 否则为返回错误代码。  
  
## <a name="remarks"></a>备注  
 [IDebugPortRequest2](../../../extensibility/debugger/reference/idebugportrequest2.md)接口通常从传递调试程序包 （客户端） 到端口提供程序 （服务器） 以获取连接到端口。 调试包和端口提供程序已经注意到该端口的可能选项。 如果一个简单的字符串可以描述该端口，则`IDebugPortRequest2::GetPortName`方法具有足够的信息来建立连接。 否则，可以由客户端可以获取服务器使用提供的其他接口`IDebugPortRequest2::QueryInterface`。  
  
## <a name="see-also"></a>请参阅  
 [IDebugPortRequest2](../../../extensibility/debugger/reference/idebugportrequest2.md)

