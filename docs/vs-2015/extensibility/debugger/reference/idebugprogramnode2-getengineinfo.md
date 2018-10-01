---
title: IDebugProgramNode2::GetEngineInfo |Microsoft Docs
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
- IDebugProgramNode2::GetEngineInfo
helpviewer_keywords:
- IDebugProgramNode2::GetEngineInfo
ms.assetid: 664e7fe5-9100-4b7d-9dc5-e5a4dd0d0451
caps.latest.revision: 14
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 42faae15c9e34bad603cfb0093830909282d544c
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2018
ms.locfileid: "47482052"
---
# <a name="idebugprogramnode2getengineinfo"></a>IDebugProgramNode2::GetEngineInfo
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

本主题的最新版本，请参阅[IDebugProgramNode2::GetEngineInfo](https://docs.microsoft.com/visualstudio/extensibility/debugger/reference/idebugprogramnode2-getengineinfo)。  
  
获取名称和标识符的运行程序的调试引擎 (DE)。  
  
## <a name="syntax"></a>语法  
  
```cpp#  
HRESULT GetEngineInfo (   
   BSTR* pbstrEngine,  
   GUID* pguidEngine  
);  
```  
  
```csharp  
int GetEngineInfo(  
   out string pbstrEngine,   
   out Guid pguidEngine  
);  
```  
  
#### <a name="parameters"></a>参数  
 `pbstrEngine`  
 [out]返回的运行程序 DE 名称 (c + + 专用： 这可以是 null 指针，该值指示调用方不希望该引擎的名称)。  
  
 `pguidEngine`  
 [out]返回运行程序 DE 的全局唯一标识符 (特定于 c + + 的： 这可以是 null 指针，该值指示调用方不感兴趣的引擎的 GUID)。  
  
## <a name="return-value"></a>返回值  
 如果成功，则返回`S_OK`; 否则为返回错误代码。  
  
## <a name="see-also"></a>请参阅  
 [IDebugProgramNode2](../../../extensibility/debugger/reference/idebugprogramnode2.md)

