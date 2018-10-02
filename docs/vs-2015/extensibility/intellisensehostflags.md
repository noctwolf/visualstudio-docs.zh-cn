---
title: IntelliSenseHostFlags |Microsoft Docs
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
- IntellisenseHostFlags
helpviewer_keywords:
- IntelliSense, IntellisenseHostFlags enumeration
- IntellisenseHostFlags enumeration
ms.assetid: 0930640b-eb84-48ef-a8f7-d4268f55c99c
caps.latest.revision: 7
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: ef0e800cbe2d101fa9ce44367ef54fb1834a7fd4
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2018
ms.locfileid: "47470998"
---
# <a name="intellisensehostflags"></a>IntelliSenseHostFlags
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

本主题的最新版本，请参阅[IntelliSenseHostFlags](https://docs.microsoft.com/visualstudio/extensibility/intellisensehostflags)。  
  
指定 IntelliSense 主机标志。  
  
## <a name="syntax"></a>语法  
  
```cpp#  
enum IntellisenseHostFlags  
{  
    IHF_READONLYCONTEXT      = 0x00000001  
    IHF_NOSEPARATESUBJECT    = 0x00000002  
    IHF_SINGLELINESUBJECT    = 0x00000004  
    IHF_FORCECOMMITTOCONTEXT = 0x00000008  
    IHF_OVERTYPE             = 0x00000010  
};  
```  
  
#### <a name="parameters"></a>参数  
  
|成员|描述|  
|-------------|-----------------|  
|`IHF_READONLYCONTEXT`|上下文缓冲区是只读的。|  
|`IHF_NOSEPARATESUBJECT`|没有使用者的文本。 上下文缓冲区包含 IntelliSense 目标 (意味着`!IHF_READONLYCONTEXT`)。|  
|`IHF_SINGLELINESUBJECT`|不支持多行的主题文本。|  
|`IHF_FORCECOMMITTOCONTEXT`|与 `CanCommitIntoReadOnlyBuffer` 相同。|  
|`IHF_OVERTYPE`|应在改写模式下编辑 （在使用者或上下文）。|  
  
## <a name="requirements"></a>要求  
 SingleFileeditor.idl  
  
## <a name="see-also"></a>请参阅  
 <xref:Microsoft.VisualStudio.TextManager.Interop>

