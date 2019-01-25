---
title: 'Idiasession:: Findfile |Microsoft Docs'
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaSession::findFile method
ms.assetid: a215dc21-b316-40d7-9923-55bfa014976b
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 72b010b60ef911dea970bf68567fc75a8c29e04f
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MTE95
ms.contentlocale: zh-CN
ms.lasthandoff: 01/02/2019
ms.locfileid: "53875924"
---
# <a name="idiasessionfindfile"></a>IDiaSession::findFile
检索由编译单位和名称的源文件。  
  
## <a name="syntax"></a>语法  
  
```C++  
HRESULT findFile (   
   IDiaSymbol*           pCompiland,  
   LPCOLESTR             name,  
   DWORD                 option,  
   IDiaEnumSourceFiles** ppResult  
);  
```  
  
#### <a name="parameters"></a>参数  
 `pCompiland`  
 [in][IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)对象，表示用于搜索的作为上下文将编译单位。 将此参数设置为`NULL`在所有编译单位中查找源文件。  
  
 `name`  
 [in]指定要检索的源文件的名称。 将此参数设置为`NULL`所有源要检索的文件。  
  
 `option`  
 [in]指定应用于名称搜索的比较选项。 中的值[NameSearchOptions 枚举](../../debugger/debug-interface-access/namesearchoptions.md)枚举可以单独或组合使用。  
  
 `ppResult`  
 [out]返回[IDiaEnumSourceFiles](../../debugger/debug-interface-access/idiaenumsourcefiles.md)检索包含源文件的列表的对象。  
  
## <a name="return-value"></a>返回值  
 如果成功，则返回`S_OK`; 否则为返回错误代码。  
  
## <a name="example"></a>示例  
  
```C++  
IDiaEnumSourceFiles* pEnum;  
pSession->findFile( NULL, L"sourcefile.cpp", nsFNameExt, &pEnum );  
```  
  
## <a name="see-also"></a>请参阅  
 [IDiaEnumSourceFiles](../../debugger/debug-interface-access/idiaenumsourcefiles.md)   
 [IDiaSession](../../debugger/debug-interface-access/idiasession.md)   
 [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)   
 [NameSearchOptions 枚举](../../debugger/debug-interface-access/namesearchoptions.md)