---
title: SccBackgroundGet 函数 |Microsoft Docs
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
- SccBackgroundGet
helpviewer_keywords:
- SccBackgroundGet function
ms.assetid: 69817e52-b9ac-4f4d-820b-2cc9c384f0dc
caps.latest.revision: 14
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: d2e6adbfbf5132fef6d53debe6731a2c1509eaab
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/23/2018
ms.locfileid: "49865084"
---
# <a name="sccbackgroundget-function"></a>SccBackgroundGet 函数
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

此函数检索从源代码管理每个指定的文件的无用户干预。  
  
## <a name="syntax"></a>语法  
  
```cpp  
SCCRTN SccBackgroundGet(  
   LPVOID  pContext,  
   LONG    nFiles,  
   LPCSTR* lpFileNames,  
   LONG    dwFlags,  
   LONG    dwBackgroundOperationID  
);  
```  
  
#### <a name="parameters"></a>参数  
 pContext  
 [in]源控件插件上下文指针。  
  
 nFiles  
 [in]中指定的文件数`lpFileNames`数组。  
  
 lpFileNames  
 [in、 out]要检索的文件的名称的数组。  
  
> [!NOTE]
>  名称必须是完全限定的本地文件名。  
  
 dwFlags  
 [in]命令标志 (`SCC_GET_ALL`， `SCC_GET_RECURSIVE`)。  
  
 dwBackgroundOperationID  
 [in]与此操作关联的唯一值。  
  
## <a name="return-value"></a>返回值  
 此函数的源控制插件实现应返回以下值之一：  
  
|“值”|描述|  
|-----------|-----------------|  
|SCC_OK|操作已成功完成。|  
|SCC_E_BACKGROUNDGETINPROGRESS|后台检索已正在的进行 （源代码管理插件应返回这仅在不支持同时执行的批操作）。|  
|SCC_I_OPERATIONCANCELED|正在完成之前已取消操作。|  
  
## <a name="remarks"></a>备注  
 始终与加载源代码管理插件的不同线程上调用此函数。 此函数不应返回直到完成;但是，它可以多次调用与多个文件，同时在所有列表。  
  
 利用`dwFlags`参数等同于[SccGet](../extensibility/sccget-function.md)。  
  
## <a name="see-also"></a>请参阅  
 [源代码管理插件 API 函数](../extensibility/source-control-plug-in-api-functions.md)   
 [SccGet](../extensibility/sccget-function.md)

