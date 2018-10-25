---
title: 'Idiaenuminjectedsources:: Clone |Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaEnumInjectedSources::Clone method
ms.assetid: 18038691-c140-426a-8617-27f0360650f3
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 6bca7bd10b7092654d1bd7c7bf8c0f0f18ee72a3
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/23/2018
ms.locfileid: "49950984"
---
# <a name="idiaenuminjectedsourcesclone"></a>IDiaEnumInjectedSources::Clone
创建一个包含当前枚举数形式的相同枚举状态的枚举器。  
  
## <a name="syntax"></a>语法  
  
```C++  
HRESULT Clone (   
   IDiaEnumInjectedSources** ppenum  
);  
```  
  
#### <a name="parameters"></a>参数  
 `ppenum`  
 [out]返回[IDiaEnumInjectedSources](../../debugger/debug-interface-access/idiaenuminjectedsources.md)对象，其中包含重复的枚举器。 未复制的插入的源，仅枚举器。  
  
## <a name="return-value"></a>返回值  
 如果成功，则返回`S_OK`; 否则为返回错误代码。  
  
## <a name="see-also"></a>请参阅  
 [IDiaEnumInjectedSources](../../debugger/debug-interface-access/idiaenuminjectedsources.md)