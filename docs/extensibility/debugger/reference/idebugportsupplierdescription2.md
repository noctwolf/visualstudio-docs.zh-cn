---
title: "IDebugPortSupplierDescription2 |Microsoft 文档"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: IDebugPortSupplierDescription2 interface
ms.assetid: dd19b9d6-0703-44b3-9498-cedffa0ce5b7
caps.latest.revision: "8"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: d4fe70f9d0ef5273f30f16e99524247a2e45843c
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="idebugportsupplierdescription2"></a>IDebugPortSupplierDescription2
使[!INCLUDE[vsprvs](../../../code-quality/includes/vsprvs_md.md)]UI，以显示内的文本**传输信息**部分**附加到进程**对话框。  
  
## <a name="syntax"></a>语法  
  
```  
IDebugPortSupplierDescription2 : IUnknown  
```  
  
## <a name="notes-for-implementers"></a>实施者注意事项  
 通过端口供应商实现此接口。  
  
## <a name="methods"></a>方法  
 下表显示的方法`IDebugPortSupplierDescription2`。  
  
|方法|描述|  
|------------|-----------------|  
|[GetDescription](../../../extensibility/debugger/reference/idebugportsupplierdescription2-getdescription.md)|检索端口供应商的说明和描述元数据。|  
  
## <a name="requirements"></a>惠?  
 标头： Msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 程序集： Microsoft.VisualStudio.Debugger.Interop.dll