---
title: 'Iactivescriptparse:: Initnew |Microsoft Docs'
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IActiveScriptParse.InitNew
apilocation:
- scrobj.dll
helpviewer_keywords:
- IActiveScriptParse_InitNew
ms.assetid: 3a582bd6-fc0d-43a5-812f-5ea55a8517a1
caps.latest.revision: 7
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: f0998bea50d7839f93111aa6b116934fae35bfa3
ms.sourcegitcommit: 116e9614867e0b3c627ce9001012a4c39435a42b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/08/2019
ms.locfileid: "54089981"
---
# <a name="iactivescriptparseinitnew"></a>IActiveScriptParse::InitNew
初始化脚本引擎。  
  
## <a name="syntax"></a>语法  
  
```cpp
HRESULT InitNew(void);  
```  
  
## <a name="return-value"></a>返回值  
 返回`S_OK`如果成功，或`E_FAIL`如果初始化期间出错。  
  
## <a name="remarks"></a>备注  
 可以使用脚本引擎之前，必须调用以下方法之一： `IPersist*::Load`， `IPersist*::InitNew`，或`IActiveScriptParse::InitNew`。 此方法的语义是相同`IPersistStreamInit::InitNew`，因为此方法指示脚本引擎初始化其自身。 请注意，不能用来同时调用`IPersist*::InitNew`或`IActiveScriptParse::InitNew`并`IPersist*::Load`，也不是有效调用`IPersist*::InitNew`， `IActiveScriptParse::InitNew`，或`IPersist*::Load`不止一次。  
  
## <a name="see-also"></a>请参阅  
 [IActiveScriptParse](../../winscript/reference/iactivescriptparse.md)