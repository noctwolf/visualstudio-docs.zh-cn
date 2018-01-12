---
title: "IWefDebuggingSupport 接口 |Microsoft 文档"
ms.custom: 
ms.date: 02/02/2017
ms.reviewer: 
ms.suite: 
ms.technology: office-development
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
author: TerryGLee
ms.author: tglee
manager: ghogen
ms.workload: office
ms.openlocfilehash: 7b132c51e12d553bcd6e722e87c8aeee96be5e5c
ms.sourcegitcommit: f9fbf1f55f9ac14e4e5c6ae58c30dc1800ca6cda
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/10/2018
---
# <a name="iwefdebuggingsupport-interface"></a>IWefDebuggingSupport 接口
  由调试环境中，如 Visual Studio 中，为了便于调试 office 应用程序的实现。 Office 应用程序，如 Word 或 Excel，将从 Visual Studio 中获得此接口，然后在某些点接口上在调试会话期间调用方法。  
  
## <a name="syntax"></a>语法  
  
```  
[  
    uuid(ccaf1a90-ce1c-4199-9cd6-b40c5c57a671),  
    oleautomation  
]  
interface IWefDebuggingSupport : IUnknown  
{  
    HRESULT SetWefProcessId(  
        [in] DWORD dwProcessId);  
    HRESULT GetAutoInsertExtensions(  
        [out, retval] SAFEARRAY(BSTR)* psaExtensionNames);  
}  
```  
  
## <a name="methods"></a>方法  
 下表列出 IWefDebuggingSupport 接口定义的方法。  
  
|name|描述|  
|----------|-----------------|  
|[GetAutoInsertExtensions 方法](../vsto/getautoinsertextensions-method.md)|获取有关要自动插入在调试过程中的 Office 应用程序的信息。|  
|[SetWefProcessId 方法](../vsto/setwefprocessid-method.md)|提供将运行 Web 扩展框架 (WEF) 内容的进程标识符。|  
  
  