---
title: IDispError 接口 |Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
helpviewer_keywords:
- IDispError interface
ms.assetid: 3dc7b55e-94ba-4669-b20a-1e011f2d07cf
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 2c67ff6e458f8350ef36a8a454e017b3ce6ea114
ms.sourcegitcommit: d3a485d47c6ba01b0fc9878cbbb7fe88755b29af
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2019
ms.locfileid: "58144922"
---
# <a name="idisperror-interface"></a>IDispError 接口
提供详细上下文错误的信息。  
  
> [!NOTE]
>  未实现此接口。  
  
 除了继承的方法之外`IUnknown`，则`IDispError`接口公开以下方法。  
  
## <a name="methods-in-vtable-order"></a>Vtable 顺序中的方法  
  
|方法|描述|  
|------------|-----------------|  
|[IDispError::QueryErrorInfo](../../winscript/reference/idisperror-queryerrorinfo.md)|检索特定类型的错误的信息。|  
|[IDispError::GetNext](../../winscript/reference/idisperror-getnext.md)|检索下一个`IDispError`对象。|  
|[IDispError::GetHresult](../../winscript/reference/idisperror-gethresult.md)|检索中的错误代码`IDispError`对象。|  
|[IDispError::GetSource](../../winscript/reference/idisperror-getsource.md)|返回的类或引发了错误的应用程序的依赖于语言的编程标识符。|  
|[IDispError::GetHelpInfo](../../winscript/reference/idisperror-gethelpinfo.md)|返回的帮助文件的路径和解释该错误，如有可能的主题的上下文 ID。|  
|[IDispError::GetDescription](../../winscript/reference/idisperror-getdescription.md)|返回此错误的文本说明。|