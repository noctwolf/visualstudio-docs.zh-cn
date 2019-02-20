---
title: IDiaSession::getEnumTables | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaSession::getEnumTables method
ms.assetid: 66e0fba2-ca63-4e24-a46a-c99c7fb61dd1
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 5c331171a62d2319666229f108428b9d62b7464e
ms.sourcegitcommit: 22b73c601f88c5c236fe81be7ba4f7f562406d75
ms.translationtype: MTE95
ms.contentlocale: zh-CN
ms.lasthandoff: 02/13/2019
ms.locfileid: "56227613"
---
# <a name="idiasessiongetenumtables"></a>IDiaSession::getEnumTables
检索包含在符号存储区中的所有表的枚举器。

## <a name="syntax"></a>语法

```C++
HRESULT getEnumTables (
    IDiaEnumTables** ppEnumTables
);
```

#### <a name="parameters"></a>参数
`ppEnumTables`  
[out]返回[IDiaEnumTables](../../debugger/debug-interface-access/idiaenumtables.md)对象。 此接口用于枚举符号存储区中的表。

## <a name="return-value"></a>返回值
如果成功，则返回`S_OK`; 否则为返回错误代码。

## <a name="example"></a>示例
此示例显示了使用的常规函数`getEnumTables`方法来获取特定的枚举器对象。 如果找到该枚举数，则该函数返回一个指向可强制转换所需的接口;否则，该函数返回`NULL`。

```C++
IUnknown *GetTable(IDiaSession *pSession, REFIID iid)
{
    IUnknown *pUnknown = NULL;
    if (pSession != NULL)
    {
        CComPtr<IDiaEnumTables> pEnumTables;
        if (pSession->getEnumTables(&pEnumTables) == S_OK)
        {
            CComPtr<IDiaTable> pTable;
            DWORD celt = 0;
            while(pEnumTables->Next(1,&pTable,&celt) == S_OK &&
                  celt == 1)
            {
                if (pTable->QueryInterface(iid, (void **)pUnknown) == S_OK)
                {
                    break;
                }
                pTable = NULL;
            }
        }
    }
    return(pUnknown);
}
```

## <a name="see-also"></a>请参阅
[IDiaEnumTables](../../debugger/debug-interface-access/idiaenumtables.md)  
[IDiaSession](../../debugger/debug-interface-access/idiasession.md)
