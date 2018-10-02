---
title: IDebugArrayField::GetRank |Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- IDebugArrayField::GetRank
helpviewer_keywords:
- IDebugArrayField::GetRank method
ms.assetid: 2364b876-5be1-4bab-9b8f-3b6121da35c6
caps.latest.revision: 10
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: f1ddd6ae45342f0efa9312881883adfc63074e73
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2018
ms.locfileid: "47481361"
---
# <a name="idebugarrayfieldgetrank"></a>IDebugArrayField::GetRank
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

本主题的最新版本，请参阅[IDebugArrayField::GetRank](https://docs.microsoft.com/visualstudio/extensibility/debugger/reference/idebugarrayfield-getrank)。  
  
获取秩或维数的数组。  
  
## <a name="syntax"></a>语法  
  
```cpp#  
HRESULT GetRank(   
   DWORD* pdwRank  
);  
```  
  
```csharp  
int GetRank(  
   out uint pdwRank  
);  
```  
  
#### <a name="parameters"></a>参数  
 `pdwRank`  
 [out]返回排名。  
  
## <a name="return-value"></a>返回值  
 如果成功，则返回 S_OK;否则，返回错误代码。  
  
## <a name="remarks"></a>备注  
 数组的秩对应于维度的数目。 在 c + + 和 C# 中，多维数组实际上是数组的数组，并因此可以视为只是一个一维数组 (和`GetRank`方法始终返回 1)。 在中[!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]，但是，多维数组的处理方式不同并这样的数组的秩反映的维数 (和`GetRank`方法始终返回维度的数目)。  
  
## <a name="see-also"></a>请参阅  
 [IDebugArrayField](../../../extensibility/debugger/reference/idebugarrayfield.md)

