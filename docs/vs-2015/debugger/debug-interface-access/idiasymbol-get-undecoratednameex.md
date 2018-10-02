---
title: 'Idiasymbol:: Get_undecoratednameex |Microsoft Docs'
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- IDiaSymbol::get_undecoratedNameEx method
ms.assetid: 579aed0b-c57d-41a1-a94a-3bf665fd4a9d
caps.latest.revision: 14
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: e8299775b1cb75a874c4d79de9560d7149bb36d4
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2018
ms.locfileid: "47479289"
---
# <a name="idiasymbolgetundecoratednameex"></a>IDiaSymbol::get_undecoratedNameEx
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

本主题的最新版本，请参阅[idiasymbol:: Get_undecoratednameex](https://docs.microsoft.com/visualstudio/debugger/debug-interface-access/idiasymbol-get-undecoratednameex)。  
  
检索部分或全部 c + + 的未修饰名称修饰 （链接） 名称。  
  
## <a name="syntax"></a>语法  
  
```cpp#  
HRESULT get_undecoratedNameEx(   
   DWORD undecorateOptions,  
   BSTR* pRetval  
);  
```  
  
#### <a name="parameters"></a>参数  
 `undecoratedOptions`  
 [in]指定的标志的组合返回该控件。 请参阅备注部分的特定值以及他们的操作。  
  
 `pRetVal`  
 [out]返回未修饰的名为 c + + 修饰名。  
  
## <a name="return-value"></a>返回值  
 如果成功，则返回`S_OK`; 否则为返回`S_FALSE`或错误代码。  
  
> [!NOTE]
>  返回值为`S_FALSE`表示该属性不是可用于符号。  
  
## <a name="remarks"></a>备注  
 `undecorateOptions`可以是下列标志的组合。  
  
> [!NOTE]
>  标记名称未定义在 DIA SDK 中，因此您需要将声明添加到你的代码，或使用原始值。  
  
|Flag|值|描述|  
|----------|-----------|-----------------|  
|UNDNAME_COMPLETE|0x0000|启用完全 undecoration。|  
|UNDNAME_NO_LEADING_UNDERSCORES|0x0001|从删除前导下划线 Microsoft 扩展关键字。|  
|UNDNAME_NO_MS_KEYWORDS|0x0002|禁用 Microsoft 扩展关键字的扩展。|  
|UNDNAME_NO_FUNCTION_RETURNS|0x0004|禁用扩展的主声明的返回类型。|  
|UNDNAME_NO_ALLOCATION_MODEL|0x0008|禁用声明模型的扩展。|  
|UNDNAME_NO_ALLOCATION_LANGUAGE|0x0010|禁用扩展的声明语言说明符。|  
|UNDNAME_RESERVED1|0x0020|保留。|  
|UNDNAME_RESERVED2|0x0040|保留。|  
|UNDNAME_NO_THISTYPE|0x0060|禁用所有修饰符上`this`类型。|  
|UNDNAME_NO_ACCESS_SPECIFIERS|0x0080|禁用扩展的成员的访问说明符。|  
|UNDNAME_NO_THROW_SIGNATURES|0x0100|禁用扩展"抛出的签名的"函数和函数的指针。|  
|UNDNAME_NO_MEMBER_TYPE|0x0200|禁用的扩展`static`或`virtual`成员。|  
|UNDNAME_NO_RETURN_UDT_MODEL|0x0400|为 UDT 返回禁用 Microsoft 模型的扩展。|  
|UNDNAME_32_BIT_DECODE|0x0800|Undecorates 32 位的修饰的名称。|  
|UNDNAME_NAME_ONLY|0x1000|获取仅主声明; 的名称只需返回 [作用域::] 名称。  展开模板参数。|  
|UNDNAME_TYPE_ONLY|0x2000|输入是只需编码; 的类型组合抽象声明符。|  
|UNDNAME_HAVE_PARAMETERS|0x4000|可以使用实际的模板参数。|  
|UNDNAME_NO_ECSU|0x8000|禁止显示枚举/类/结构/联合。|  
|UNDNAME_NO_IDENT_CHAR_CHECK|0x10000|禁止显示有效的标识符字符检查。|  
|UNDNAME_NO_PTR64|0x20000|不在输出中包括 ptr64。|  
  
## <a name="see-also"></a>请参阅  
 [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)



