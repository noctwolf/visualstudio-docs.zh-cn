---
title: SccPopulateDirList 函数 |Microsoft Docs
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
- SccPopulateDirList
helpviewer_keywords:
- SccPopulateDirList function
ms.assetid: dfff634b-b155-498b-a356-6eb252ac4fad
caps.latest.revision: 12
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 358512c94f46971cc91ef3ed065c83ba56e5ad16
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2018
ms.locfileid: "47471315"
---
# <a name="sccpopulatedirlist-function"></a>SccPopulateDirList 函数
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

本主题的最新版本，请参阅[SccPopulateDirList 函数](https://docs.microsoft.com/visualstudio/extensibility/sccpopulatedirlist-function)。  
  
此函数将确定哪些目录和 （可选） 文件存储在源代码管理，提供要检查的目录的列表。  
  
## <a name="syntax"></a>语法  
  
```cpp  
SCCRTN SccPopulateDirList(  
   LPVOID        pContext,  
   LONG          nDirs,  
   LPCSTR*       lpDirPaths,  
   POPDIRLISTFUNCpfnPopulate,  
   LPVOID        pvCallerData,  
   LONG          fOptions  
);  
```  
  
#### <a name="parameters"></a>参数  
 pContext  
 [in]源控件插件上下文指针。  
  
 nDirs  
 [in]中的目录路径数量`lpDirPaths`数组。  
  
 lpDirPaths  
 [in]若要检查的目录路径的数组。  
  
 pfnPopulate  
 [in]要为每个目录路径和 （可选） 中的文件名调用的回调函数`lpDirPaths`(请参阅[POPDIRLISTFUNC](../extensibility/popdirlistfunc.md)有关详细信息)。  
  
 pvCallerData  
 [in]要传递的值保持不变的回调函数。  
  
 fOptions  
 [in]控制处理目录的方式的值的组合 (请参阅的"PopulateDirList 标志"部分[位标志由特定命令](../extensibility/bitflags-used-by-specific-commands.md)有关可能的值)。  
  
## <a name="return-value"></a>返回值  
 此函数的源控制插件实现应返回以下值之一：  
  
|“值”|描述|  
|-----------|-----------------|  
|SCC_OK|已成功完成操作。|  
|SCC_E_UNKNOWNERROR|出现了错误。|  
  
## <a name="remarks"></a>备注  
 仅这些目录和 （可选） 实际上是在源控件存储库中的文件名称传递到回调函数。  
  
## <a name="see-also"></a>请参阅  
 [源代码管理插件 API 函数](../extensibility/source-control-plug-in-api-functions.md)   
 [使用特定命令的位标志](../extensibility/bitflags-used-by-specific-commands.md)   
 [POPDIRLISTFUNC](../extensibility/popdirlistfunc.md)   
 [错误代码](../extensibility/error-codes.md)
