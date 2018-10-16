---
title: SccEnumChangedFiles 函数 |Microsoft Docs
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
- SccEnumChangedFiles
helpviewer_keywords:
- SccEnumChangedFiles function
ms.assetid: 76cac510-107b-4c1a-ba60-9c39b6db2e71
caps.latest.revision: 13
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: e4bc5595b5421e0be0139598464e70c6af52df80
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/12/2018
ms.locfileid: "49294471"
---
# <a name="sccenumchangedfiles-function"></a>SccEnumChangedFiles 函数
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

此函数将给定的本地文件的列表，确定哪些文件是不同于源代码代码管理数据库中的相应版本。  
  
## <a name="syntax"></a>语法  
  
```cpp  
SCCRTN SccEnumChangedFiles(  
   LPVOID  pContext,  
   HWND    hWnd,  
   LONG    cFiles,  
   LPCSTR* lpFileNames,  
   LONG*   plIsFileDifferent  
);  
```  
  
#### <a name="parameters"></a>参数  
 pContext  
 [in]源控件插件上下文指针。  
  
 hWnd  
 [in]它提供了任何对话框，父级可以使用源代码管理插件，则 IDE 窗口的句柄。  
  
 cFiles  
 [in]文件名称中指定的数量`lpFileNames`数组。 此外指定了大小的`plIsFileDifferent`数组。  
  
 lpFileNames  
 [in]若要检查的本地文件名称的数组。  
  
 plIsFileDifferent  
 [in、 out]值，该值指示每个文件的差异状态数组 (数组必须至少具有`cFiles`条目)。 该文件是不同的非零值表示。  
  
## <a name="return-value"></a>返回值  
 此函数的源控制插件实现应返回以下值之一：  
  
|“值”|描述|  
|-----------|-----------------|  
|SCC_OK|操作已成功完成。|  
|SCC_UNSPECIFIEDERROR|常规错误。|  
  
## <a name="see-also"></a>请参阅  
 [源代码管理插件 API 函数](../extensibility/source-control-plug-in-api-functions.md)

