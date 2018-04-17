---
title: SccQueryChanges 函数 |Microsoft 文档
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- SccQueryChanges
helpviewer_keywords:
- SccQueryChanges function
ms.assetid: 4cd58eb3-6952-49b1-9620-8682e3eaa604
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: d887c0cea989fa6a955edc2f39b9667e7421093d
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/16/2018
---
# <a name="sccquerychanges-function"></a>SccQueryChanges 函数
此函数枚举给定的文件，对于通过回调函数的每个文件提供名称更改的信息的列表。  
  
## <a name="syntax"></a>语法  
  
```cpp  
SCCRTN SccQueryChanges(  
   LPVOID           pContext,  
   LONG             nFiles,  
   LPCSTR*          lpFileNames,  
   QUERYCHANGESFUNC pfnCallback,  
   LPVOID           pvCallerData  
);  
```  
  
#### <a name="parameters"></a>参数  
 pContext  
 [in]源控件插件的上下文指针。  
  
 nFiles  
 [in]中的文件数`lpFileNames`数组。  
  
 lpFileNames  
 [in]要获取其相关信息的文件名的数组。  
  
 pfnCallback  
 [in]要输入列表中每个文件的名称调用的回调函数 (请参阅[QUERYCHANGESFUNC](../extensibility/querychangesfunc.md)有关详细信息)。  
  
 pvCallerData  
 [in]对回调函数，将传递的值保持不变。  
  
## <a name="return-value"></a>返回值  
 此函数的源代码控制插件实现应返回以下值之一：  
  
|值|描述|  
|-----------|-----------------|  
|SCC_OK|查询过程成功完成。|  
|SCC_E_PROJNOTOPEN|尚未在源代码管理中打开项目。|  
|SCC_E_ACCESSFAILURE|没有访问源代码管理系统，可能由于网络或争用问题发生时出现问题。|  
|SCC_E_NONSPECIFICERROR|未指定或常规时出错。|  
  
## <a name="remarks"></a>备注  
 要查询的更改是对命名空间： 具体而言，重命名、 添加和删除文件。  
  
## <a name="see-also"></a>另请参阅  
 [源控件插件 API 函数](../extensibility/source-control-plug-in-api-functions.md)   
 [QUERYCHANGESFUNC](../extensibility/querychangesfunc.md)   
 [错误代码](../extensibility/error-codes.md)