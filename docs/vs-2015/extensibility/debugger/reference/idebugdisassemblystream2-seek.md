---
title: IDebugDisassemblyStream2::Seek |Microsoft Docs
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
- IDebugDisassemblyStream2::Seek
helpviewer_keywords:
- IDebugDisassemblyStream2::Seek
ms.assetid: afec3008-b1e0-4803-ad24-195dbfb6497e
caps.latest.revision: 11
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: b718412793271d96a8c8a22bb8c69997c3305cdc
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2018
ms.locfileid: "47482061"
---
# <a name="idebugdisassemblystream2seek"></a>IDebugDisassemblyStream2::Seek
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

本主题的最新版本，请参阅[IDebugDisassemblyStream2::Seek](https://docs.microsoft.com/visualstudio/extensibility/debugger/reference/idebugdisassemblystream2-seek)。  
  
将读取的指针移动反汇编流给定数量的相对于指定位置的说明中。  
  
## <a name="syntax"></a>语法  
  
```cpp#  
HRESULT Seek(   
   SEEK_START          dwSeekStart,  
   IDebugCodeContext2* pCodeContext,  
   UINT64              uCodeLocationId,  
   INT64               iInstructions  
);  
```  
  
```csharp  
int Seek(   
   enum_SEEK_START    dwSeekStart,  
   IDebugCodeContext2 pCodeContext,  
   ulong              uCodeLocationId,  
   long               iInstructions  
);  
```  
  
#### <a name="parameters"></a>参数  
 `dwSeekStart`  
 [in]中的值[SEEK_START](../../../extensibility/debugger/reference/seek-start.md)枚举，用于指定开始查找过程的相对位置。  
  
 `pCodeContext`  
 [in][IDebugCodeContext2](../../../extensibility/debugger/reference/idebugcodecontext2.md)对象，表示查找操作是相对于代码上下文。 仅当使用此参数`dwSeekStart`  =  `SEEK_START_CODECONTEXT`; 否则为此参数将被忽略并且可以为 null 值。  
  
 `uCodeLocationId`  
 [in]查找操作是相对于代码位置标识符。 如果使用此参数`dwSeekStart`  =  `SEEK_START_CODELOCID`; 否则为此参数将被忽略，可以设置为 0。 请参阅备注部分[GetCodeLocationId](../../../extensibility/debugger/reference/idebugdisassemblystream2-getcodelocationid.md)方法有关的代码位置标识符的说明。  
  
 `iInstructions`  
 [in]要移动相对于指定的位置的指令数`dwSeekStart`。 此值可以是负数，以向后移动。  
  
## <a name="return-value"></a>返回值  
 如果成功，则返回`S_OK`。 返回`S_FALSE`如果搜寻位置到可用的指令的一个点，该列表。 否则，返回错误代码。  
  
## <a name="remarks"></a>备注  
 如果搜索到列表的开头之前位置，读取的位置设置为列表中的第一个指令。 如果看到的是将其置于列表末尾之后，读取的位置设置的最后一个指令列表中。  
  
## <a name="see-also"></a>请参阅  
 [IDebugDisassemblyStream2](../../../extensibility/debugger/reference/idebugdisassemblystream2.md)   
 [SEEK_START](../../../extensibility/debugger/reference/seek-start.md)   
 [IDebugCodeContext2](../../../extensibility/debugger/reference/idebugcodecontext2.md)   
 [GetCodeLocationId](../../../extensibility/debugger/reference/idebugdisassemblystream2-getcodelocationid.md)

