---
title: MODULE_SYMBOL_SEARCH_INFO |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- MODULE_SYMBOL_SEARCH_INFO
helpviewer_keywords:
- MODULE_SYMBOL_SEARCH_INFO structure
ms.assetid: 432aff03-08a5-4c5a-b2d5-e212090fc70a
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 9deadc13f8cbe3678282bb2d9ac619959ecd26b3
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/23/2018
ms.locfileid: "49875913"
---
# <a name="modulesymbolsearchinfo"></a>MODULE_SYMBOL_SEARCH_INFO
包含有关已搜索的符号搜索路径的状态信息。  
  
## <a name="syntax"></a>语法  
  
```cpp  
typedef struct _tagSYMBOL_SEARCH_INFO  
{  
   SYMBOL_SEARCH_INFO_FIELDS dwValidFields;  
   BSTR                      bstrVerboseSearchInfo;  
} MODULE_SYMBOL_SEARCH_INFO;  
```  
  
```csharp  
public struct MODULE_SYMBOL_SEARCH_INFO {  
   public uint   dwValidFields;  
   public string bstrVerboseSearchInfo;  
}  
```  
  
#### <a name="parameters"></a>参数  
 `dwValidFields`  
 中的标志的组合[SYMBOL_SEARCH_INFO_FIELDS](../../../extensibility/debugger/reference/symbol-search-info-fields.md)枚举，它指定此结构中所述的搜索信息的类型。  
  
 `bstrVerboseSearchInfo`  
 搜索路径和结果连接成单个字符串。  
  
## <a name="remarks"></a>备注  
 此结构从调用返回[GetSymbolInfo](../../../extensibility/debugger/reference/idebugmodule3-getsymbolinfo.md)方法。  
  
 如果`bstrVerboseSearchInfo`字段不为空，则它包含搜索路径和该搜索的结果的列表。 列表格式与跟省略号 （"..."） 后, 跟结果的路径。 如果有多个路径结果对，然后由"\r\n"（回车符-/ 换行） 对分隔每个对。 该模式如下所示：  
  
 \<路径 >...\<结果 > \r\n\<路径 >...\<结果 > \r\n\<路径 >...\<结果 >  
  
 请注意，最后一项没有 \r\n 序列。  
  
 下面是可能发生`bstrVerboseSearchInfo`已发送到标准输出的字符串。  
  
 `c:\symbols\user32.pdb... File not found.`  
  
 `c:\winnt\symbols\user32.pdb... Version does not match.`  
  
 `\\symbols\symbols\user32.dll\0a8sd0ad8ad\user32.pdb... Symbols loaded.`  
  
## <a name="requirements"></a>要求  
 标头： msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Assembly: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>请参阅  
 [结构和联合](../../../extensibility/debugger/reference/structures-and-unions.md)   
 [GetSymbolInfo](../../../extensibility/debugger/reference/idebugmodule3-getsymbolinfo.md)